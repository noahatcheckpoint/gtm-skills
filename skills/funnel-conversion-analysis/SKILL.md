---
name: funnel-conversion-analysis
description: "Analyses a B2B revenue funnel stage by stage using cohort-based conversion rates and stage velocity, segments the results to find where and for whom the funnel leaks, sizes the revenue impact of each leak and recommends the two or three fixes worth doing first. Use for quarterly business reviews, when pipeline targets are missed, or when deciding where to invest marketing and sales effort."
license: MIT
metadata:
  title: "Funnel Conversion Analysis"
  category: "analytics"
  author: "harmeet"
  summary: "Find where your revenue funnel leaks, for which segments, and which fix is worth the most, using cohort conversion and velocity."
  tags: "funnel analysis, conversion rates, pipeline velocity, cohort analysis, revenue analytics"
  version: "1.0"
  updated: "2026-10-19"
---
# Funnel Conversion Analysis

Produces a diagnosis of the revenue funnel: conversion and time between every stage, measured on cohorts so the numbers are honest, broken down by the segments that matter, with each leak sized in revenue and a short list of fixes ranked by value. The output answers "where should we focus next quarter?"

## When to use

- Pipeline or bookings targets were missed and leadership wants to know why.
- Preparing a quarterly business review or annual plan.
- Deciding whether to invest in more top-of-funnel volume or better conversion.
- A channel, segment, or team seems to underperform and you need evidence.
- After changing lifecycle or pipeline definitions, to set a new baseline.

## What you need

Ask for these before analysing:

1. **Stage definitions** for the funnel being analysed (for example lead, MQL, SQL, opportunity, closed won). If definitions changed during the period, note when.
2. **Data:** records with the date each stage was entered, plus segment fields (source, channel, company size, industry, region, rep or team, product). A spreadsheet export is fine.
3. **Time range:** ideally four or more quarters so cohorts have time to mature.
4. **Values:** average deal size by segment, sales cycle length.
5. **Targets** for the coming period, if the goal is planning.
6. **Known events:** pricing changes, new team members, campaign launches, tracking changes.

## Process

1. **Validate the data first.** Check for records that skip stages, stage dates out of order, stages set in bulk on one day (often an import or a workflow change), and missing segment values. Note what you exclude and why. A funnel built on broken timestamps produces confident nonsense.
2. **Use cohort conversion, not snapshot ratios.** Group records by the month or quarter they entered a stage, then measure what share reached the next stage within a defined window. Dividing this month's SQLs by this month's MQLs mixes different cohorts and misleads whenever volume changes.
3. **Respect cohort maturity.** Recent cohorts have not had time to convert. Either exclude cohorts younger than the typical stage-to-stage time, or show them separately as immature.
4. **Measure velocity, including the records that never moved.** Median days between each pair of stages (median, not mean, because a few slow deals distort averages) describes only records that reached the next stage, so label it as time among converters. A funnel where most records stall or die can still show a fast median. Add an aging view per entry cohort: the share still open, lost and converted at 30, 60 and 90 days, or a time-to-event curve that keeps open records as censored instead of dropping them. Also compute overall pipeline velocity: number of opportunities times win rate times average deal size, divided by sales cycle length.
5. **Build the baseline funnel.** Volume in, conversion to next stage, median days, for each stage. Highlight the stage with the biggest gap versus your own history or a target.
6. **Segment.** Break conversion down by source, segment, region, and team. Look for the cells that differ most from the overall rate, and check the volume behind each; a 60% rate on five records is noise.
7. **Size each leak.** For the weakest stage and segment combinations, estimate the revenue gained if conversion moved to a realistic benchmark (your best-performing comparable segment, or last year's rate), all else equal. This turns a conversion chart into a priority list.
8. **Diagnose causes.** Combine the numbers with qualitative evidence: rejection and loss reasons, call notes, lead response times. Common causes are slow follow-up, poor-fit leads from one channel, weak qualification, missing champion access, or pricing friction.
9. **Recommend two or three fixes.** For each, the expected impact, effort, owner, and the metric that will show whether it worked. Prefer fixes at the stage with the largest sized gap, not the most visible complaint.
10. **Set up monitoring.** The same cohort views, refreshed monthly, with alert thresholds for the stages you are fixing.

## Output format

```
# Funnel Conversion Analysis: [Company / Segment]   Period [ ]

## Summary
The biggest leak is [stage] for [segment]; fixing it to [benchmark] is worth about [revenue]. Top fixes: [1] [2] [3].

## Data notes
Exclusions, definition changes, immature cohorts.

## Baseline funnel (cohort-based)
| Stage to stage | Cohort volume | Conversion | Median days (converters only) | Still open / lost at 90 days | vs last year / target |
|---|---|---|---|---|---|

## Pipeline velocity
[opps] x [win rate] x [avg deal] / [cycle days] = [value per day]

## Segment breakdown
| Segment | Stage | Volume | Conversion | Gap vs overall |

## Leak sizing
| Leak | Current | Benchmark | Revenue impact | Confidence |

## Likely causes
[evidence per leak]

## Recommendations
| Fix | Stage | Expected impact | Effort | Owner | Success metric |

## Monitoring
[views, cadence, alert thresholds]
```

## Quality checklist

- Data quality issues are checked and exclusions are stated.
- Conversion is cohort-based with a defined window, not a same-period ratio.
- Immature cohorts are excluded or labelled.
- Velocity uses medians labelled as converters only, alongside an aging or time-to-event view that includes open and lost records.
- Segment results show the volume behind each rate.
- Every leak is sized in revenue with a stated benchmark.
- Recommendations are limited to the top two or three with success metrics.

## Common mistakes

- **Snapshot ratios.** Comparing this month's stage counts mixes cohorts; when volume grows, conversion appears to fall even if nothing changed.
- **Judging recent cohorts too early.** Last month's leads have not had time to become customers.
- **Averages distorted by outliers.** One deal that took 400 days drags the mean; use medians.
- **Reading noise as signal.** Small segments swing wildly. Show volume and avoid conclusions on tiny samples.
- **Fixing the loudest complaint.** The stage people argue about is not always the stage that costs the most revenue.
- **Ignoring definition changes.** A new MQL rule mid-year creates an apparent conversion jump that is purely definitional.
- **Recommending ten fixes.** Teams act on two or three. Rank by sized impact and stop.

## Example prompts

- "Analyse our funnel from MQL to closed won for the last four quarters. Here is the export with stage dates."
- "Our pipeline is down 25% versus plan. Where is the funnel leaking?"
- "Compare conversion and velocity by lead source and company size."
- "Calculate our pipeline velocity and tell me which lever matters most."
- "Should we invest in more leads or better conversion next quarter? Use our funnel data to decide."
