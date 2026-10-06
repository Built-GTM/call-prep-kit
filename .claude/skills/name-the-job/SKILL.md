---
name: name-the-job
description: Turn a rough idea for an AI agent into a one-sentence job, a fence of everything it must not do, and the map of sibling agents that fence implies. Takes natural language in ("I want something that writes outbound off signals") and returns the spec plus a build order, telling you which fence items are already covered by a skill you own and which are gaps you have to build. This is step one of the agent build order and it runs before any prompt writing. Trigger on "I want an agent that", "spec this agent", "name the job", "what agents do I need for this", "is this one agent or several", "help me scope this agent", "break this into agents", "what does this agent not do", or any moment someone describes an agent they are about to build.
---

# Name the Job: one sentence, one fence, and the swarm it implies

## What this does

Takes a rough description of an agent somebody wants and returns three things: the job in one sentence, a fence listing everything the agent must not do with who does each instead, and the map of other agents that fence just revealed.

The fence is the point. Most people describe an agent by what it should do and build until it does five things badly. Writing down what it must not do, with a name next to each item, turns one vague agent into a scoped agent plus a list of its siblings. That list is your build order, and you got it before writing a prompt.

This is step one of the agent build order in `SHIP-A-SOLUTION.md`. It runs after the problem is named and before any contract or prompt exists. It does not write the contract, that is `agent-contract`. It does not decide what the agent versus the human owns, that is `cut-the-drag`. It does not name the problem or find the receipt, that is `solve-the-problem`, which runs before this.

## What you'll need

A description of what you want, in whatever words you have. One paragraph is plenty, one sentence is enough to start. No connectors required.

## How this runs at your connection level

This skill is never reliant on a connector. It runs on the data you give it today and gets more powerful as you connect tools. It never invents a number it cannot see. A gap is a prompt, not a guess.

- **Bring your data**: describe the agent in your own words. The skill runs the full scoping today and asks you the questions it needs. No connection required.
- **Connect your tools**: pointed at your skill library and repo, the same skill resolves each fence item automatically, telling you which ones you already own and which are real gaps, instead of asking you.
- **Just exploring**: no agent in mind? Get the five fence questions and a worked example, so you can see how one idea becomes four agents before you try it on your own.

Every run ends with the one thing that would make the next run sharper, a field to add or a tool to connect.

## Customize this for yourself

| Set this | What it is | Default / Example |
|---|---|---|
| SKILL library | where your existing skills live, so fence items can resolve | `public-skills/` |
| AGENT registry | where already-built agents are listed | your plugin marketplace or agent index |
| BLOCKER rule | what makes a gap a blocker rather than later work | the target agent cannot run without it |
| SPLIT trigger | what means you have two agents | splitting would duplicate the read; an "and" or comma joining two deliverables is the weaker signal |

## The method

### Step 1: Force the one sentence

Write it in this shape and no other: **given INPUT, return OUTPUT.** One input clause, one output clause.

Say the grain while you are here. One record in and one out, or many in and one summary out. "Why we are losing" is portfolio grain and "why did we lose this one" fans out per deal. Both fit the sentence shape and they are different agents, so pick before you go on.

Then apply the split test, which is about work and not about grammar. **Would splitting duplicate the work?** If the halves would each re-read the same input, and could disagree about what they read, they are one agent. Several fields of one record, produced by one read of one input, are one output: a renewal-terms row, not a date agent plus a notice-period agent plus a clause agent.

Only after that, look at the sentence. An "and" or a comma joining two genuinely different deliverables, from different inputs or different reads, means two agents: "a scored list and a draft message" is two agents that fail at different times and share the blame. When the work test and the sentence disagree, the work test wins. Do not let a rewording settle it. If calling the output one noun is the only thing that made it pass, you have renamed the problem.

The output may also include a refusal: "return one message, or a refusal and the questions that would make it writable" is one output in two states. The states have to be addressed to the same person. A refusal that goes back to the operator is a state. Something that goes outward to a third party, like a clarifying question sent to a customer, is a second deliverable with its own delivery path, and that usually belongs to a comms agent rather than this one.

When a request names several jobs, do not run this skill once per job and hand back a pile of specs. Pick the target: the one whose current output is worst. If that is not obvious, ask. The rest become fence items and land on the map as suppliers or later work. One spec and one map, every time. If two really are co-equal and nobody can choose, scope the one that is upstream of the other and say why.

A schedule or a trigger is not a fence item and gets no resolution. Record it on its own line: what fires this, and what it does when it fires with nothing to do. A recurring agent that wakes to an empty queue should do nothing visible rather than produce an empty report.

### Step 2: Build the fence

Ask these five questions in order. Each one surfaces work that feels like it belongs and does not.

1. **What data does it need that it would have to go and get?** Fetching is almost always a different agent, because fetching fails differently than judging.
2. **What decision does it make that someone or something else already makes?** If a scoring model, a CRM field or a person already decides this, the agent reads that decision rather than making its own. Careful here, because this question can land on the job itself rather than beside it. The test: would reading somebody else's answer make this agent pointless? If yes and that answer exists, the real job is a reader, and say so. If yes and no such answer exists, this is the judgment the agent owns. Write that down as owned, with the reasoning, so the next person does not mistake it for a gap.
3. **What happens to its output after it is produced?** Sending, scheduling, posting and writing back are their own jobs.
4. **What happens immediately before its input arrives?** Whatever produces the input is a sibling, and it is usually the blocker.
5. **What would stop it cold on a real input?** Not a wrong answer, an impossible one. A scanned PDF where it expects text. A language it cannot read. A file too large to hold. These are capability gaps, and each one is a sibling agent or a preprocessing step. What the agent does with a merely bad or empty input is a contract question, not a fence item, so leave that for `agent-contract`.

Questions one, three and four produce an item for almost every agent that has ever existed, because nearly everything needs something fetched, something written somewhere, and something upstream. Those three are plumbing and they do not count toward a healthy fence. The bar is **at least one item specific to this job**: a decision it must not make, a capability it does not have, or a judgment a named person keeps. If you cannot find one of those, you have not understood the job yet.

### Step 3: Resolve every fence item

Each item gets exactly one of three resolutions, and you say which:

- **Covered.** An existing skill or agent does this. Name it. Check before you claim it: a skill that sounds right and does something adjacent is not coverage.
- **Human.** A person does this and should keep doing it. Name the role, not the team.
- **Gap.** Nothing does this yet. This is a new agent, and it goes on the map.
- **Unverified.** It might be covered and you could not check. Name the candidate and what would confirm it. This is a legitimate resolution rather than a failure, and it is the honest answer every time this skill runs without access to your library. Never resolve an unchecked item to GAP. A map that tells someone to rebuild a skill they already own is worse than one that says go look.

Checked means you read the candidate's own description and method. A name that sounds right is not coverage and never was.

"Something else handles that" is not a resolution. It is the thing that becomes a surprise in week three.

### Step 4: Order the gaps

A gap is a **blocker** when nothing valid reaches the agent's input without it. Not "the agent would be better with it," and not "the agent cannot run unattended without it," because hand-feeding is usually the right first move and that looser reading would make every gap a non-blocker.

Everything else is **later**, however appealing it looks.

Blocker or later often turns on data quality rather than architecture. A loss-theme analyst needs call notes only if the loss-reason field is mostly "Other." When the call depends on data you have not looked at, mark it unknown and say what you would check, rather than guessing at a CRM you have not seen.

Blockers come first on the map, but the target agent still gets built before them whenever you can feed it by hand. That is how you test the contract without waiting on a dependency, and it means the blockers get built against a consumer you already trust.

### Step 5: Emit the spec and the map

Hand back the one sentence, the fence with resolutions, and the swarm map with its build order. The map is the deliverable people do not expect and the one they keep.

## Quality gates

- The sentence is one input clause and one output clause, with no "and" in the output half.
- The fence has at least three items.
- Every fence item resolves to a named skill, a named role, a named gap, or unverified with a named candidate. None are left open.
- Coverage claims were checked by reading the candidate, or marked unverified.
- The fence holds at least one item that is not plumbing.
- Any schedule or trigger is recorded on its own line, with what it does when there is nothing to do.
- Every gap is marked blocker or later, with the reason.
- The output says plainly when the original idea was more than one agent.
- No em dashes anywhere.

## Output (example)

```
THE JOB
  Given one role and the dated facts you have about their company,
  return one first-touch message that earns the send, or a refusal
  and the questions that would make it writable.

  Split test: output half has no "and" joining two deliverables.
  The refusal is a second state of one output, not a second output.

THE FENCE
  ITEM                            RESOLUTION        WHO OR WHAT
  find and date the signals       GAP, blocker      signal-research agent
  score how stale a signal is     GAP, later        decay-scoring agent
  pull the account list           GAP, blocker      crm-sourcing agent
  decide the altitude to aim at   COVERED           inside this agent, it
                                                    is the judgment it owns
  judge the wording               COVERED           builtgtm-voice-checker
  plan touch two                  COVERED           cadence-builder
  map the buying committee        GAP, later        multi-thread agent
  put the draft in the inbox      GAP, later        comms agent
  send it                         HUMAN             the rep, always

THE SWARM THIS IMPLIES
  BLOCKERS, build or hand-feed first
    1  crm-sourcing          accounts in, a list of accounts out
    2  signal-research       an account in, dated facts out
  THE TARGET
    3  relevance             role + dated facts in, one message out
  LATER
    4  decay-scoring         a fact in, a freshness score out
    5  comms                 a message in, a draft in the inbox out
    6  multi-thread          an account in, the committee out

VERDICT
  One agent became six, and two of them block it. Recommendation:
  build relevance now and hand-feed it facts by hand for the first
  ten runs. That tests the contract without waiting on the blockers,
  and the blockers get built against a known-good consumer.

One sharpener: point this at your skill library and the COVERED rows
resolve themselves instead of you confirming them one at a time.
```

A second run, on a reader rather than a writer, because the fence looks different and people assume that means they did it wrong.

```
THE JOB
  Given one contract PDF, return one renewal-terms row.
  Grain: one document in, one row out.

  Work test: the renewal date, the notice period and the auto-renew
  clause come from one read of one document. Splitting them would
  parse the same PDF three times and let three agents disagree about
  what it said. One output with three fields, not three agents.

THE FENCE
  ITEM                            RESOLUTION        WHO OR WHAT
  find and supply the PDFs        GAP, blocker      document-sourcing
  read a scanned or image-only    GAP, blocker      OCR step. capability
  PDF                                               gap, from question 5
  reconcile the base contract     GAP, later        amendment-chain agent
  against its amendments
  decide whether to renew or      HUMAN             the CSM
  give notice
  put the row in the tracker and  GAP, later        comms agent
  calendar the deadline
  locate and quote the clauses    OWNED             the judgment this
                                                    agent exists to make

  Not plumbing: the amendment reconciliation. That is the item that is
  specific to this job rather than true of every agent.

TRIGGER
  none. runs on demand, one document at a time.

THE SWARM THIS IMPLIES
  BLOCKERS
    1  document-sourcing   a customer in, its contract PDFs out
    2  OCR                 an image PDF in, text out, only if the
                           contracts are scans. UNKNOWN until someone
                           looks at ten real ones.
  THE TARGET
    3  terms-extractor     a PDF in, one renewal-terms row out
  LATER
    4  amendment-chain     a contract set in, the governing terms out
    5  comms               a row in, a tracker entry and a reminder out

VERDICT
  Nothing resolved to COVERED, and for a reader that is normal. A
  writing agent borrows wording and cadence helpers from the library.
  An extraction agent usually borrows nothing, so a fence of GAP plus
  HUMAN plus one OWNED row is a finished fence, not a skipped step.

One sharpener: look at ten real contracts before you decide whether
OCR is a blocker. That single check moves an agent on or off the
critical path.
```

## Example chat

Here is the skill running on a real idea, start to finish.

**You:** I want an agent that looks at our CRM, finds accounts with signals, figures out what matters, and writes the outbound.

**Claude:** That is four agents, and the sentence tells us: looks, finds, figures out, writes. Four verbs joined by "and" is four contracts.

Let me force the split before we go further. Which one is the agent you actually want to build first, meaning the one where the current output is worst?

**You:** The writing. Everything we send sounds like AI.

**Claude:** Then that is the target and the other three are its suppliers. The job:

Given one role and the dated facts you have, return one first-touch message that earns the send.

Now the fence. Five questions, and the useful ones here are two and four. What decision does it make that something else already makes, and what happens right before its input arrives?

**You:** I guess the signals come from somewhere. And we have a spreadsheet that scores how old a signal is.

**Claude:** Both are siblings, and they land differently. The signal source is a blocker, because with no dated fact there is nothing to write from. The decay spreadsheet is later, and it is worth saying why: your composer should not adjudicate freshness at all. It states the date and the rep or the decay agent decides whether that is still news. Freshness varies enough by industry that a default inside the composer would be wrong more often than right.

```
BLOCKERS   crm-sourcing, signal-research
TARGET     the composer
LATER      decay-scoring, comms, multi-thread
HUMAN      sending
```

**You:** So I cannot build the composer until the signal agent exists?

**Claude:** You can, and you should. Hand-feed it facts for the first ten runs. You are testing whether the contract is right, and a human pasting five facts tests that better than a pipeline, because when it fails you know the failure is the instructions. Then the signal agent gets built against a consumer you already trust.

One sharpener: write the handoff shape now, while both sides are in your head. Two fields and a date beats a conversation in three weeks about what "signal" meant.

## Go further

- **Point it at your library.** Connected to your skills directory, COVERED rows resolve themselves and stop being a memory test.
- **Keep the map.** The swarm map is the roadmap for the next quarter of agent work. File it next to the standard, not in a chat.
- **Re-run it when the fence leaks.** The first time someone asks the agent to do something on its fence, that is the signal a sibling is missing or the fence was wrong. Re-run rather than widen the agent.
- **Run it on agents you already shipped.** An agent with no written fence has one anyway, held in somebody's head. Write it down and see what it was quietly doing.

## Make it yours

Set where your skills and agents live so coverage resolves automatically, and set your own blocker rule if "cannot run without it" is too strict for how you sequence work. The five fence questions are the part to keep. Built by an operator. Customize it, break it, make it better.
