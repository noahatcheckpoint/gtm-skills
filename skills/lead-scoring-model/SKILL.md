---
name: lead-scoring-model
description: Builds a two-axis lead scoring model (fit and intent) with point weights derived from historical conversion, negative signals, decay rules, an MQL threshold and a validation plan. Use when designing scoring from scratch, when sales ignores the current score, or when MQL volume and quality are out of balance.
license: MIT
metadata:
  title: "Lead Scoring Model"
  category: "revops-crm"
  author: "harmeet"
  summary: "Design fit and intent scores weighted by real conversion data, with decay, negative signals and a threshold you can defend to sales."
  tags: "lead scoring, MQL threshold, fit score, intent signals, RevOps"
  version: "1.0"
  updated: "2026-10-19"
---
# Lead Scoring Model

Produces a scoring specification a CRM admin can implement and a sales leader can trust: separate fit and intent scores, weights grounded in your own win data where it exists, decay and negative rules, a threshold, and a backtest that shows the score actually separates winners from the rest.

## When to use

- Building the first scoring model, or replacing one nobody believes.
- Reps say "the score is meaningless" and work leads by gut feel.
- MQL volume swings wildly or conversion from MQL to opportunity keeps falling.
- A new segment, product, or motion (for example a free trial) needs its own scoring.

## What you need

Ask for these before building. If data is missing, say which weights will be assumptions.

1. **ICP and anti-ICP:** firmographics, roles, and the profiles you never want to see.
2. **Outcome data:** every lead (or account) created in the last 12 to 18 months, with its attributes as they stood when it arrived and what happened next: became an opportunity or not, then won or lost. Even a spreadsheet export works. Won and lost deals alone are not enough, because they only describe leads that already reached sales.
3. **Available signals:** form fields, enrichment fields, web and email activity, product usage, third-party intent if any.
4. **Current funnel volumes:** leads per month, current MQLs, MQL to opportunity rate.
5. **Sales capacity:** how many new leads per rep per week can be worked properly.
6. **Hand-raisers:** which actions should bypass scoring entirely (demo request, contact sales, pricing quote).

## Process

1. **Split the score into two axes.** Fit asks "should we sell to them?" Intent asks "are they leaning in now?" Report them separately (for example a letter grade for fit and a number for intent). A single blended number hides a perfect-fit account that is cold and a hot lead from a company you cannot serve.
2. **Route hand-raisers around the model.** A demo request from an in-ICP company goes straight to sales. Scoring exists for the ambiguous middle, not for people who already asked.
3. **Derive fit weights from lift, not opinion.** Work on the full cohort of leads created in a period, not just deals, and use each attribute as it was at creation (fields enriched after the deal leak the outcome back in). For each value (industry, size band, role seniority, region), compute its lead-to-opportunity rate and divide by the cohort's overall rate; repeat with win rate as a second view. A value with 2x lift earns roughly double the points of a 1x value; values below 0.5x earn zero or negative. Merge thin cells before trusting them (heuristic: under about 30 leads or 10 conversions), and with fewer than about 50 conversions overall, label weights as hypotheses.
4. **Pick intent signals that precede revenue.** Rank activities by how often they appear in the 30 to 60 days before won deals versus lost or stalled ones. Typical high-value signals: pricing page visits, return visits from several people at one account, product usage milestones, replies to sales emails. Low-value: single blog views, opening newsletters.
5. **Add negative scoring, and keep suppression outside it.** Competitor domains, students, job seekers, free email domains (if B2B only) and unsupported countries subtract points or disqualify. Unsubscribes and hard bounces are not score events: an unsubscribe suppresses the contact for the channel and scope they opted out of, a hard bounce suppresses that address, and no intent score can bring either back into marketing or sequences.
6. **Add decay.** Intent should fade when activity stops. Heuristic: reduce intent points by a fixed share each month without activity, or reset intent to zero after 90 days of silence. Fit does not decay, but it must be refreshed when enrichment data changes.
7. **Cap repeated actions.** Ten visits to the same blog post should not equal one pricing visit. Cap points per signal per period.
8. **Set the threshold from capacity.** Work backwards: if reps can handle 120 new MQLs a month and the model scores 600 leads above 40, the threshold is too low. Choose the cut that delivers the volume sales can work within the SLA, then check the conversion rate at that cut.
9. **Backtest out of time.** Fit the weights on an earlier period, then score leads from a later period the weights never saw. Show conversion to opportunity by score band. A good model shows a clear staircase: each higher band converts noticeably better than the one below. If bands are flat, the weights are wrong.
10. **Define governance.** Owner, review cadence (quarterly is typical), change log, and a rule that only a few weights change per review so you can see what caused any shift.

## Output format

```
# Lead Scoring Model: [Segment]  Version [x]  Owner [name]

## Bypass rules (go straight to sales)
- [action] from [fit condition]

## Fit score (grade A to D)
| Attribute | Value | Lift vs baseline | Points | Evidence (n leads / conversions) |

## Intent score (0 to 100)
| Signal | Points | Cap per 30 days | Why it matters |

## Negative and disqualifying rules
| Condition | Effect (minus points / disqualify) |

## Suppression (outside the score)
- Unsubscribed: suppressed for [channel and scope]
- Hard bounce: address suppressed

## Decay
[rule]

## MQL definition
Fit grade [A or B] AND intent >= [x], OR bypass action.
Expected volume: [n per month] vs sales capacity [n].

## Backtest
| Score band | Leads | Opportunities | Conversion |

## Governance
Review cadence, change log location, success metrics.

## Assumptions
```

## Quality checklist

- Fit and intent are separate, and the MQL rule uses both.
- Every fit weight cites lift or is labelled as an assumption.
- Hand-raisers bypass the score.
- Negative rules include competitors and non-buyers; some disqualify outright.
- Unsubscribes and hard bounces trigger suppression, never just a point deduction.
- Weights come from the full lead cohort with point-in-time attributes, and the backtest uses a later period.
- Intent decays and repeated actions are capped.
- Threshold is justified by sales capacity and backtest conversion.
- Backtest shows conversion rising band by band, or the output says it does not.
- There is a named owner and a review cadence.

## Common mistakes

- **Scoring what is easy to track instead of what predicts revenue.** Email opens are plentiful and nearly useless as a buying signal.
- **One blended number.** Engagement can push a terrible-fit lead over the line. Fit must gate intent.
- **No decay.** A lead who binged content 14 months ago still sits at MQL level and pollutes the queue.
- **Setting the threshold by round number** ("50 feels right") instead of by capacity and conversion.
- **Weights set in a workshop and never checked.** Without a backtest you cannot tell a model from a guess.
- **Changing ten rules at once.** When MQL volume jumps, nobody knows which change did it.
- **Ignoring account-level activity.** In B2B, three people from one account each doing a little is a stronger signal than one person doing a lot.

## Example prompts

- "Build a lead scoring model for our mid-market SaaS. Here is an export of last year's leads and what happened to each."
- "Sales says our MQLs are junk. Review our scoring rules and tell me what to change."
- "Design separate fit and intent scores and an MQL threshold that matches 4 SDRs' capacity."
- "Add decay and negative scoring to our existing model."
- "How do I backtest a new scoring model before turning it on?"
