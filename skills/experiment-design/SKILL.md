---
name: experiment-design
description: Designs a go-to-market experiment (landing page, email, pricing page, outbound sequence, onboarding flow) with a falsifiable hypothesis, one primary metric, guardrail metrics, sample size and duration estimates, randomisation unit, stopping rules and a decision plan written before launch. Use before running any A/B or holdout test, when test results keep being inconclusive, or when low traffic makes classic A/B testing doubtful.
license: MIT
metadata:
  title: "Experiment Design"
  category: "analytics"
  author: "harmeet"
  summary: "Plan a GTM test with a falsifiable hypothesis, one primary metric, sample size, stopping rules and a decision written before launch."
  tags: "A/B testing, experiment design, sample size, conversion optimisation, holdout test"
  version: "1.0"
  updated: "2026-10-19"
---
# Experiment Design

Produces a one-page test plan that is agreed before anything goes live: what you believe, what you will change, how you will measure it, how long it must run, what would make you stop, and what you will do with each possible result. Writing the decision in advance is what separates an experiment from a story told afterwards.

## When to use

- Before launching an A/B test on a page, email, ad, pricing presentation, or onboarding step.
- Testing an outbound sequence or messaging angle across two groups of accounts.
- Measuring whether a programme (nurture, a sales play) creates lift, using a holdout group.
- Previous tests ended "inconclusive" or were stopped as soon as a winner appeared.
- Traffic is low and you need to decide whether a test is even feasible.

## What you need

Ask for these before designing:

1. **The change** you want to test and why you think it will work (research, data, customer feedback).
2. **Primary goal:** the business outcome you care about (signups, demo requests, replies, meetings, activation, revenue).
3. **Baseline:** current conversion rate on that metric and volume per week reaching the tested step.
4. **Smallest lift worth acting on:** the minimum improvement that would justify shipping and maintaining the change.
5. **Constraints:** how long you can run, tools available for splitting traffic or lists, seasonal events coming up.
6. **Risks:** metrics that must not get worse (unsubscribes, lead quality, refund rate, page speed).

## Process

1. **Write a falsifiable hypothesis.** Format: "Because [evidence], we believe that [change] for [audience] will [increase/decrease] [primary metric] by at least [amount]. We will know this is false if [result]." If you cannot say what result would prove it wrong, it is not ready.
2. **Pick one primary metric.** Choose the metric closest to revenue that still has enough volume to measure in the time available. Clicks are easy to move and often do not translate into pipeline; meetings booked or qualified signups are better if volume allows.
3. **Add guardrails.** Two or three metrics that must not deteriorate beyond a set tolerance (for example, lead fit score, unsubscribe rate, downstream conversion to opportunity). A variant that wins the primary metric but breaks a guardrail does not ship.
4. **Choose the randomisation unit.** Visitor, account, or rep territory. In B2B, randomise by account when several people from one company might see both variants, or results will be contaminated.
5. **Estimate sample size and duration.** Fix the design before calculating: randomisation unit, allocation ratio (50/50 or unequal), one-sided or two-sided test, and expected attrition. A standard calculator is valid only when the unit you randomise is the unit you measure, such as visitors. If you randomise accounts or territories but measure people or leads, outcomes within a cluster move together, so the calculation must use the number of clusters and an intracluster correlation estimate (from past data, or a cautious assumed value); an ordinary calculator will overstate your power, often badly when there are only a few dozen clusters. Common defaults are 95% confidence and 80% power with the smallest lift worth acting on. Divide by weekly volume to get duration. As a heuristic, run for at least one full business cycle (often two weeks minimum) to cover weekday patterns. Remember that small baselines need far more traffic to detect the same relative lift.
6. **Check feasibility honestly.** If the required duration is longer than you can run, choose a different approach: test a bigger change, move the metric up the funnel, pool similar pages, or use a qualitative method (user tests, sales call feedback) instead. Running an underpowered test and calling it a result is worse than not testing.
7. **Set stopping rules before launch.** The default is a fixed horizon: run until the planned sample is reached, and stop early only for a guardrail breach or a broken implementation. Unplanned peeking, stopping as soon as one variant looks ahead, greatly increases false winners and exaggerates effect sizes. If you need the option to stop early for a clear win or for futility, choose a sequential design up front (group-sequential with alpha spending, or a Bayesian rule with a pre-set decision threshold), write down the interim looks and boundaries, and size the test for it.
8. **Plan a quality check.** Verify both variants render and track correctly on day one, and that groups are balanced in size and mix (a sample ratio check).
9. **Write the decision table.** For each outcome (clear win, clear loss, inconclusive, guardrail breach) state the action now. Inconclusive usually means keeping the simpler or cheaper option and logging what was learned.
10. **Plan the write-up.** What was tested, the result with a confidence interval, the decision, and what the next test is. Store it in a shared log so teams stop repeating old tests.

## Output format

```
# Experiment Plan: [Name]   Owner [ ]   Planned start [ ]

## Hypothesis
Because [evidence], we believe [change] for [audience] will [direction] [metric] by at least [x]. Falsified if [result].

## Variants
Control: [ ]   Variant: [ ]   (one change only, or a declared bundle)

## Metrics
Primary: [metric, definition, data source]
Guardrails: [metric, tolerance]

## Design
Randomisation unit: [visitor / account / territory]   Measurement unit: [ ]
Split: [50/50]   Sidedness: [ ]   Clusters per arm and ICC (if clustered): [ ]
Audience and exclusions: [ ]   Expected attrition: [ ]

## Sample size and duration
Baseline [ ]  Minimum lift worth acting on [ ]  Confidence [95%]  Power [80%]
Required per variant [ ]   Weekly volume [ ]   Duration [ ] weeks
Feasible? [yes / no, and alternative]

## Stopping rules
[fixed horizon: planned sample reached; early stop only for guardrail breach or broken tracking]
[or sequential: interim looks at [ ], efficacy and futility boundaries [ ], method [ ]]

## Decision table
| Outcome | Action |
|---|---|
| Win on primary, guardrails OK | |
| Loss | |
| Inconclusive | |
| Guardrail breach | |

## Launch checks
[tracking verified, sample ratio check, QA of both variants]
```

## Quality checklist

- The hypothesis states evidence, direction, minimum lift, and what would falsify it.
- There is exactly one primary metric, and it is close to revenue.
- Guardrails have explicit tolerances.
- The randomisation unit prevents the same account seeing both variants where that matters.
- Sample size and duration are estimated and feasibility is judged honestly.
- Stopping rules forbid unplanned peeking; any early efficacy or futility stop comes from a pre-specified sequential design.
- Clustered designs are sized on the number of clusters with an intracluster correlation, not with an ordinary calculator.
- A decision is written for every outcome before launch.

## Common mistakes

- **Stopping when it looks significant.** Checking daily and stopping at the first good reading produces false winners far more often than the stated confidence suggests.
- **Too many metrics.** With ten metrics, one will "win" by chance. Pick one primary before launch.
- **Testing tiny changes on tiny traffic.** A button colour on 300 visitors a week will never reach a result. Test bold changes or do not test.
- **Randomising by visitor in account-based motions.** Two buyers at the same company see different messages and the results blur.
- **Optimising clicks that do not produce pipeline.** A higher click rate with worse lead quality is a loss.
- **No decision plan.** Without one, every result gets reinterpreted to fit what someone already wanted.
- **Not logging results.** Teams rerun the same test a year later because nobody wrote it down.

## Example prompts

- "Design an A/B test for a new demo request page headline. We get about 4,000 visitors a week and convert 2.1%."
- "We want to test two outbound messaging angles across 600 accounts. How should we split and measure it?"
- "Is a pricing page test feasible with 900 visitors a month? If not, what should we do instead?"
- "Write the hypothesis, metrics and decision table for testing a shorter signup form."
- "Set up a holdout test to measure whether our nurture sequence creates pipeline."
