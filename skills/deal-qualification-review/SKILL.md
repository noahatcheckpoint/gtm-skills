---
name: deal-qualification-review
description: "Reviews one opportunity or a whole pipeline against a qualification framework (MEDDICC by default, BANT or SPICED on request), scores each element on evidence, flags gaps and red flags, and produces the specific actions or questions that would close each gap, or a recommendation to disqualify. Use in deal reviews, before committing a deal to the forecast, or when coaching reps on qualification."
license: MIT
metadata:
  title: "Deal Qualification Review"
  category: "sales"
  author: "harmeet"
  summary: "Score a deal against MEDDICC on evidence, not optimism, and get the exact next actions that close each qualification gap."
  tags: "deal qualification, MEDDICC, BANT, deal review, sales coaching"
  version: "1.0"
  updated: "2026-10-19"
---
# Deal Qualification Review

Produces an evidence-based qualification scorecard for a deal: for each element of the framework, what is known, how it is known, how confident you can be, and what to do next. The output tells the rep and manager whether to invest more time, change the approach, or walk away.

## When to use

- Weekly or monthly deal reviews between a manager and rep.
- Before moving a deal into commit or a late pipeline stage.
- A large deal feels promising but nobody can say who signs or why now.
- Coaching a rep whose deals stall or slip.
- Reviewing a whole pipeline to find deals that should be closed out.

## What you need

Ask for these before scoring:

1. **Deal facts:** company, amount, stage, close date and its history, products.
2. **Notes:** discovery notes, call summaries, email threads, or the rep's own description.
3. **Contacts:** people engaged, their roles, and when each was last in a two-way conversation.
4. **Framework preference:** MEDDICC by default; BANT suits simpler transactional sales; SPICED suits recurring revenue motions focused on customer impact.
5. **Competitive situation** and alternatives, including doing nothing.

## Process

1. **Choose the framework and explain why.** MEDDICC elements:
   - Metrics: the quantified business impact the buyer expects.
   - Economic buyer: the person with final economic ownership of the decision and the authority to commit the budget. In larger organizations procurement approval and contract signature often sit with other people; map those separately under paper process instead of expecting one person to hold all three.
   - Decision criteria: what the buyer will judge vendors on, formally and informally.
   - Decision process: the steps, people, and dates from evaluation to selection.
   - Paper process: legal, procurement, security, and signature steps after selection, with who approves each one.
   - Identify pain: the business problem, its cause, and who feels it.
   - Champion: an insider with influence who is actively selling for you when you are not there.
   - Competition: alternatives including other vendors, internal builds, and inaction.
2. **Score each element on evidence, 0 to 3.**
   - 0 Unknown: nothing gathered.
   - 1 Assumed: rep believes it, no buyer confirmation.
   - 2 Stated: buyer said it, but not verified or not by the right person.
   - 3 Verified: confirmed by the right person and backed by an action (a meeting held, a document shared, a step completed).
3. **Ask "how do we know?" for every claim.** "The VP is the economic buyer" scores 1 if it came from the champion's guess, 3 if the VP confirmed budget ownership in a meeting.
4. **Test the champion separately.** A real champion has influence, gives you information you could not get alone, and takes action (sets up meetings, shares internal documents, pushes back internally). Someone friendly who does none of this is a coach, not a champion.
5. **Flag red flags:** single-threaded with one contact; no access to the economic buyer by mid-stage; pain that is a nice-to-have with no number attached; decision criteria written by a competitor; close date set by the seller; no paper process discussed in a late stage; repeated date slips; silence after a proposal.
6. **Check stage consistency.** Compare the score with the stage. A late-stage deal with Economic buyer, Paper process, or Champion below 2 is over-staged.
7. **Write gap-closing actions.** For each element below 3: the specific question to ask, who to ask, and the action that would prove it. For example: "Ask the champion to arrange 20 minutes with the CFO to review the business case before the proposal."
8. **Make a recommendation:** continue as is, change approach (multi-thread, re-quantify, reset timeline), move back a stage, or disqualify. Disqualifying a deal early frees time for winnable ones and is a valid, positive outcome.
9. **For pipeline reviews,** summarise across deals: average scores per element (which element is weakest across the team) and the list of deals to close out.

## Output format

```
# Qualification Review: [Deal]   Amount [ ]   Stage [ ]   Close [ ]

## Verdict
[Continue / Change approach / Move back to [stage] / Disqualify] because [one sentence]

## Scorecard (0 Unknown, 1 Assumed, 2 Stated, 3 Verified)
| Element | What we know | How we know | Score | Gap-closing action | Who | By |
|---|---|---|---|---|---|---|
| Metrics | | | | | | |
| Economic buyer | | | | | | |
| Decision criteria | | | | | | |
| Decision process | | | | | | |
| Paper process | | | | | | |
| Identify pain | | | | | | |
| Champion | | | | | | |
| Competition | | | | | | |
Total [x]/24

## Red flags
- [flag]: [evidence]

## Stage check
[consistent / over-staged, with reason]

## Questions for the next call
1.
2.
3.

## Pipeline summary (if reviewing several deals)
| Deal | Total | Weakest element | Verdict |
```

## Quality checklist

- Every score cites how the information is known.
- Scores of 3 require buyer confirmation plus an action.
- The champion is tested on influence and action, not friendliness.
- Red flags are listed with evidence.
- Stage is compared with qualification and inconsistencies are named.
- Every gap has a concrete question or action, an owner, and a date.
- The verdict is explicit, including disqualification when warranted.

## Common mistakes

- **Scoring on optimism.** "They love us" is not evidence of anything in the framework.
- **Confusing a user with the economic buyer.** The person running the evaluation rarely owns the budget.
- **Calling any friendly contact a champion.** If they have not taken a risk or an action for you, they are not one yet.
- **Ignoring the paper process until verbal yes.** Procurement and legal steps found late are the most common cause of slipped close dates.
- **Treating the framework as a form to fill in during calls.** It is a review tool; the questions should feel natural in conversation.
- **Never disqualifying.** Pipelines full of zombie deals make forecasts and coverage meaningless.
- **Forgetting "do nothing" as a competitor.** Many deals are lost to inertia, not rivals.

## Example prompts

- "Run a MEDDICC review on this deal. Here are my discovery notes and the email thread."
- "Score these eight late-stage deals and tell me which are over-staged."
- "My champion says they will get budget approved. How do I verify that?"
- "Use BANT to qualify this inbound lead from a 40-person agency."
- "What questions should I ask next call to close the gaps on economic buyer and paper process?"
