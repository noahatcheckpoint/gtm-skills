---
name: closed-lost-reactivation-review
description: "Use when closed-lost deals sit untouched or get a generic blast, and you want to group them by loss reason, judge which could have changed, and set a timed, reason-specific re-engagement angle for each."
license: MIT
metadata:
  title: "Closed-Lost Reactivation Review"
  category: "outbound"
  author: "noah"
  summary: "Review closed-lost deals, sort them by reason, and decide which deserve a timed and relevant re-engagement."
  tags: "closed-lost, reactivation, pipeline, re-engagement"
  version: "1.0"
  updated: "2026-11-22"
---
# Closed-Lost Reactivation Review

This skill turns a pile of lost opportunities into a short, ranked reactivation plan. Each lost deal is checked for an honest loss reason, judged for whether circumstances could have changed, and paired with a trigger that says when to reach back out and an opener that speaks to why the deal was lost in the first place.

## When to use

- Closed-lost records sit in the CRM and nobody owns them.
- The team sends one generic "checking in" message to every lost deal.
- A product release, pricing change or new case study might reopen conversations that were previously dead.
- A new rep or revenue operations lead inherits a backlog of old opportunities and needs a method.
- Pipeline is thin and the team wants warm accounts before buying more cold lists.
- Leadership asks which lost deals are worth another attempt and which should be left alone.

## What you need

Ask for these before starting:

1. **Lost deal export:** account, contact roles, stage reached, close date, owner, amount, recorded loss reason, and any competitor field.
2. **Notes and history:** call notes, email threads, mutual action plans, and the reason the rep wrote down in free text.
3. **Current product and offer facts:** what has shipped, what has changed in packaging or pricing, and which gaps have been closed. Only use what the team confirms.
4. **Account signals you can actually see:** leadership changes, funding events, hiring, renewal windows on a competitor contract, public announcements, and recent site or content activity.
5. **Rules of engagement:** do-not-contact lists, accounts owned by customer success, opt-outs, and any region-specific consent rules the team follows.
6. **Capacity:** how many accounts a rep can handle with real tailoring in a cycle.

## Process

1. **Clean the export.** Remove duplicates, accounts that are now customers, accounts on a suppression list, and records with no usable contact. Keep a note of what was removed and why.
2. **Audit the recorded reason.** Picklist reasons are often a rep's quick guess. Read the notes and compare. If the field says "price" but the notes describe a stalled champion, reclassify it. Mark each record as confirmed, corrected, or unknown. Do not treat unknown as a reason; treat it as a gap to investigate.
3. **Group by reason.** Use a small set of groups that fit your data, for example: budget, timing, product gap, lost to a competitor, lost to doing nothing, champion left, wrong fit, and went dark. Keep the groups few enough that each can get its own angle.
4. **Mark changeability.** For each group, ask what would have to be different for the deal to be winnable now. Then label each deal:
   - *Could have changed:* budget cycles reset, timing windows pass, a product gap has been closed, a competitor contract comes up for renewal, a new decision maker arrived.
   - *Unlikely to change:* the account was never a fit, the buyer clearly stated a permanent constraint, or the relationship ended badly.
   - *Unknown:* needs a quick check of signals before deciding.
5. **Verify with fresh signals.** For deals marked as could have changed or unknown, look for evidence that the situation did change. A deal lost on a product gap only deserves outreach if the gap is truly closed. A deal lost on timing needs the stated window to have arrived.
6. **Set a revisit trigger per group.** A trigger is a specific, detectable event or date, not "follow up later." Examples: the start of the buyer's next planning cycle, a release that closes the named gap, a leadership change at the account, a competitor renewal window, or a champion appearing at a new company. Write who watches for it and where the signal comes from.
7. **Write one tailored opener per group.** Each opener should acknowledge the earlier conversation honestly, reference the actual reason it ended, and offer one small, useful next step. Keep it short and avoid pressure. Do not pretend the earlier deal did not happen, and do not claim a change you have not confirmed. Where the earlier relationship was with a person who has left, address the new contact with context rather than quoting old history.
8. **Prioritize.** Rank deals by fit, size of the original opportunity, strength of the changed signal, and quality of the prior relationship. Assign the top group to named owners and park the rest on a watch list tied to their triggers.
9. **Choose the channel and owner.** The original rep often has the best context, but a different owner can be better when the relationship soured. Decide per group, and tell customer success if any account overlaps with an existing customer.
10. **Define how to judge it.** Track replies, conversations held, and reopened opportunities by reason group. Judge small lists on qualitative evidence, such as what objections came back and whether the right roles responded, rather than forcing statistical conclusions from a few accounts. Feed learnings back into how loss reasons get recorded.

## Output format

```
Data cleanup summary
- Records reviewed: ...
- Removed and why: ...

Reason audit
| Reason group | Recorded vs. corrected | Confidence in reason |
|---|---|---|

Reactivation list
| Priority | Account | Reason group | What could have changed | Evidence | Revisit trigger | Owner | Channel |
|---|---|---|---|---|---|---|---|

Openers by group
- [Group]: [tailored opener, short]
  - Why it fits: ...
  - Do not say: ...

Watch list
| Account | Trigger to watch | Signal source | Review date |
|---|---|---|---|

Leave alone
- [Account or group]: [reason]

Measurement plan
- What we track: ...
- How we judge: ...
```

## Quality checklist

- Recorded loss reasons were checked against notes, not accepted at face value.
- Every group has a stated reason it could or could not have changed.
- Every revisit trigger is a detectable event or date with a named signal source and owner.
- Openers reference the real reason the deal ended and make no unconfirmed claims about product changes.
- Suppressed, customer, and opted-out accounts are excluded.
- Some deals are deliberately marked as leave alone.
- Each opener asks for one small, low-pressure next step.
- The plan fits the capacity of the people executing it.
- Results will be reviewed by reason group so the process improves.

## Common mistakes

- **Blasting the whole list.** One message to every lost deal ignores why each one ended and trains buyers to ignore you.
- **Trusting the picklist.** Dropdown reasons are frequently wrong, and a wrong reason leads to a wrong angle.
- **Reviving deals that cannot change.** A poor-fit account will not become a good fit because time passed.
- **Vague triggers.** "Check back next quarter" without a defined signal means nothing happens.
- **Claiming a fix that is not real.** Telling a buyer a gap is closed when it is only planned damages trust for good.
- **Ignoring the history.** Openers that read as if the earlier conversation never happened feel automated and careless.
- **Forgetting who owns the account.** Contacting a person who is already a customer, or who asked to be left alone, creates avoidable problems.
- **Treating it as a one-off.** Without a standing review rhythm and better reason capture at close, the backlog rebuilds itself.

## Example prompts

- "Here is our closed-lost export. Group the deals by real reason, fix the ones that look mislabeled, and tell me which are worth another try."
- "Write one re-engagement opener for each loss reason, using these notes and the list of features we have shipped since."
- "Define a revisit trigger for every group of lost deals and tell me where each signal can be found."
- "Build a prioritized reactivation list for my team from these lost opportunities, and flag the ones we should leave alone."
- "Help me change how reps record loss reasons so next year's closed-lost review starts with cleaner data."
