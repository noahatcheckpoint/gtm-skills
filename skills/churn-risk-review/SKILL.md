---
name: churn-risk-review
description: Reviews a book of customer accounts for churn and downgrade risk using usage, relationship, support, commercial and outcome signals, tiers each account by risk and renewal proximity, diagnoses the likely cause and writes a save plan per at-risk account. Use ahead of renewal quarters, in weekly customer success reviews, after a churn spike, or when designing a customer health score.
license: MIT
metadata:
  title: "Churn Risk Review"
  category: "customer-success"
  author: "esther"
  summary: "Spot at-risk customers early from usage, relationship and support signals, tier them by urgency and write a save plan for each."
  tags: "churn risk, customer health score, renewals, customer success, retention"
  version: "1.0"
  updated: "2026-10-19"
---
# Churn Risk Review

Produces a prioritised list of accounts at risk of churning or shrinking, the evidence behind each rating, the most likely cause, and a concrete save plan with an owner and deadline. It also suggests how to turn the signals into a repeatable health score.

## When to use

- Two to three quarters before a large block of renewals.
- Weekly or monthly customer success reviews.
- After an unexpected churn or downgrade, to find similar accounts before they leave.
- When building or recalibrating a customer health score.
- When a key product change, price increase, or support incident affects many customers.

## What you need

Ask for these before reviewing:

1. **Account list** with contract value, renewal date, segment, and owner.
2. **Usage data:** active users versus licensed seats, key feature adoption, trend over the last 90 days.
3. **Relationship data:** executive sponsor and champion names, last meaningful contact, any role changes.
4. **Support data:** open tickets, escalations, recent incidents, satisfaction scores.
5. **Commercial data:** payment issues, discount history, downgrade requests, budget comments.
6. **Outcome data:** the goals agreed at onboarding and whether they are being met.
7. **Past churn:** if available, the reasons and signals seen before previous losses.

## Process

1. **Group signals into five families** and assess each account on all of them:
   - Usage: falling active users, seats unused, key features abandoned, logins concentrated in one person.
   - Relationship: champion or sponsor left, no executive contact in six months, meetings declined, slow replies.
   - Support: repeated tickets on the same issue, escalations, a recent serious incident, worsening satisfaction.
   - Commercial: late payments, requests to reduce seats, procurement suddenly involved, budget cuts announced, acquisition by another company.
   - Outcomes: the goals they bought for are not being reached, or nobody can say what the goals were.
2. **Weight signals by what has predicted churn for you.** If past churn data exists, check which signals appeared before losses and weight those highest. Without history, treat champion loss, sharp usage decline, and unmet outcomes as the strongest early warnings.
3. **Rate each account:** Healthy, Watch, At risk, or Critical. Use the trend, not just the level: a large customer at 60% usage and rising is healthier than one at 80% and falling fast.
4. **Combine risk with renewal timing and value.** Critical accounts renewing within 90 days and above a value threshold go first. A risky account renewing in 11 months has time for a structured recovery.
5. **Diagnose the root cause.** Typical causes: poor onboarding (never reached value), lost champion, product gap, service failure, price or budget pressure, strategy change at the customer, or a competitor. The save plan depends on the cause; a discount will not fix an adoption problem.
6. **Write a save plan per at-risk account.** Include the objective (renew at what value), the actions (re-onboard a team, executive-to-executive call, success review with a new sponsor, roadmap conversation, commercial restructure), the owner, and dates. Decide early which accounts need help from leadership, product, or support.
7. **Plan the conversation.** For critical accounts, prepare an honest opening: acknowledge the issue, show what you have observed, ask what has changed for them, and propose a recovery plan with dated review points.
8. **Identify accounts to let go gracefully.** Some customers are a poor fit and will churn regardless. Note them, protect the relationship, and capture the lesson for qualification.
9. **Turn findings into a health score.** Propose a simple scored model (each signal family weighted, refreshed monthly) and a review cadence. Recalibrate after each renewal cycle by comparing scores with actual outcomes.

## Output format

```
# Churn Risk Review: [Book / Segment]   As of [date]

## Summary
[n] accounts reviewed, [value] at risk, [n] critical renewing in 90 days.

## Risk register
| Account | ARR | Renewal | Usage | Relationship | Support | Commercial | Outcomes | Rating | Trend | Likely cause | Owner |
|---|---|---|---|---|---|---|---|---|---|---|---|

## Save plans (At risk and Critical)
### [Account]
- Objective:
- Root cause:
- Actions (owner, date):
- Help needed from: [leadership / product / support]
- Review date:

## Accounts to let go gracefully
[account, reason, lesson]

## Patterns across the book
[common causes, segments, product areas]

## Proposed health score
| Signal family | Indicators | Weight | Data source |
Refresh cadence, recalibration plan.
```

## Quality checklist

- Every account is assessed on all five signal families or the gap is noted.
- Ratings consider trend, not only current level.
- Priority combines risk, renewal date, and value.
- Each at-risk account has a root cause, not just a symptom.
- Save plans have owners, dates, and a review date.
- Discounts are not the default remedy.
- Patterns across accounts are summarised for product and leadership.
- A health score proposal includes a recalibration step.

## Common mistakes

- **Starting the save conversation at renewal.** By then the customer has usually decided. Risk work must start two or more quarters ahead.
- **Trusting a friendly user over silence from the sponsor.** Daily users rarely make the renewal decision.
- **Usage counts without context.** Login volume can look fine while the team that bought the product has stopped using it.
- **Discounting to save an adoption problem.** A cheaper product nobody uses still churns next year.
- **Health scores nobody calibrates.** If green accounts churn, the weights are wrong; compare scores with actual outcomes each cycle.
- **Hiding risk to protect a forecast.** Late surprises are worse than early honest flags.
- **No feedback loop to sales and product.** The same poor-fit customers keep being sold and the same gaps keep causing churn.

## Example prompts

- "Review these 40 accounts renewing next quarter and flag churn risk. Here is usage, ticket and contact data."
- "Our champion at a top-10 customer just left. Write a save plan."
- "Design a simple customer health score from usage, support and relationship signals."
- "We lost three customers last month. Find similar accounts in our book before they leave."
- "Prepare talking points for a renewal conversation with a customer whose usage dropped 40%."
