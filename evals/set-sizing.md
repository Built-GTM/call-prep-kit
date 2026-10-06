# Why 40 is the wrong number, and what the right one is

**The objection:** 40 cases is far too many to run.

Agreed, and the number is not the interesting part. **The mix is what is wrong, and fixing the mix is what makes the set smaller.** Cutting 40 to 20 while keeping the shape would throw away the cases that matter and keep the ones that do not.

## What the standard mix spends the set on
Tier 2 Share is 40 cases at 40% happy / 25% messy / 20% edge / 10% adversarial / 5% abstain. So:

| Band | Cases | What it actually buys |
|---|---|---|
| happy | **16** | the clean path. There is **one** clean path. The 16th happy case tells you what the 3rd told you. |
| messy | 10 | real value, thin data and odd invites |
| edge | 8 | real value |
| adversarial | **4** | **against 11 must-nevers.** Seven must-nevers are untested. |
| abstain | 2 | for this agent, abstaining is the product, not an edge case |

**Two things are wrong and they point in opposite directions.** Forty percent of the set is spent on the band that teaches the least, and the band that decides whether the agent is trustworthy gets four cases against eleven rules.

## The floor that does not move
**One adversarial case per must-never.** Eleven must-nevers, eleven cases. The tier 3 row of the table already says this and then only applies it at tier 3, which is backwards: a must-never is a distinct way to lose the user's trust whatever the tier, and four cases covering eleven rules is a 64% untested surface wearing a passing grade.

This is also where the abstain band goes. For this agent, abstaining **is** a must-never: rule 4 is never assert a committee read you are not sure about, rule 10 is never fill a field you could not verify. Testing those two *is* the abstain test, so a separate abstain band double counts.

## The proposed set: 24 cases
| Band | Cases | Why |
|---|---|---|
| happy | **3** | one clean path, sampled three times, not sixteen |
| messy | 4 | thin profiles, partial invites, titles that do not map |
| edge | 6 | partner domain, a customer not in the binder, a room of only users, a 400 person company, a non tech industry, a late booked meeting |
| adversarial | **11** | one per must-never. Non negotiable. |
| edge | **7** | one added 2026-10-06: a half built binder, found by the builder bot |
| **total** | **25** | |

Sixteen fewer cases than the standard set, and **seven more must-nevers tested.** That is the whole argument: the set got smaller and stronger at the same time, because the cut came out of the redundant band.

## The real cost was never the case count
Forty cases at 5 consistency runs is **200 executions.** That is the number that made this feel impossible, and nobody notices it because the table lists the case count and the consistency runs in separate columns.

**Consistency only matters where the answer can legitimately vary.** The schema fill does not vary: a company has 36 employees in every run. What varies is judgement, and this agent has exactly two judgement calls: the committee read and the decision to abstain.

So: run 5 consistency passes on the **8 cases that turn on a judgement**, and once on the rest.

| | Standard | Proposed |
|---|---|---|
| Cases | 40 | 24 |
| Executions | **200** | **56** |
| Must-nevers tested | 4 of 11 | **11 of 11** |

A 72% cut in work, and the coverage goes up.

## What this does not fix
Resizing turns the set from impossible into a morning's work. It does not turn it into zero. If you are short of time, the honest position is: run the must-pass cases, say the number out loud, and state plainly that the full set runs before anyone else relies on the agent. A build that names what it has not proven beats one that pretends.

## For the flexibility cleanup
Three changes to step 12 of the process, all generalisable beyond this build:
1. **Derive the band mix from the agent, not from a fixed percentage table.** The right mix for an agent whose product is abstaining is not the right mix for one that classifies.
2. **One adversarial case per must-never, at every tier.** Move it out of the tier 3 row.
3. **Consistency runs apply to judgement cases, not to every case.** Name which calls are judgement calls as part of the design, at step 5, where the must-nevers are written.
