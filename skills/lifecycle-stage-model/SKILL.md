---
name: lifecycle-stage-model
description: Designs a lifecycle stage model for contacts and accounts, from first touch to customer and advocate, with entry rules, owners, exit paths and recycling. Use when funnel reports disagree, when MQL and SQL mean different things to different teams, or when setting up or rebuilding a CRM.
license: MIT
metadata:
  title: "Lifecycle Stage Model"
  category: "revops-crm"
  author: "esther"
  summary: "Define every lifecycle stage from subscriber to advocate with entry rules, owners and recycle paths so funnel numbers mean one thing."
  tags: "lifecycle stages, MQL, SQL, funnel definitions, CRM governance"
  version: "1.0"
  updated: "2026-10-19"
---
# Lifecycle Stage Model

Produces a written lifecycle model that every team can point to: each stage has a plain definition, an observable entry trigger, a single owning team, and a defined way out (forward, back to nurture, or disqualified). The result is a funnel whose conversion rates can be trusted.

## When to use

- Marketing reports 400 MQLs and sales says it received 90 real leads.
- The CRM has a lifecycle field, but stages are set by hand, skipped, or never move backwards.
- You are launching a new CRM, a new segment, or a product-led motion and need stages that fit it.
- Board or leadership metrics (lead to customer rate, pipeline sourced) are being questioned.

Not the right tool for deal stages inside an opportunity. Lifecycle describes the relationship with a person or account; the deal pipeline describes one buying process. Use the pipeline stage skill for that.

## What you need

Ask for anything missing before drafting:

1. **Motion:** sales-led, product-led, or hybrid; inbound, outbound, or both.
2. **Unit of record:** do you track lifecycle on contacts, accounts, or both? (B2B teams selling to buying groups usually need both.)
3. **Current stages** and how they are set today (manual, workflow, score threshold).
4. **Teams and handoffs:** who works a lead first (marketing, SDR, AE, CS) and where ownership changes.
5. **Volumes:** rough monthly counts at each current stage, if known.
6. **Known pain:** the argument people keep having about the funnel.

If the user has none of this, offer a default B2B model and mark every assumption.

## Process

1. **Separate three concepts that teams conflate.** Lifecycle stage (where the relationship is), lead status (what a rep is doing with it right now: new, attempting, connected, nurturing, disqualified), and deal stage (where a specific opportunity is). Most broken models jam all three into one field.
2. **Pick the minimum number of stages.** Every stage must answer "who owns it and what do they do next?" If two stages share an owner and an action, merge them. A typical B2B set:
   - Subscriber: opted into content, no buying signal.
   - Lead: known contact with enough data to evaluate.
   - Marketing qualified (MQL): meets agreed fit and intent thresholds.
   - Sales accepted (SAL): a rep reviewed it and agrees it deserves outreach.
   - Sales qualified (SQL): a conversation confirmed a real need and a path to buy.
   - Opportunity: a deal record exists with an amount and close date.
   - Customer: closed won.
   - Advocate (optional): referenceable, referring, or reviewing.
   - Product-led motions add **Product qualified (PQL)**: a user hit an activation or usage threshold.
3. **Write entry triggers as events, not opinions.** "Requested a demo," "fit score at least B and 3 engagement actions in 30 days," "rep logged a connected call with pain confirmed." Avoid "seems interested."
4. **Assign one owning team per stage** and the action expected within a time window. This becomes the backbone of the sales and marketing SLA.
5. **Define every exit.** Forward, recycle to nurture (with a reason code), or disqualify (with a reason code). Decide who may move a record backwards and when. A model that only moves forward inflates every stage over time.
6. **Decide account versus contact roll-up.** Common rule: account stage equals the most advanced contact stage, except Customer, which is set at account level only when a deal closes.
7. **Add timestamps.** Every stage needs a "date entered" field, never overwritten. Without it, velocity and cohort conversion are impossible.
8. **Set guardrails.** No skipping from Lead straight to Customer without a deal; Customer cannot be set manually; disqualification requires a reason.
9. **Define the metrics the model enables:** stage to stage conversion by cohort month, median days in stage, recycle rate, and disqualification reasons.
10. **Plan the migration.** Map every old value to a new one, decide how to backfill dates, and pick a cutover date after which reports use only the new model.

## Output format

```
# Lifecycle Stage Model: [Company / Segment]
Motion: [sales-led / product-led / hybrid]   Unit: [contact / account / both]

## Stage definitions
| Stage | Definition | Entry trigger (event) | Owner | Expected action and window | Exits |
|---|---|---|---|---|---|
| Lead | ... | ... | Marketing | ... | MQL / Nurture / Disqualified |

## Lead status values (separate field)
[list with one line each]

## Recycle and disqualification reasons
| Code | Meaning | Returns to | Re-entry rule |

## Roll-up rules (contact to account)
[rules]

## Guardrails
[bullets]

## Required fields and timestamps
[field list per stage]

## Metrics this model enables
[metric, formula, where it is reported]

## Migration map
| Old value | New stage | Backfill method |

## Assumptions and open questions
```

## Quality checklist

- Every stage has exactly one owner and one expected action.
- Entry triggers are observable events or thresholds anyone could audit.
- Lifecycle, lead status, and deal stage are three separate fields.
- Every stage has a backward or exit path with reason codes.
- "Date entered" timestamps exist for every stage and are never overwritten.
- Customer is set by a closed won deal, not by hand.
- Stage count is the minimum that still separates distinct owners and actions.
- Assumptions are labelled, not hidden.

## Common mistakes

- **Using lifecycle stage as a to-do list.** "Attempting contact" is a status, not a stage. Mixing them makes conversion rates meaningless.
- **One-way models.** Nobody ever goes back to nurture, so the SQL bucket fills with dead leads and the conversion rate drifts down quarter after quarter.
- **MQL defined by score alone.** A high activity score from a student or a competitor is not qualified. Fit has to gate intent.
- **No SAL step when the handoff is contested.** Without an explicit acceptance moment, sales and marketing argue about leads that were never looked at.
- **Overwriting dates.** Re-entering a stage and stamping a new date erases the history you need for cohort analysis. Keep first-entered and last-entered separately if records can cycle.
- **Designing for the CRM's default picklist** instead of for your handoffs. Default stages are a starting point, not a model.
- **Too many stages.** Twelve stages means nobody sets them correctly. If a stage has no unique owner or action, cut it.

## Example prompts

- "Design a lifecycle stage model for our B2B SaaS. We have inbound demo requests, a free trial, and an SDR team."
- "Marketing and sales disagree on what an MQL is. Help me write stage definitions both can sign."
- "We sell to buying committees. How should lifecycle work at contact versus account level?"
- "Map our current eleven lifecycle values to a cleaner model and give me a migration plan."
- "Add a product qualified lead stage to our existing funnel without breaking reporting."
