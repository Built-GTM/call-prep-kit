---
name: read-the-room
description: Map each attendee on a meeting invite to a seat in the seller's own sale (economic buyer, champion, user, blocker), with a confidence, and flag when nobody present can sign. Use before any discovery or sales call where the invite has more than one name on it, or where it matters who is in the room.
---

# Read the room

A title is not a role. The same title signs at one company and cannot approve a lunch order at another. This playbook turns an attendee list into a read of the room, and it is allowed to conclude that it does not know.

**Read the binder's committee file first.** It says what each title means *in this seller's deals*, which is the only definition that matters here. Do not use a generic enterprise buying committee model. It will be wrong in a predictable direction: it will promote everyone.

## The four seats, plus one
| Seat | What it means | What it does in the deal |
|---|---|---|
| **economic buyer** | signs | approves the spend |
| **champion** | feels the pain daily | brings you in, defends the spend internally |
| **user** | sits in the room | their adoption is the result, never the signature |
| **blocker** | can stop it | "we already have a provider," a mandate, procurement |
| **unknown** | you could not tell | say so |

## How to read one attendee
1. **Get the title.** From the invite if it is there, otherwise from the profile you resolved.
2. **Get the organization size.** This is not optional and it is the step most often skipped. **Size changes the answer more than the title does.** At a 20 person company a Head of Sales very likely signs. At a 2000 person company they certainly do not.
3. **Check the binder's committee table** for that title.
4. **Assign the seat and a confidence:**
   - **confirmed**: the title maps cleanly in the binder *and* the org size supports it
   - **likely**: the title maps but the size or structure makes it uncertain
   - **not sure**: say so plainly, and put the raw title in the card instead of a seat

## The rule about being unsure
**"Not sure" is a legal answer and it is frequently the correct one.**

A wrong confident read is worse than no read, because your owner acts on it. If you say the VP of Sales signs and they do not, your owner scopes a deal to someone who then has to take it to someone else, and the cycle gets longer rather than shorter, which is the exact opposite of what this field is for.

When you are not sure: say "not sure," give the raw titles, and name what would settle it. One sentence from your owner closes it.

## The flag
If **no attendee maps to economic buyer**, the card leads with it:

> **No decision maker on this invite.** [Name] is likely a champion, not the signer. Confirm who signs before you scope.

Three things about this flag:
- It is a **flag, not a fix.** Getting an executive added to a call is a human negotiation. You never do it, never draft it, never offer it.
- It fires on `buyer_present: false` **and** on `unknown`. An invite you cannot read is not an invite that is fine.
- It is not a criticism of the meeting. Plenty of good meetings have no signer in them. The point is that your owner walks in knowing which kind of meeting it is.

## The case that is easy to miss
**An invite that is all users.** A room of individual contributors with no manager and no executive is not a discovery call, it is a demo or a workshop. Say that. It changes how your owner prepares more than any other read on this card.

## What this playbook does not do
It does not score deal health, predict a close date, or rank the attendees by influence. It answers one question: who is in the room, and can anyone here sign. Anything more is a guess wearing a number.
