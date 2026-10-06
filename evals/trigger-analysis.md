# Can the Bot be trigger based? Mostly yes, and it costs one new design decision

**The question:** if the Bot can connect to a calendar, can it not be trigger based rather than scheduled?

**Partly, and the part that is true matters.** The easy answer is that routines are scheduled rather than event triggered, and that is where the thinking usually stops. It should not.

## The two primitives, and what they actually give you
| | What it is | What it does not do |
|---|---|---|
| A **routine** | time scheduled: run at this time | fire on an event |
| A **calendar connector** | read access to the calendar | push you an event when something changes |

So there is no event subscription. Reading a calendar does not make the calendar tell you anything.

**But a routine on a short interval that asks "what is new since last time" is functionally a trigger**, with a latency equal to the interval. That is the thing I missed by treating the words as a category instead of a dial.

## Trigger and sweep are not two things. They are one dial.
| Interval | What it feels like | Honest description |
|---|---|---|
| once daily, evening | a sweep | "your cards are ready in the morning" |
| hourly | nearly live | "a new invite gets a card within the hour" |
| the platform minimum | **a trigger** | "a new invite gets a card within N minutes" |

**The one thing to check before promising a number:** what the minimum routine interval actually is on this platform. I do not know it and will not guess, because the whole claim on the landing page depends on it. That is a five minute check in the Bot's own settings screen.

## What this does to the landing page problem
The page says the agent is **"triggered by a calendar invite."** I recommended changing it to a sweep. That was the right call for a daily routine and the wrong call if the interval can be short.

**The honest wording either way is a latency, not a mechanism:** *"picks up a new invite within about fifteen minutes."* That is true, checkable, and closer to what the page already claims than "sweep" is. **Describe the lag, not the trigger.**

## The cost nobody sees until they build it: the Bot has to remember
A fifteen minute poll runs about 96 times a day. **Each run finds the same meetings as the last one.** Without a memory of what it has already prepared, it writes 96 identical cards for one meeting, burns research on every single one, and the owner stops opening the output by Tuesday.

So polling needs state: a record of which meetings already have cards.

**And here is the collision.** The binder is **read only**, absolutely, enforced by a platform rule and a drift test, because a binder that changes quietly makes every card after it worthless. Now the agent needs somewhere to write.

### The wrong fix, and it is the obvious one
Add an exception: "the binder is read only, except `carded.md`."

**Do not do this.** Rule 6 currently reads: never edit, move, reformat, summarise, tidy or append to any file in `/workspace/call-prep/`. It is absolute, which is why it survives being paraphrased by a builder bot. The moment it has an exception, it becomes a rule with a judgement call in it, and the judgement call is "is this file the exception?" That is precisely the kind of rule that gets smoothed away, and the failure is silent for weeks.

### The fix: a second folder, not an exception
```
/workspace/call-prep/          the binder.  READ ONLY, no exceptions, ever.
/workspace/call-prep-state/    one file the agent writes.  carded.md
```

**Two locations with two unqualified rules, rather than one location with a rule and a carve out.**

`carded.md` holds one line per meeting already prepared: the meeting id, when the card was written, and nothing else. No research, no card content, no company facts. If it is ever lost, the worst case is a handful of duplicate cards for one day.

**The general principle, worth keeping:** when a rule has to hold absolutely, do not weaken it with an exception. Move the thing that needs different treatment somewhere else and give it its own rule.

## The rest of the bill
| Cost | Size |
|---|---|
| 96 calendar reads a day | small, but **there is no dry run on this platform**, so every one is a real call |
| Research per new meeting | unchanged. Bounded by how many meetings actually get booked, not by the poll rate |
| A file the agent writes | the design cost above, and the only real one |
| The coverage line still matters | a poll can still miss, and it must still say what it missed |

## Recommendation
**Build the sweep, ship the dial.**

1. **For the show: the evening sweep.** It is the thing that works, the thing the binder is ready for, and one less moving part in a live build.
2. **Add `carded.md` and the second folder now**, while the block is being edited anyway, because retrofitting state into a running agent means editing its instructions, and we have just learned what a save can do to those.
3. **Then shorten the interval** and say the latency out loud: "a new invite gets a card within N minutes." Check N first.
4. **Fix the landing page to a latency rather than a mechanism**, whichever interval we land on.

## What I got wrong, and the shape of it
I had two facts, routines are scheduled and connectors read calendars, and concluded "no trigger." The conclusion treats a continuous quantity as a category. A sweep at a short enough interval **is** a trigger for every practical purpose, and the real question was never whether it is event driven, it was how much latency the owner can live with.

**This is a different class of mistake from the usual one.** Most errors in a build like this are holding the right fact and using a wrong one, which is what a binder fixes. This one is holding **both** right facts and drawing a lazy line between them, and no binder fixes that. Only somebody asking the obvious follow up question does.
