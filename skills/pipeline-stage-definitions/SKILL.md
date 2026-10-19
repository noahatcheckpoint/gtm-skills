---
name: pipeline-stage-definitions
description: Writes deal pipeline stage definitions anchored on buyer-verified exit criteria, with required fields, evidence per stage, stall thresholds and probability guidance. Use when stages mean different things to different reps, when forecasts miss because deals are over-staged, or when designing a pipeline for a new sales motion.
license: MIT
metadata:
  title: "Pipeline Stage Definitions"
  category: "revops-crm"
  author: "esther"
  summary: "Define deal stages by what the buyer has done, not what the rep has done, with exit evidence, required fields and stall rules."
  tags: "pipeline stages, exit criteria, deal hygiene, sales process, forecasting"
  version: "1.0"
  updated: "2026-10-19"
---
# Pipeline Stage Definitions

Produces a stage guide that makes "this deal is in Stage 3" mean the same thing for every rep and manager. Each stage is defined by a buyer action that can be verified, the evidence required to claim it, the fields that must be filled, and how long a deal may sit there before it is reviewed.

## When to use

- Two reps with similar deals put them in different stages.
- Late-stage pipeline looks healthy but deals keep slipping or dying.
- Win rates by stage are flat, which means stages do not carry information.
- You are adding a new motion (partner-led, expansion, self-serve upgrade) that does not fit the current pipeline.
- Leadership wants stage-weighted forecasts and the numbers are unreliable.

## What you need

Ask for these before drafting:

1. **Sales motion:** average deal size, typical sales cycle length, number of stakeholders, procurement involvement.
2. **Current stages** and any written definitions.
3. **Real buying steps:** what customers actually do between first meeting and signature (security review, pilot, business case, legal).
4. **Historic data if available:** conversion between stages and median days in each.
5. **Qualification framework in use,** if any (for example BANT, MEDDICC, SPICED).
6. **Pain points:** where deals stall, where forecasts break.

## Process

1. **Map the buyer's journey before the seller's.** List the decisions the customer must make, in order: agree there is a problem worth solving, agree on what a solution must do, choose a vendor, get approval to spend, sign. Stages should mirror these decisions.
2. **Keep the stage count small.** Five to seven open stages suits most B2B motions. More stages create false precision; fewer hide where deals stall.
3. **Write exit criteria as buyer actions.** Weak: "demo delivered," "proposal sent." Strong: "buyer confirmed the problem and its cost in their own words," "economic buyer agreed to evaluate a proposal," "buyer shared their procurement steps and dates." A seller can always send a proposal; only a buyer can react to it.
4. **Attach evidence to each exit.** What would a manager look at to verify it? A recap email the buyer replied to, a scheduled meeting with the economic buyer, a mutual action plan, a security questionnaire received.
5. **Define required fields per stage.** Early: pain, source, primary contact. Mid: decision criteria, economic buyer, competitor, amount estimate. Late: paper process, signer, legal contact, close date with reason. Make the CRM block advancement when they are empty, if your system supports it.
6. **Set stall thresholds.** Use roughly 1.5 to 2 times the median days in stage as a review trigger. A stalled deal is not automatically dead, but it must be re-justified or moved back.
7. **Allow backward movement.** If the champion leaves or the budget is frozen, the deal moves back. A pipeline that only moves forward ends up overstating late-stage value.
8. **Define closed lost properly.** Required loss reason (from a fixed list), competitor if any, and the stage it was lost from. Add a "no decision" reason; it is often the biggest competitor.
9. **Add probability guidance only after defining evidence.** Use historic stage-to-win conversion where you have it. If not, give provisional probabilities and mark them for recalibration after two quarters.
10. **Produce a one-page rep cheat sheet** alongside the full guide. Reps will not read a long document mid-call.

## Output format

```
# Pipeline Stage Guide: [Motion]   Version [x]   Owner [name]

## Stage overview
| # | Stage | Buyer decision reached | Exit criteria (buyer action) | Evidence | Required fields | Stall after (days) | Probability |
|---|---|---|---|---|---|---|---|

## Stage detail
### [Stage name]
- Purpose:
- Enters when:
- Exits when:
- Evidence required:
- Typical rep activities (not exit criteria):
- Moves back if:

## Closed lost
Reasons list: [..., No decision]
Required: reason, competitor, stage lost from.

## Hygiene rules
[close date changes need a reason, no stage skipping without manager note, stall reviews weekly]

## Rep cheat sheet
[one line per stage: "Move to X when the buyer has ..."]

## Metrics to track
Stage conversion, median days per stage, stage skips, backward moves, slip rate.
```

## Quality checklist

- Every exit criterion is something the buyer did, not the seller.
- Each stage names the evidence a manager can inspect.
- Required fields are listed per stage and get stricter later in the pipeline.
- Stall thresholds are set and tied to a review action.
- Backward movement is allowed and described.
- Closed lost includes "no decision" and a required reason.
- Probabilities are either historic or clearly marked provisional.
- A one-page cheat sheet is included.

## Common mistakes

- **Stages named after seller activities.** "Demo" and "Proposal" tell you what the rep did, not whether the buyer moved.
- **Stage-weighted forecasting on unverified stages.** Multiplying inflated stages by probabilities produces a confident wrong number.
- **Close dates nobody questions.** A close date pushed three times without a reason is a signal, not a typo.
- **No "no decision" loss reason.** Teams blame competitors for deals that died of inertia.
- **One pipeline for every motion.** Renewals, expansions, and new business have different buying steps.
- **Probability set by optimism.** Without history, label numbers as provisional and recalibrate.
- **Definitions that live in a slide deck** instead of in the CRM help text where reps see them.

## Example prompts

- "Rewrite our pipeline stages so each one is defined by a buyer action. Here are our current six stages."
- "Design a pipeline for an enterprise motion with security review and procurement."
- "What required fields should block a deal from moving to Negotiation?"
- "Our late-stage pipeline keeps slipping. Help me set stall rules and exit evidence."
- "Create a separate pipeline for expansion deals with existing customers."
