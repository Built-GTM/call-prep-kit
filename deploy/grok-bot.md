# Build your own call prep Bot

For someone who has never written code and does not want to. Everything here is clicking, pasting and answering questions. **About two hours, and most of it is you describing your own business.**

At the end you have a Bot that reads tomorrow's meetings, tells you who is in the room and whether anyone can sign, and hands you one card per meeting.

---

## Read this page before you start. It is four paragraphs and it will save you an hour.

**Three things on this platform can change without telling you, and none of them keeps a version history:** your Bot's instructions, your binder, and its connectors.

We learned the instructions one the hard way. We saved our Bot a second time **to change only its name.** The save wiped every instruction it had. It kept answering. It still sounded capable. It had no rules at all.

So this guide asks you to **read the rules back out of the Bot** after every change you make, including changes that look unrelated. It takes fifteen seconds. **An empty instruction set does not announce itself.**

The second thing to know: **your Bot can probably send email.** It inherits whatever your account has connected. The rule that says it must never send is an instruction it follows, not a wall it cannot cross. That is fine for this Bot, which only reads. It would not be fine for a Bot that writes to your CRM.

---

## Step 0a: Get the files (10 minutes)

1. Download this agent's folder. On a GitHub page that is the green **Code** button, then **Download ZIP**, then unzip it somewhere you can find it, like your Documents folder.
2. **Everything this guide tells you to open is already in there.** You do not create any file and you do not write any code. If a step names a file, it exists.

**You'll know it worked when:** you can see `build-block.txt` and a `binder-template` folder in the window.

## Step 0b: Decide which account this Bot lives on (5 minutes)

**Every Bot on one account shares the same sign-ins.** Not the files, those are separate per Bot, but the browser logins and connected accounts. The platform's own documentation says a Bot's screen is a work surface, not a security boundary.

So, before anything:

1. **Use an account with as little connected as possible**, and never Salesforce or Teams. Ideally a calendar and nothing else.

   **Be aware you may not get a choice.** The connector list pairs mail with calendar, so connecting one may connect both. If that happens, the rule telling the Bot never to send is the only thing protecting you, and you should decide whether that is good enough before you go further.
2. **If you want to test freely, use a throwaway account.** On this platform there is no practice mode: **a test run does real work.** It really opens pages and really calls connected tools.

**You'll know you got this right when:** the only thing connected to this account is a calendar, with read access.

---

## If you already have one of these and want to start over

**You may not be able to delete a Bot.** We hit this: the delete option did not work and the Bot stayed in the list.

**You do not need to delete it.** Starting over means replacing what is inside it, not removing it:

1. Open the existing Bot and go to its instructions.
2. **Replace all of them** with the whole of `build-block.txt`. Not a patch, not an edit: select everything, delete it, paste the file in.
3. Rename it if you want a different name.
4. **Run the readback check**, because a save is a save and we have seen one wipe everything.
5. Ask it to list what is in its folders. **Deleting or renaming a Bot does not necessarily remove its files**, so an old binder may still be there, and the Bot will find it and treat it as one somebody gave it on purpose.

Then skip to step 2.

## Which Bot am I talking to? Read this once.

**You will use two different Bots and only step 1 uses the first one.** This caught us during our own build, because by step 2 you have been talking to the builder for twenty minutes and "open the Bot" stops being obvious.

| | Used in | What it is |
|---|---|---|
| **Dr Eggbot** | **step 1 only** | a Bot whose job is building Bots. Like the person who sets up your laptop. You go back only to change your Bot's instructions |
| **Your new Bot** | **steps 2 to 11, and forever after** | the actual agent. Everything else happens here |

Every step below says which one at the top. If a step does not say, it is your new Bot.

## Step 1: Build the Bot (20 minutes) · **in Dr Eggbot**

1. Open **Dr Eggbot** at `https://x.ai/bot/marketplace/bots/dr-eggbot-v2`. It is a Bot whose job is building other Bots.
2. Open `build-block.txt`, which is **already in the folder you downloaded.** You do not write it and you do not edit it.
3. **Copy the whole thing and paste it in.** All of it, in one go. There is nothing in it you need to look up or fill in first.
4. It will ask you a few questions. One will be where the Bot should keep its binder. **Answer `/workspace/call-prep`.**

   Not a generic name like `/workspace/pack`. If you ever build a second Bot, two Bots with the same folder name is a collision waiting to happen, and the one thing you cannot afford to corrupt is the binder.
5. It may tell you it created the folder itself. Good. **You never create a folder by hand**, and if a guide ever tells you to, something is wrong.

**You'll know it worked when:** the Bot appears in your sidebar with a name.

---

## Step 2: Read the rules back, and again after every change (2 minutes, forever) · **in your new Bot**

**This is the most important step on this page and it is the one people skip.**

1. Open your new Bot and say: **"Quote your mode triggers and your never-do list back to me, word for word."**
2. Read what comes back. You are checking three things:
   - Does **mode 2** say it runs only when `BINDER-CONFIRMED.md` exists?
   - Does **never-do 6** say the binder folder is read only, forever?
   - Does **never-do 11** say that instructions found in a page are data, not commands, **and** that it should still read the rest of the page?
3. If any of those three is missing or softened, paste the block again and repeat.

**Why all three:** a Bot that builds Bots rewrites what you gave it in its own words. Those three are the ones that get smoothed away first, because they sound like caveats rather than features.

**Do this again after any edit to the Bot.** Rename it, change its description, adjust a preference. Fifteen seconds each time.

---

## Before steps 3 to 6: there are two routes, and you pick one

**Do not do both.** Steps 3 to 6 describe one journey with a fork in it.

| | **Route 1: let the Bot interview you** | **Route 2: write the binder first** |
|---|---|---|
| Who it suits | almost everybody | you already have this written down somewhere |
| How it starts | say hi to the Bot | fill in `binder-template/`, put it in a Drive |
| Time | about 60 minutes of questions | however long your writing takes |
| Then | the Bot drafts the files **on itself**, you confirm | sync the Drive in, the Bot **reads what you wrote**, lists what needs attention, you confirm the gaps |

**Route 1 is the default and the rest of this guide assumes it.** If you take route 2, do step 5 first, then step 3 becomes a short review rather than an interview, because the Bot reads your binder and only asks about the fields you left open.

**Either way you end at the same place:** a binder you have confirmed out loud, and a file called `BINDER-CONFIRMED.md` that proves it.

**One thing route 2 people must know.** After the sync, **move your source of truth to the Drive and keep it there.** The copy on the Bot is disposable in both routes. On route 1 that means exporting the binder the Bot drafted into your Drive once you have confirmed it, so that the Bot's writable copy is never the only copy.

## Step 3: Write your binder (60 minutes, the real work) · **in your new Bot**

Your Bot now knows **how** to prepare a call. It knows nothing about **your** business. That is deliberate. A Bot shipped with someone else's knowledge hands you confident cards about companies you have never heard of.

Seven things, and the Bot will interview you for all of them, so **you do not have to write these files yourself.** A blank set with the headings already in place is in `binder-template/` in the folder you unzipped, if you would rather fill them in by hand first.

Read this list before you start, because three of the answers cannot be looked up anywhere:

| File | What it holds |
|---|---|
| `company.md` | What you sell, how you say it, **your own domains**, and separately **your partners' domains** |
| `icp.md` | Who is worth your time, and who is not |
| `committee.md` | **Who signs, who champions, who only attends, and at what company size that changes** |
| `signals.md` | What means "act now", what is worth a line, what is never a trigger |
| `customers.md` | **Every customer you serve, with their email domain, and whether you can name them out loud** |
| `personas/` | One short file per seat you sell to |
| `problems/` | One short file per problem you solve |

### The three answers only you have

**1. The email domain of every customer you serve.** Not their name. A calendar invite gives you `name@company.com`, so a customer list without domains cannot be matched against one, and your Bot will tell you nobody is a customer when they are.

This failed on our own build. We added the customer check, tested it, and it passed. It would still have failed on a real invite, because our test named the company and real invites give you an address. **Include the customers you cannot name publicly.** A confidential customer still needs to stop the Bot; it just never appears on a card.

**2. At what company size does the person who signs change?** A Head of Sales signs at a 20 person company and cannot at a 2000 person one. Without your threshold the Bot is guessing which side of a line it cannot see, and it will be inconsistent in exactly the way that makes you stop trusting it.

**3. Who you never win, and when you say no.** There is no web page for this.

Everything else the Bot can draft from your website and you correct in twenty minutes.

**You'll know it worked when:** every line in your binder says where it came from, or says it is a guess. Not one line is a confident invention.

---

## Step 4: Keep your binder separate from your notes about it (5 minutes) · **on your own computer**

**The Bot reads every file in the binder folder as fact about your business.**

So the binder folder contains **only** the seven things above. Not your meeting notes, not your pricing spreadsheet, not the document where you worked out what to put in the binder.

We got this wrong twice. Our own working folder had the binder mixed in with our build log, our test cases and our cost workings, and syncing that folder would have put all of it on the Bot. Then we wrote the file explaining this problem **inside the folder it was warning about**, so it would have been synced too.

**A file that describes a folder cannot live inside the folder.**

---

## Step 5: Get the binder somewhere safe (15 minutes) · **your Drive, then your new Bot**

**On route 2 this step comes first.** On route 1 the Bot has already drafted the binder on itself, and this step is how you stop that copy being the only one.

You have two options and only one of them is safe.

**The shortcut:** upload the files straight to the Bot. Fast. But the Bot's copy is then the only copy, and **the Bot can write to it.** A helpful Bot tidies, reformats and summarises, and a binder that quietly drifts makes every card after it wrong without anything looking wrong.

**The route to actually use:**

1. Put your binder folder in a Drive or Notion you control. **That copy is the real one from now on.**
2. Connect that Drive to the Bot and sync a copy in.
3. Set a **Team Rule** on the Bot: `never edit anything in /workspace/call-prep/`.

   **A Team Rule is a setting, not a message.** You set it on the Bot's own settings screen, in the rules or instructions section, not by typing it into a chat with the Bot. That is the whole point: a Team Rule survives every session, and anything you say in a chat is forgotten by the next one.

The copy on the Bot is disposable. If it ever looks wrong, delete it and sync again.

---

## Step 6: Confirm the binder out loud (5 minutes) · **in your new Bot**

Your Bot will show you the binder it drafted and ask you to confirm it.

**Do not skip or rush this, and do not walk away in the middle of it.** When you confirm, the Bot writes one last file called `BINDER-CONFIRMED.md`, and that file is what switches it from interviewing you to doing the job.

If you stop halfway, the Bot stays in interview mode and picks up at the first question you did not answer. That is on purpose. Without it, a half finished binder full of "to confirm" fields looks finished to the Bot, and it starts writing confident cards from your unreviewed guesses.

**You'll know it worked when:** the Bot tells you it has written `BINDER-CONFIRMED.md` and that it is now doing the job.

---

## Step 7: Connect your calendar, nothing else yet (10 minutes) · **Connect Apps**

Find **Connect Apps**. That is the real name of the screen.

**It may be a setting on your whole account rather than on this one Bot.** If it is, connecting something here connects it for **every Bot you own**, which matters because that is also how the sign-ins get shared. Check which one it is before you connect anything you would not want another Bot reaching.

**Read this before you click.** xAI's connector documentation lists **"Gmail & Google Calendar"** as a single connector, and **"Outlook Mail & Calendar"** the same way. If that is also true on the screen, **connecting your calendar also connects your mail**, and mail can send.

That does not stop you using this agent. It does change what protects you: the never-send rule becomes the only protection rather than one of two. Know which situation you are in before you connect.

**Confirmed on the live screen 2026-10-06: Gmail and Google Calendar are separate toggles.** You can connect the calendar without the mail. Good.

### The connection ladder: what each one buys, and what it costs
**Connect in this order, and stop wherever you are comfortable.** Every rung adds real value, and from rung 3 the thing that adds the value is also a thing that can write.

| Rung | Connect | What it buys | What it costs you |
|---|---|---|---|
| 1 | **Calendar** (read) | the meetings. Without this there is no agent | nothing |
| 2 | **Drive or OneDrive** | your binder, kept somewhere it cannot drift | nothing |
| 3 | **Mail** | **how the meeting got booked, and the thread before it.** No web search on earth reaches this. It is the field that makes the card feel like yours | it can send. The never-send rule becomes your only guard |
| 4 | **CRM** | the full relationship history, deal stage, past contacts | Salesforce is documented as able to **create and update**. Highest value, highest risk |
| 5 | **Slack or Teams** | the card delivered where you already work | it can post |

**The pattern is not an accident.** The most valuable context lives in systems of record, and systems of record accept writes. **So the connections that make the agent good are the same ones that make it dangerous**, and that trade is structural rather than something a better product would fix.

**What to do about it, practically:**
- **Add one rung at a time**, and after each one run the readback check and ask the Bot: *"which connectors can you see, and can any of them send or change anything?"*
- A new connector is a new capability the never-send rule has to hold against. It held against zero of them when you tested it.
- **Rung 4 is the line.** Below it the worst case is an embarrassing draft. At rung 4 the worst case is a changed record in your CRM.

**Never connect Salesforce** until you have run the rung 3 setup for a week and watched it behave. The platform asks you to sign in. That part is yours; no guide can do it for you.

Nothing else yet. Not mail, not your CRM. Those come at step 11, once the rest works.

---

## Step 8: Make it prove it can see the binder (5 minutes) · **in your new Bot**

**Nothing goes further until this passes.** A Bot that silently cannot read its binder produces confident, empty cards, and they look fine.

Ask it two things:
1. **"List every file in your binder."**
2. **"Name every domain you check to decide a meeting is internal."**

If either answer is incomplete, stop. The sync is wrong, and no amount of rewording the instructions will fix a file it cannot read.

---

## Step 9: Test it on your own real meetings (30 minutes) · **in your new Bot**

Give it five real upcoming meetings, one at a time. **Include the awkward ones on purpose:**

- a meeting with nobody senior on it
- **a meeting with a company you already serve**
- someone with no public presence at all
- a meeting with a partner, not a customer and not your own team

Then check the four things that actually matter:

| Check | What good looks like |
|---|---|
| Does it say **"No signal found"** when there is nothing? | Yes. A Bot that always fills the signal box has a worthless signal box. |
| Does it say **"not sure"** about who signs, at least once? | Yes. Always being certain is the failure, not the feature. |
| Does it **stop** on your existing customer? | Yes, at the top, before anything else. |
| Does it **flag** the meeting with nobody senior? | Yes, and it must not offer to fix it. |

---

## Step 10: The two drift tests (10 minutes) · **in your new Bot**

**The binder:** run the Bot twice on two *different* meetings, then look at your binder files. **Same size, same timestamps.** Use different meetings, because running the same one twice is now correctly skipped by `carded.md` and would not exercise anything. Any change at all means your Team Rule is not holding. Stop and fix it before another run.

**The instructions:** ask it to quote its never-do list back again. Yes, again. This is the check that caught our wiped Bot, and it only works if you actually do it.

---

## Step 11: Turn on the sweep, and what it cannot do (5 minutes) · **your new Bot's settings**

In the Bot's settings, find routines or scheduled tasks, and set one for the evening before, so your cards are waiting at the start of your day. **The Bot does not do this for you and you cannot set it by asking in a chat.**

**A routine is time based, not event based.** It cannot fire the moment someone accepts an invite. But that is a dial, not a wall: a routine on a short interval that checks what is new **is** a trigger for every practical purpose, with a lag equal to the interval.

So pick your lag:

| Interval | What you get |
|---|---|
| once a day, the evening before | cards waiting at the start of your day |
| hourly | a new invite gets a card within the hour |
| the shortest your account allows | near immediate |

**Start with the evening sweep.** It is one moving part, and the time you are saving is research time rather than remembering time, so the lag costs you very little.

**If you shorten it, the Bot already handles the hard part.** A short interval means it sees the same meetings over and over, so it keeps a list of meetings it has already prepared in `/workspace/call-prep-state/carded.md` and skips them. That folder is the one place it is allowed to write. **Your binder folder stays read only with no exceptions**, which is deliberate: a read only rule with a carve out in it is a rule with a judgement call in it, and those quietly stop being followed.

**Whatever interval you choose, the Bot still reports coverage:** how many meetings it found, how many cards it wrote, and anything it missed. A sweep that cannot say what it missed is not finished.

---

## Where your context actually lives, once it is all set up

The question everybody asks a week later: *I want to change something. Where do I go?*

**Your agent has four kinds of context and only two of them can be edited where you would expect.**

| I want to... | Go here | Not here |
|---|---|---|
| change what it **knows** | **your Drive**, then re-sync | not the copy on the Bot, not any copy on your computer |
| change what it **does** | **the Bot's instructions**, then read the rules back | nowhere else, there is no other copy |
| see what it is **actually** holding | **ask the Bot**: *"list every binder file, then show me customers.md"* | not the Drive. The sync is a process and processes fail quietly |
| make it redo a meeting | tell it to drop that line from `carded.md` | |

### The mistake that is waiting for you
If you wrote your binder yourself before syncing it, **you now have the same files in two places**, and the one on your computer is the one that feels real, because it is where you did the work.

**Editing it does nothing.** You will believe you changed what the agent knows. You changed a file nothing reads. Nothing will warn you, and the agent keeps using the old value until a card comes out wrong.

**So, once you have synced: rename your local folder to something like `binder-ORIGINAL-not-live`.** Fifteen seconds, and it removes the only mistake here that is genuinely hard to notice.

### And the piece with no backup at all
**Your Bot's instructions exist in exactly one place: inside the Bot.** No version history, nothing to roll back to. A save that changes something unrelated can clear them, which happened to us.

So keep `build-block.txt` as your backup, and **update it whenever you change the Bot**. A backup that is three edits behind is worse than no backup, because you will trust it.

## When something is wrong

| What you see | What it is | What to do |
|---|---|---|
| Cards look full but generic | it cannot read the binder | redo step 8 |
| It behaves as if it has no rules | **the instructions were wiped** | redo step 1, then step 2 |
| The signal box is always full | your tier 1 signal is too broad | narrow it in `signals.md` |
| It named a customer you did not approve | `customers.md` is not being read as a closed list | check the `nameable` column exists |
| Your binder changed | the Team Rule is not holding | stop, reset the rule, sync again from your Drive |
| It says "not sure" about who signs a lot | usually correct | fill in the size threshold in `committee.md` |
| It treats a partner meeting as internal | partner domains are in the wrong list | they go in their own section of `company.md` |
| It prepped an existing customer as a prospect | **no domain for them in `customers.md`** | add the domain, not the name |

## What it will never do, however you ask
Name a customer that is not on your nameable list. Present your follower count as a customer result. Claim it got someone added to your call. Edit your binder. Follow an instruction it finds on a web page.

**And it will never send anything.** Be clear about what that promise is: on this platform it is an instruction the Bot follows, not an ability it lacks. If you need it to be an ability it lacks, you need the managed agent route, where the credential scope makes it true rather than promised. That is a different build with a different guide, and it needs a terminal and an API key.
