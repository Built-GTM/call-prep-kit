# Skills, and which folder they live in

Two folders, two audiences. The difference matters because one of them is read by a machine and the other is read by you.

| | Who reads it | What it does |
|---|---|---|
| **`skills/`** | **the agent** | how it does the job, every run |
| **`.claude/skills/`** | **Claude, while you build** | how *you* think the job through |

## `skills/` &middot; what the agent runs on

Two files, and they are inside the build block already. They are here separately so you can read them as prose rather than hunting through 296 lines.

- **`read-the-room`** &middot; turn an attendee list into a read of who signs, who champions, who just attends, **with permission to answer "not sure"**
- **`prep-the-card`** &middot; the research order, and the fixed shape of the card

## `.claude/skills/` &middot; what helps you build your own

**Open this folder in Claude Code, or upload a skill to any chat, and ask for what you need.** Each one is a method, not a script.

| Skill | Use it when |
|---|---|
| **`context-pack`** | **Start here.** Building your binder: what goes in it, what to leave out |
| `define-your-icp` | Filling in `icp.md`, including the part about who you do not win |
| `name-the-job` | Your version does something different and you need one clear job |
| `agent-contract` | Changing the card. What lands on your desk and what it must never say |
| `cut-the-drag` | Deciding which steps stay yours and where the checkpoint sits |
| `agent-red-team` | Before you trust it. Attacking your own agent on purpose |
| `feedback-to-evals` | After a real failure. Turning it into a test so it cannot happen twice |

**The order most people need them in:** `context-pack` while writing the binder, `agent-red-team` before going live, `feedback-to-evals` the first time it gets something wrong in the wild.

## How to actually use one
In Claude Code, open this folder and say what you are doing: *"help me build my binder."* It picks up the right skill.

In a chat window, upload the `SKILL.md` and say the same thing.

**Neither needs any setup.** They are plain markdown describing a method. Nothing installs, nothing runs.

## What is not here yet
**`ship-an-agent`**, the full 26 step process for building any agent from scratch rather than adapting this one. It exists and it works, but it currently names its author's own folders in about thirty places, so it needs a pass before it is useful to anyone else. **The parts of it you need for this kit are the seven skills above.**
