---
name: pipeline-coverage-gap-plan
description: "Use when a team needs to find where pipeline falls short of target by segment and stage, then plan sources, owners and checkpoints to close the gap before the shortfall reaches the forecast."
license: MIT
metadata:
  title: "Pipeline Coverage Gap Plan"
  category: "gtm-strategy"
  author: "noah"
  summary: "Find where pipeline falls short of target by segment and stage, then plan sources, owners and checkpoints to close the gap."
  tags: "pipeline, planning, coverage, capacity"
  version: "1.0"
  updated: "2026-11-24"
---
# Pipeline Coverage Gap Plan

## When to use

- A new period is starting and the team wants to know whether pipeline is sufficient to reach target before the period is underway.
- Pipeline looks thin in one segment, region or stage, and the response so far has been ad hoc campaigns or general pushes for more outreach.
- A target has changed (higher goal, new segment, new product line) and existing coverage was sized for the old one.
- Capacity has changed, for example reps have left, a team has been added, or a program has been paused, and the team needs to see what that does to coverage.
- Leadership asks where the pipeline will come from and nobody has a single, shared answer.

This is a forward-looking planning exercise. It is not a forecast review of deals already in play. Use it to decide how to create or recover pipeline, then hand deal-level inspection to the normal forecast process.

## What you need

Ask for these before building anything:

1. **Target:** the revenue or bookings goal for the period, split by the segments the business actually manages (region, size band, product, new versus expansion).
2. **Current pipeline:** open opportunities by segment and stage, with amounts, expected close periods and source. A spreadsheet export or a pasted table is enough.
3. **Conversion assumptions:** how pipeline at each stage has historically turned into closed business, as the team understands it. If nobody trusts the history, capture a working assumption and mark it as an assumption.
4. **Coverage rule:** the multiple of pipeline to target the team considers healthy, and who set it. If none exists, agree on a working one and label it.
5. **Timing:** how long each stage typically takes, so pipeline created late is not counted as if it could still close in the period.
6. **Capacity:** quota-carrying headcount, outbound capacity, marketing program budget, partner reach and any known constraints on each.
7. **Owners:** who leads each function that could create or recover pipeline, and who can approve changes to the plan.

If any item is missing, say so in the output and proceed with clearly labeled assumptions. Do not invent figures.

## Process

1. **Restate the target by segment.** Break the goal into the same segments the pipeline data uses. If the two do not line up, fix the mapping first, because every later step depends on it. Note any segment where the target is new or unproven.
2. **Compute required pipeline.** For each segment, work out how much pipeline is needed at each stage to support the target, using the conversion assumptions and the coverage rule. Show the arithmetic in a table so others can challenge the inputs.
3. **Compare against current pipeline.** Lay current pipeline against required pipeline by segment and stage. Exclude or flag items that are stale, have no next step, or have close dates the stage timing makes unrealistic. Be explicit about what you excluded and why.
4. **Locate the gap.** Name where the shortfall sits: which segment, which stage, and whether it is a volume problem (not enough created), a conversion problem (created but stalling) or a timing problem (will arrive too late). The kind of gap decides which sources are relevant.
5. **Check the data before acting.** Look for explanations that are not real gaps: opportunities not yet logged, a segment definition mismatch, a source field left blank. Resolve these with the owners before planning new activity.
6. **List candidate sources.** For each gap, list ways to close it. Typical families:
   - Outbound prospecting into named accounts.
   - Marketing programs, content and events aimed at the segment.
   - Partner and referral motions.
   - Customer expansion and cross-sell.
   - Recovery of closed-lost, stalled or dormant opportunities.
   - Inbound capture improvements, such as response handling and routing.
   - Stage conversion fixes, such as qualification or follow-up discipline.
7. **Rank the sources.** Score each candidate on effort, likelihood of producing pipeline in time, dependency on other teams, and risk to existing work. Use a simple high, medium, low scale and write one line of reasoning per score. Prefer a small number of well-resourced sources over a long list of thin ones.
8. **Size the contribution.** For each chosen source, estimate the pipeline it could contribute and state the assumption behind that estimate. Check the total against the gap. If it does not cover the gap, say how much remains and either add sources or raise the shortfall to leadership as a decision.
9. **Assign owners.** Every chosen source gets one named owner, a defined first action and a start date. Confirm capacity: if an owner is already full, something else has to move, and the plan should say what.
10. **Set checkpoints.** Choose review dates spaced so there is time to react, with a leading indicator for each source that can be read at the first checkpoint (for example meetings booked, opportunities created, responses received). Define in advance what result means continue, change or stop.
11. **Document risks and triggers.** Note what could invalidate the plan, such as a conversion assumption that proves wrong, and what trigger would prompt a re-plan.
12. **Share and agree.** Walk the plan through with the owners and the revenue leader. Record decisions and any open disagreements on assumptions.

## Output format

```
PIPELINE COVERAGE GAP PLAN: [period]   Prepared by: [name/role]   Date: [date]

Assumptions and data notes
- [coverage rule, conversion assumptions, exclusions, missing data]

Target vs pipeline
| Segment | Target | Required pipeline | Current pipeline (cleaned) | Gap | Gap type (volume / conversion / timing) |

Gap by stage
| Segment | Stage | Required | Current | Shortfall |

Candidate sources (ranked)
| Rank | Source | Segment addressed | Effort | Likelihood | Dependencies | Reasoning |

Selected plan
| Source | Segment | Expected contribution | Key assumption | Owner | First action | Start date |

Coverage after plan
| Segment | Gap | Planned contribution | Remaining gap | Decision needed |

Checkpoints
| Date | Source | Leading indicator | Continue / change / stop criteria |

Risks and re-plan triggers
- ...

Open questions for leadership
- ...
```

## Quality checklist

- Target and pipeline use the same segment definitions.
- The arithmetic from target to required pipeline is visible and every input is labeled as data or assumption.
- Stale and unrealistic pipeline is flagged rather than silently counted.
- Each gap is classified as volume, conversion or timing, and the sources match that type.
- Sources are ranked with a written reason, not only a score.
- Every selected source has one named owner, a first action and a start date.
- Owner capacity has been considered, and trade-offs are stated.
- Any remaining uncovered gap is shown openly with a decision request.
- Checkpoints have leading indicators and pre-agreed continue, change or stop criteria.
- No figure appears without a stated basis.

## Common mistakes

- **Planning from total pipeline only.** A healthy overall number can hide an empty segment or a thin late stage. Always look by segment and stage.
- **Counting everything open as real.** Opportunities with no next step or impossible timing inflate coverage and delay the alarm.
- **Treating every gap as a volume problem.** If deals are stalling, more top-of-funnel activity adds to the pile without fixing the leak.
- **Long lists with no ranking.** A dozen equal ideas means none gets resourced. Choose and commit.
- **Owners without capacity.** Assigning a source to someone who is already fully loaded produces a plan on paper only.
- **Optimistic contribution estimates with no stated basis.** Write the assumption beside each estimate so it can be tested at the first checkpoint.
- **Checkpoints set too late.** If the first review happens when the period is nearly over, there is nothing left to adjust.
- **Confusing this with forecast review.** Inspecting individual deals is a different job. This plan is about creating or recovering pipeline early enough to matter.
- **Plan frozen after approval.** Conditions change. Use checkpoints to move effort from weak sources to strong ones.

## Example prompts

- "Here is our target by region and an export of open opportunities. Find where pipeline falls short and build a plan to close the gap."
- "Several reps left this period. Show how coverage changes by segment and what sources could make up the difference."
- "Our mid-market segment looks thin at the middle stages. Is it a volume or a conversion problem, and what should we do about it?"
- "Rank these candidate pipeline sources by effort and likelihood, then assign owners and checkpoint dates."
- "Review our coverage plan and tell me which assumptions are weakest and what we should check at the first checkpoint."
