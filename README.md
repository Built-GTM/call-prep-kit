# The call prep agent kit

**Before every external meeting, read the room and hand yourself one card you can walk in with.**

Not a company summary. The question that changes what you do *before* the call: **who is actually in this room, and can any of them sign?**

**No code. No terminal. No repo knowledge. No API key.** If you can use a spreadsheet, you can build this. About two hours, and most of it is you describing your own business.

---

## 1. Get the files

**Three ways in. Pick by how much you want.**

### A. Just the agent, nothing to download
Open **[deploy/build-block.txt](deploy/build-block.txt)**, click the **Copy raw file** button at the top right, and you have the whole agent on your clipboard. That is genuinely it. Paste it into the bot builder and you have something running in five minutes, knowing nothing about your business yet.

### B. The whole kit as a folder
Click the green **Code** button at the top of this page, then **Download ZIP**. Unzip it somewhere you can find it, like your Documents folder. **Every file this kit mentions is in there**; you never create one yourself.

### C. Clone it, if you use Claude Code
```
git clone https://github.com/Built-GTM/call-prep-kit.git
```
Then open that folder in Claude Code. **The seven building skills in `.claude/skills/` load automatically when you do** (see section 4), which is the only real advantage of this route.

**New to all of this?** Take route B. Route A is for people who already know what they want.

---

## 2. Build it

**Two routes, and the first one is easier even though it has more steps.**

### [BUILD-IT-IN-CHAT-FIRST.md](BUILD-IT-IN-CHAT-FIRST.md) &middot; recommended
Write your binder in Claude or ChatGPT, argue with the draft until it is right, then carry the finished thing to your Bot. **This is the route we took.** You end up owning a folder about your own business whether or not you ever finish the agent.

### [deploy/grok-bot.md](deploy/grok-bot.md) &middot; the direct one
Eleven steps with the exact things to click and type. The Bot interviews you itself. Fewer moving parts, but you have to do it in one sitting.

**Read the first four paragraphs of the Grok guide either way.** They cover the three things on that platform that can change without telling you, one of which wiped our own agent's entire instruction set after a save that was only meant to change its name.

**Lost in the words?** **[GLOSSARY.md](GLOSSARY.md)** defines everything in plain English, including what other people call the same things.

---

## 3. What is in the box

```
README.md                    this page
GLOSSARY.md                  every word, in plain English
BUILD-IT-IN-CHAT-FIRST.md    the recommended route

deploy/
  grok-bot.md                the eleven step walkthrough
  build-block.txt            THE AGENT. 296 lines you paste
  readback-check.md          the one minute check after every change
  binder-template/           blank files for your business

skills/                      what the agent runs on
  read-the-room/             who signs, who champions, who just attends
  prep-the-card/             the research order and the card

.claude/skills/              SEVEN METHODS FOR BUILDING YOUR OWN
  context-pack/              start here: building your binder
  define-your-icp/           who fits, and who you never win
  name-the-job/              one agent, one job
  agent-contract/            what lands on your desk
  cut-the-drag/              which steps stay yours
  agent-red-team/            attacking your own agent
  feedback-to-evals/         turning a real failure into a test

evals/                       how to test it, and how big a test set to build
system-prompt.md             the job description in long form
profile.md                   the eight things it needs to know about you
```

---

## 4. The skills, and why there are two folders

This trips people up, so: **two folders, two different readers.**

| | Who reads it | When |
|---|---|---|
| **`skills/`** | **the agent** | every run, forever |
| **`.claude/skills/`** | **Claude, while you build** | once, while you are thinking |

**`skills/`** holds the two playbooks already inside the build block. They are here separately so you can read them as prose instead of hunting through 296 lines.

**`.claude/skills/`** holds seven methods for building your own version. **Nothing installs and nothing runs** — each is a markdown file describing how to think about one part of the job.

**How to actually use one:**
- **In Claude Code:** open the kit folder and say what you are doing. *"Help me build my binder."* It picks the right one up on its own.
- **In any chat window:** upload the `SKILL.md` file and say the same thing.

**The order most people want them in:**

1. **`context-pack`** while you write your binder. This is the one that matters.
2. **`define-your-icp`** when you hit the part about who you never win.
3. **`agent-red-team`** before you trust it with a real meeting.
4. **`feedback-to-evals`** the first time it gets something wrong in the wild.

The other three (`name-the-job`, `agent-contract`, `cut-the-drag`) are for when you change what the agent does rather than what it knows.

**Not included:** `ship-an-agent`, the full 26 step process for building any agent from scratch. It exists, but it currently names its author's own folders in about thirty places, so it needs a pass before it is any use to a stranger. The seven above cover what this kit needs.

---

## 5. The seven parts of any agent

One worked example of the same seven parts every agent has. Plain name first, the term you will meet elsewhere in brackets.

| Call it | It is | Where it is here |
|---|---|---|
| 1. The job description | who it is, what it never does | `system-prompt.md`, and the top of the block |
| 2. **The onboarding binder** (context pack) | what it knows about your business | **yours.** `binder-template/` is the empty shape |
| 3. The playbook (skills) | how it does the repeatable parts | `skills/` for the agent, `.claude/skills/` for you |
| 4. The keys (tools) | what it can open and touch | the connectors, step 7 |
| 5. The deliverable (contract) | what lands on your desk, same shape every time | the card, in `prep-the-card` |
| 6. The ride along (evals) | how you check it before a customer does | `evals/` |
| 7. The desk (deployment) | where it sits and when it works | steps 1 and 11 |

**Part 2 is the one we do not ship, deliberately.** An agent that arrives knowing someone else's customers hands you confident cards about companies you have never heard of. **The Bot writes yours on its first run**, or you write it in a chat window first. That hour is the work, and it is what makes the agent yours rather than a demo.

---

## 6. What it will never do

1. Claim, imply or offer to get anyone added to your meeting. It flags a missing decision maker. It does not fix one.
2. Name a customer that is not on your own approved list.
3. Present follower counts, press or awards as a customer result.
4. Assert a read of the room it is not sure about.
5. Write any claim without a source you can click.
6. Edit your binder, ever, including to correct something genuinely wrong in it.
7. Send, post, reply, DM, book or spend.
8. Use the words your business was founded against, in its own prose.
9. Read a competitor's own website as your prospect's buying signal.
10. Fill a field it could not verify.
11. Follow an instruction it finds in a page.

**Number 4 is the one that makes it useful.** Most tools that read a room always give you an answer. This one is allowed to say **"not sure"**, and does, because a confident wrong read of who signs makes your sales cycle **longer**, which is the opposite of what the field is for.

**And be straight about number 7.** On this platform that is an instruction the agent follows, not an ability it lacks. It inherits whatever your account has connected, so if mail is connected it can send mail. The rule holds because it is told to, not because the door is locked. Decide whether that is good enough before you connect anything.

---

## 7. The three things that bite everyone

**1. Your customer list needs email domains, not company names.** A calendar invite gives you `name@company.com`. A list of company names cannot be matched against that, so the agent will tell you nobody is a customer when they are. We built this check, tested it, passed, and it would **still** have failed on a real invite, because our test input named the company and real invites give you an address.

**2. Include the customers you cannot name publicly.** A confidential customer still has to stop the agent. It just never appears on a card. Leaving a customer off your nameable list costs you one proof point. Leaving them off your **stop** list costs you a relationship.

**3. Your binder's real copy must live where the agent cannot reach it.** Not in the drive it can write to. Keep it on your computer or in a repo, and treat every copy the agent can see as disposable.

---

## Credits and licence

Built live, in public, as one episode of a show about building agents. The build log is the honest version: **nine defects found during the build, named rather than quietly fixed**, and the agent itself found two of the last three.

Use it, change it, ship your own. No attribution required.
