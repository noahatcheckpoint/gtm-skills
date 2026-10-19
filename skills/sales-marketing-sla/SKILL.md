---
name: sales-marketing-sla
description: Drafts a two-way service level agreement between marketing and sales (and optionally SDRs and customer success): lead definitions, volume commitments, response times by lead type, follow-up effort, acceptance and rejection rules, recycling, reporting and an escalation path. Use when leads go unworked, when marketing and sales blame each other, or when launching a new handoff.
license: MIT
metadata:
  title: "Sales and Marketing SLA"
  category: "revops-crm"
  author: "esther"
  summary: "Write a two-way SLA with lead definitions, response times, follow-up effort, rejection rules and a shared scorecard both teams sign."
  tags: "SLA, sales and marketing alignment, lead handoff, MQL follow-up, RevOps"
  version: "1.0"
  updated: "2026-10-19"
---
# Sales and Marketing SLA

Produces a short agreement both leaders can sign: what marketing delivers, what sales does with it, how fast, how hard, what happens to leads that are rejected, and how compliance is reported. It turns a recurring argument into a scorecard.

## When to use

- Marketing says sales ignores leads; sales says the leads are bad.
- High-intent requests wait a day or more for a first response.
- Leads are rejected or abandoned without any reason recorded.
- A new SDR team, segment, or lead source is being introduced.
- Pipeline targets are shared between teams but nobody owns the handoff.

## What you need

Ask for these first:

1. **Lifecycle definitions** in use (MQL, SAL, SQL), or permission to propose them.
2. **Lead types and volumes:** demo requests, trials, content leads, event leads, partner referrals, per month.
3. **Team capacity:** reps or SDRs working inbound and how many leads each can handle per week.
4. **Current response data:** median time to first touch and number of attempts, if known.
5. **Targets:** pipeline or revenue goals and the share expected from marketing.
6. **Pain points:** the specific complaints from each side.

## Process

1. **Agree definitions first.** The SLA rests on a shared meaning of a qualified lead. Write the MQL criteria (fit plus intent), what sales acceptance means, and what an SQL is. If these do not exist, draft them and mark them for sign-off.
2. **Set marketing's commitments.** Volume of qualified leads per month (derived from the pipeline target working backwards through historical conversion rates), minimum data on each lead (name, company, role, source, the action that triggered it), and the quality bar (share that sales should accept).
3. **Tier response times by intent.** Hand-raisers (demo, pricing, contact sales) deserve the fastest response, measured in minutes to a few hours during business hours. Scored leads can tolerate a business day. Low-intent leads may go to nurture without rep contact. Speed matters most for the highest intent leads; a single target for all leads either wastes rep time or loses hot ones.
4. **Define follow-up effort.** The number of attempts across channels and the period they span before a lead can be closed out (for example, several touches across email, phone, and social over two to three weeks). Define what counts as an attempt: a logged call or a sent personal email, not a status change.
5. **Write acceptance and rejection rules.** Sales must accept or reject within a set window (often one to two business days). Rejection requires a reason from a fixed list (wrong fit, wrong person, no contact data, duplicate, existing customer, not interested now). This list is marketing's most useful quality feedback.
6. **Define recycling.** Where rejected or unresponsive leads go (nurture, re-score), how long before they can return, and what re-qualifies them. Leads should never just disappear.
7. **Add accountability for both sides.** If marketing delivers below the agreed quality, sales follow-up obligations for those leads relax. If sales misses response times, those leads do not count against marketing's conversion targets. Symmetry keeps the agreement fair.
8. **Build the scorecard.** Weekly or monthly: leads delivered versus target, acceptance rate, median time to first touch by tier, share meeting effort standard, rejection reasons breakdown, conversion to opportunity, and pipeline created.
9. **Set governance.** A recurring joint review (monthly works for most teams), an escalation path when the SLA is breached repeatedly, and a quarterly renegotiation of targets.

## Output format

```
# Sales and Marketing SLA   Effective [date]   Review [cadence]
Signed by: [Marketing lead], [Sales lead]

## Definitions
MQL: [criteria]   SAL: [criteria]   SQL: [criteria]

## Marketing commits to
- [n] MQLs per month, split by segment
- Required data on every lead: [...]
- Target acceptance rate: [x]%

## Sales commits to
| Lead tier | Examples | First touch within | Attempts | Over period |
|---|---|---|---|---|

## Acceptance and rejection
Accept or reject within [x] business days. Rejection reasons: [list]

## Recycling
| Outcome | Goes to | Can return when |

## Mutual accountability
[rules for each side when the other misses]

## Scorecard
| Metric | Target | Owner | Source report |

## Governance and escalation
[review meeting, attendees, escalation steps]
```

## Quality checklist

- Commitments run both ways; each team has measurable obligations.
- Definitions are written, not referenced as "the usual."
- Response times are tiered by lead intent.
- "Attempt" and "worked" are defined by real activity.
- Rejection needs a reason from a fixed list within a deadline.
- Recycling rules ensure no lead disappears.
- Every scorecard metric has an owner and a data source.
- There is a review cadence and an escalation path.

## Common mistakes

- **One-way SLAs.** An agreement that only measures sales response becomes a stick, and sales stops engaging with it.
- **Volume targets without quality targets.** Marketing hits the number with leads nobody can sell to.
- **A single response time for every lead.** Treating a newsletter signup like a demo request burns rep time.
- **Silent non-follow-up.** Leads that are neither worked nor rejected hide the real quality picture. Force a decision.
- **Free-text rejection reasons.** They cannot be analysed. Use a fixed list plus optional notes.
- **No consequence for breaches.** If nothing happens when the SLA is missed, it is a wish list.
- **Writing it once.** Targets and capacity change; renegotiate quarterly.

## Example prompts

- "Write a sales and marketing SLA for our inbound team of 5 SDRs and 8 AEs."
- "Marketing and sales keep fighting about lead quality. Draft an agreement and a scorecard."
- "Set tiered response times for demo requests, trials and content downloads."
- "Create rejection reasons and recycling rules for leads sales does not accept."
- "Work backwards from a pipeline target to the number of MQLs marketing should commit to."
