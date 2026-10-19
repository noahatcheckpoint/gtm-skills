---
name: attribution-model-design
description: "Designs a B2B marketing attribution approach: the business questions it must answer, the touchpoint and stage data required, the choice of model (first touch, last touch, position-based, W-shaped, data-driven) with self-reported attribution and incrementality tests alongside, and a reporting spec with known limits. Use when leadership asks which channels drive pipeline, when budgets are being reallocated, or when attribution reports are distrusted."
license: MIT
metadata:
  title: "Attribution Model Design"
  category: "analytics"
  author: "harmeet"
  summary: "Choose and specify an attribution approach that answers real budget questions, with the data rules, model choice and honest limits."
  tags: "marketing attribution, multi-touch attribution, self-reported attribution, incrementality, pipeline reporting"
  version: "1.0"
  updated: "2026-10-19"
---
# Attribution Model Design

Produces an attribution design that starts from the decisions it must support, not from a model menu. The deliverable covers the questions to answer, the data rules that make answers trustworthy, the model (or combination) to use, how self-reported attribution and lift tests fit in, and a reporting spec that states its own limits.

## When to use

- Leadership asks "which channels create pipeline?" and current reports cannot answer.
- Marketing budget is being reallocated across channels or programmes.
- Different teams report different "sourced pipeline" numbers.
- You are moving from last touch reporting to something more complete.
- Dark social, podcasts, communities, or word of mouth matter but never show up in reports.

## What you need

Ask for these before designing:

1. **Decisions to support:** budget allocation across channels, campaign optimisation, sales and marketing credit, board reporting.
2. **Sales motion:** sales cycle length, number of stakeholders, inbound versus outbound mix, deal volume per quarter.
3. **Data available:** campaign and source tracking on contacts, touchpoint history, opportunity contact roles, stage dates, ad platform data.
4. **Current reporting:** what is reported today and why it is distrusted.
5. **Volume:** opportunities and closed won deals per quarter (data-driven models need a lot).
6. **Channels in play,** including ones hard to track (events, partners, communities, content syndication).

## Process

1. **Write the questions first.** For example: "Which channels open new accounts?" (first touch helps), "What converts engaged accounts into opportunities?" (opportunity creation touches help), "If we cut this channel, would pipeline fall?" (a causal question: answer it with an incrementality test or a careful quasi-experiment, never with the model). Each question may need a different view.
2. **Define the conversion events.** Usually: first touch, lead created, opportunity created, closed won. Agree that pipeline and revenue are attributed at opportunity level, using contacts linked to the opportunity, not just the person who filled in a form.
3. **Set data rules.** Standard naming for source, medium, and campaign; a fixed channel taxonomy (paid search, paid social, organic search, direct, referral, email, events, partner, outbound, other); tracking parameters on every link you control; and rules for offline touches (events, sales meetings) to be logged as touchpoints. Without consistent capture, any model just redistributes bad data.
4. **Choose the model or models.**
   - First touch: good for "what brings new accounts in"; blind to everything after.
   - Last touch: simple, but over-credits bottom-funnel channels like branded search and direct.
   - Position-based (often 40/20/40): credits opening and converting touches; the weights are a convention, not a measurement.
   - W-shaped: gives the largest shares to three milestones (the opening touch, the touch that created the lead, the touch that created the opportunity) and spreads the rest; needs reliable stage dates.
   - Data-driven: learns weights from your history; needs high volume and clean data, and still shows correlation, not cause.
   For most mid-market B2B teams, a position-based or W-shaped model as the main view, with first touch shown alongside, is a sensible start. Show more than one view so nobody mistakes one model for the truth.
5. **Add self-reported attribution.** A "How did you hear about us?" field on demo and signup forms captures podcasts, communities, peer recommendations, and other channels software tracking misses. Use a short list of channels plus an "Other" free-text option so answers can be counted. Decide required versus optional by testing: compare form completion rate and answer quality between the two before making it mandatory. Categorise answers monthly and compare with the software view.
6. **Add incrementality tests for big budget questions.** Randomized holdouts or geographic experiments are the preferred way to learn whether spend causes pipeline. When randomizing is not feasible, use a quasi-experimental design with its assumptions stated: matched markets, interrupted time series around a channel pause, difference-in-differences against a comparable region or segment, or a synthetic control. Attribution models cannot answer this.
7. **Define account versus contact logic.** In buying committee sales, roll touches up to the account and opportunity; decide the lookback window (often 90 to 180 days before opportunity creation, matched to your cycle).
8. **Specify reports.** Pipeline and revenue by channel under each model, self-reported source breakdown, cost per opportunity by channel, and trend over time. State the limits on the report itself.
9. **Plan governance.** An owner, a data quality check each month (share of opportunities with no touchpoints, share in "other"), and a review when the model or taxonomy changes.

## Output format

```
# Attribution Design: [Company]   Owner [ ]   Version [ ]

## Questions this must answer
| Question | Decision it informs | View that answers it |

## Conversion events and lookback
[events, opportunity-level attribution, lookback window]

## Data rules
Channel taxonomy: [list]
Naming convention: [source / medium / campaign rules]
Offline touch logging: [rules]

## Model choice
Primary view: [model] because [reason]
Secondary views: [models]
Not using: [model] because [reason]

## Self-reported attribution
Field, placement, categorisation process, review cadence.

## Incrementality tests planned
| Channel | Test type | Duration | Success metric |

## Reports
| Report | Audience | Cadence | Stated limits |

## Data quality monitoring
[% opps with no touches, % in Other, threshold for action]
```

## Quality checklist

- Every report maps to a stated business question and decision.
- Attribution is at opportunity level with contacts linked to the deal.
- A channel taxonomy and naming convention are defined.
- The model choice is justified and at least two views are shown.
- Self-reported attribution is included.
- Causal questions are routed to experiments or stated-assumption quasi-experiments, not to the model.
- The self-reported field uses a controlled list plus "Other", and required versus optional is decided by a completion test.
- Data quality metrics and an owner are named.

## Common mistakes

- **Choosing a model before agreeing the questions.** The model debate never ends because people want different answers.
- **Treating any model as causal.** Attribution shows which touches were present, not which ones made the difference.
- **Form-filler only attribution.** In B2B, the person who downloads an asset is often not the buyer. Attribute through opportunity contact roles.
- **Ignoring offline and dark channels.** Events, podcasts, and referrals vanish from software reports; self-reported data brings them back.
- **Data-driven models on thin data.** With a few dozen deals per quarter, learned weights are noise.
- **Inconsistent campaign naming.** One channel split across fifteen spellings ruins every model.
- **Using attribution to settle credit fights.** Shared pipeline goals reduce the pressure to win the attribution argument.

## Example prompts

- "Design an attribution approach for our B2B SaaS. We close about 60 deals a quarter with a 4-month cycle."
- "Our board wants sourced pipeline by channel. What model should we use and what are its limits?"
- "Compare first touch, W-shaped and data-driven attribution for our situation."
- "Set up self-reported attribution and explain how to reconcile it with our software reports."
- "How do we test whether our paid social spend actually creates pipeline?"
