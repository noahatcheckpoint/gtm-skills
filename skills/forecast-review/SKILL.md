---
name: forecast-review
description: Runs a weekly or quarterly sales forecast review: classifies deals into commit, best case and pipeline using evidence rules, tests each committed deal, compares rep call, weighted and historical views, and produces a forecast call with risks and actions. Use before a forecast call, a board update, or when forecast accuracy has been poor.
license: MIT
metadata:
  title: "Forecast Review"
  category: "revops-crm"
  author: "noah"
  summary: "Pressure-test the forecast deal by deal with evidence rules, three independent views and a clear call with named risks."
  tags: "sales forecast, commit, best case, pipeline coverage, deal inspection"
  version: "1.0"
  updated: "2026-10-19"
---
# Forecast Review

Produces a defensible forecast number for the period plus the reasoning behind it: which deals are truly committed, what upside is realistic, where the gap to target sits, and what must happen this week to close it. It replaces "the reps said so" with evidence rules applied consistently.

## When to use

- Preparing for a weekly forecast call or a monthly or quarterly leadership update.
- The last few periods missed (or massively beat) the forecast and you want to know why.
- A new sales leader wants a consistent inspection method across managers.
- Pipeline looks large but coverage feels thin.

## What you need

Ask for these before reviewing:

1. **Period and target:** quarter or month, quota or plan number, booked to date.
2. **Open deal list** for the period: name, amount, stage, close date, rep forecast category, next step, last activity date, and close date change history if available.
3. **Category definitions** in use today, if any.
4. **History:** win rate by stage and by category over the last four quarters, and past forecast accuracy (called versus actual).
5. **Context:** big deals that drive the number, known seasonality, recent pricing or team changes.

## Process

1. **Fix the category rules first.** If the team has none, propose:
   - Commit: the buyer has agreed to buy, the paper process is known and in motion, the signer is identified, and only execution remains. You would be surprised to lose it.
   - Best case: a real path to close this period exists, but at least one condition is unconfirmed (approval, legal, budget release).
   - Pipeline: qualified and open, but closing this period would need things to go unusually well.
   - Omitted: not closing this period; remove from the call.
2. **Test every commit deal with six questions.** Has the economic buyer confirmed? Is the paper process (legal, procurement, security) mapped with dates? Is the close date tied to a buyer event (budget cycle, go-live need) rather than our quarter end? When was the last two-way buyer interaction? Has the close date already moved? Is the amount agreed or still a proposal? Two or more weak answers moves the deal to best case.
3. **Flag hygiene risks across the list:** close dates in the past, no activity in 14 days or more, close date pushed twice or more, amount changed late, deals that skipped stages, single-threaded deals with one contact.
4. **Build three views of the number:**
   - Rep call: sum of commit plus the rep's judgment on best case.
   - Weighted: amount times the historical rate at which comparable deals closed within the time left in the period. A plain stage win rate counts wins that took months and so overstates an in-period number. Build the rates from past deals at the same point in a period, split by stage, time already spent in stage, deal type and amount band, and treat deals likely to slip together (one budget freeze, one large buyer) as correlated rather than independent. Backtest the method on a few past periods and use it only if it would have landed close.
   - Run rate or history: what similar periods closed relative to starting pipeline.
   If the views differ by more than about 15%, explain the gap before choosing a number.
5. **Check coverage.** Remaining target versus open pipeline in period. Many B2B teams use 3x coverage early in a quarter as a rule of thumb, but your own historical conversion is a better guide. Coverage that only works if every best case deal closes is a gap, not coverage.
6. **Concentrate on what moves the number.** Rank deals by amount times uncertainty. The top five to ten usually decide the period; spend review time there.
7. **Make the call:** a commit number, a most-likely number, and an upside number, each with the deals that make it up.
8. **Assign actions.** For every at-risk deal above a size threshold: the single action that would de-risk it this week, the owner, and the date. Typical actions: executive-to-executive call, confirm procurement steps in writing, agree a mutual action plan, renegotiate scope to fit budget.
9. **Track accuracy.** Record the call, then compare it with the result at period end. Accuracy by rep and by category reveals habitual sandbagging or optimism.

## Output format

```
# Forecast Review: [Team]  [Period]  As of [date]

## The call
| | Amount | vs target |
|---|---|---|
| Booked | | |
| Commit | | |
| Most likely | | |
| Upside | | |

## Three views
| View | Number | Notes |
| Rep call | | |
| Weighted (horizon-matched, backtested) | | |
| Historical run rate | | |

## Coverage
Remaining target [ ], open pipeline in period [ ], coverage [x]

## Commit inspection
| Deal | Amount | EB confirmed | Paper process | Buyer-driven date | Last buyer touch | Date pushes | Verdict |

## Risk flags
| Deal | Flag | Action | Owner | By |

## Category changes recommended
| Deal | From | To | Reason |

## Gap closing plan
[deals and actions that would close the gap to target]

## Accuracy log
Last period called [ ] vs actual [ ]
```

## Quality checklist

- Category rules are written down and applied the same way to every rep.
- Every commit deal has been tested against the six questions.
- Three independent views are shown and any large gap is explained.
- Coverage is calculated on in-period pipeline only.
- The call has commit, most likely, and upside, each traceable to deals.
- Every at-risk large deal has one action, an owner, and a date.
- Past accuracy is referenced.

## Common mistakes

- **Treating stage as category.** A deal in Negotiation is not automatically commit; buyer evidence decides.
- **Quarter-end close dates.** Dates clustered on the last day of the period reflect our calendar, not the buyer's.
- **Ignoring date push history.** A deal that has slipped twice is far less likely to close than its stage suggests.
- **Inspecting every deal equally.** Time spent on small deals is time not spent on the five that decide the number.
- **Punishing honest downgrades.** If moving a deal out of commit triggers a lecture, reps stop doing it.
- **Coverage inflated by out-of-period deals** or by pipeline that has had no activity in a month.
- **Never closing the loop.** Without an accuracy log, the same optimism repeats every quarter.

## Example prompts

- "Review this quarter's forecast. Here is our open deal list with stages, amounts and close dates."
- "Apply strict commit rules to these 12 deals and tell me which ones should move to best case."
- "Build a weighted forecast using our historical stage win rates and compare it to the rep call."
- "We are 30% short of target with six weeks left. Where can the gap realistically come from?"
- "Write forecast category definitions our managers can enforce consistently."
