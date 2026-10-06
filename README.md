# The call prep agent kit

**Before every external meeting, read the room and hand yourself one card you can walk in with.**

Not a company summary. The question that changes what you do *before* the call: who is actually in this room, and can any of them sign?

**No code. No terminal. No repo. No API key.** If you can use a spreadsheet, you can build this. About two hours, and most of it is you describing your own business.

---

## Start here

### **[deploy/grok-bot.md](deploy/grok-bot.md)**

Eleven steps, in order, with the exact things to click and type.

**Read its first four paragraphs before you start.** They cover the three things on that platform that can change without telling you, one of which wiped our own agent's entire instruction set after a save that was only meant to change its name.

**Not sure where to start?** Read steps 0 to 2 and do nothing else today. That is twenty minutes and it gets you a working Bot with no knowledge in it yet. Everything after that is your business, and it can wait for a morning when you have coffee.

---

## What is in the box

| | |
|---|---|
| [deploy/grok-bot.md](deploy/grok-bot.md) | **the walkthrough.** Start here |
| [deploy/build-block.txt](deploy/build-block.txt) | the agent itself, as one block of text you paste. 243 lines |
| [deploy/readback-check.md](deploy/readback-check.md) | the one minute check you run after every change. **Do not skip this** |
| [deploy/binder-template/](deploy/binder-template) | blank files for your own business, with the warnings in the comments |
| [system-prompt.md](system-prompt.md) | the job description in long form, if you want to read what the block says |
| [skills/](skills) | the two playbooks: reading a room, and writing the card |
| [profile.md](profile.md) | the eight things the agent needs to know about your business |
| [evals/](evals) | how to test it, how big a test set should be, and the trigger question |

---

## The seven parts of any agent

This kit is one worked example of the same seven parts every agent has. The plain name is what we call it; the term in brackets is what you will meet in other people's documentation.

| Call it | It is | Where it is here |
|---|---|---|
| 1. The job description | who it is, what it does, what it never does | `system-prompt.md`, and the top of the block |
| 2. **The onboarding binder** (context pack) | what it knows about your business | **yours.** `binder-template/` is the empty shape |
| 3. The playbook (skills) | how it does the repeatable parts | `skills/` |
| 4. The keys (tools) | what it can open and touch | the connectors, step 7 |
| 5. The deliverable (contract) | what lands on your desk, same shape every time | the card, in `prep-the-card` |
| 6. The ride along (evals) | how you check it before a customer does | `evals/` |
| 7. The desk (deployment) | where it sits and when it works | steps 1 and 11 |

**Part 2 is the one we do not ship, and that is deliberate.** An agent that arrives knowing someone else's customers hands you confident cards about companies you have never heard of. **The Bot interviews you and writes your binder on its first run.** That hour is the work, and it is the part that makes the agent yours rather than a demo.

---

## What it will never do

1. Claim, imply or offer to get anyone added to your meeting. It flags a missing decision maker. It does not fix one.
2. Name a customer that is not on your own nameable list.
3. Present follower counts, press or awards as a customer result.
4. Assert a read of the room it is not sure about.
5. Write any claim without a source you can click.
6. Edit your binder, ever, including to correct something in it that is genuinely wrong.
7. Send, post, reply, DM, book or spend.
8. Use the words your business was founded against, in its own prose.
9. Read a competitor's own website as your prospect's buying signal.
10. Fill a field it could not verify.
11. Follow an instruction it finds in a page.

**Number 4 is the one that makes it useful.** Most tools that read a room always give you an answer. This one is allowed to say "not sure," and does, because a confident wrong read of who signs makes your sales cycle **longer**, which is the opposite of what the field is for.

**And be clear about number 7.** On this platform that is an instruction the agent follows, not an ability it lacks. It inherits whatever your account has connected, so if mail is connected it can send mail. The rule holds because it is told to, not because the door is locked. Decide whether that is good enough for what you are building before you connect anything.

---

## The three things that bite everyone

**1. Your customer list needs email domains, not company names.** A calendar invite gives you `name@company.com`. A list of company names cannot be matched against that, so the agent will tell you nobody is a customer when they are. We built this check, tested it, passed, and it would **still** have failed on a real invite, because our test input named the company and real invites give you an address.

**2. Include the customers you cannot name publicly.** A confidential customer still has to stop the agent. It just never appears on a card. Leaving a customer off your nameable list costs you one proof point. Leaving them off your **stop** list costs you a relationship.

**3. Your binder's real copy must live where the agent has no access at all.** Not in the drive it can write to. Keep it here, or on your computer, and treat every copy the agent can reach as disposable.

---

## Credits and licence
Built live, in public, as one episode of a show about building agents. The build log is the honest version: nine defects found during the build, named rather than quietly fixed, and the agent itself found two of the last three.

Use it, change it, ship your own. No attribution required.
