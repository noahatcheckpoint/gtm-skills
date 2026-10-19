---
name: icp-definition
description: "Use when a team needs to define or sharpen its ideal customer profile from real customer evidence. Builds firmographic, situational and behavioral criteria, separates the ICP from buyer personas, and produces a scored fit rubric plus explicit disqualifiers that sales, marketing and RevOps can apply to any account list."
license: MIT
metadata:
  title: "ICP Definition"
  category: "gtm-strategy"
  author: "noah"
  summary: "Turn your best and worst customers into an evidence-based ideal customer profile with a fit scoring rubric and hard disqualifiers."
  tags: "icp, ideal customer profile, segmentation, targeting, fit scoring"
  version: "1.0"
  updated: "2026-10-19"
---
# ICP Definition

This skill produces an ideal customer profile that a rep can apply to a single account in under a minute and that an ops team can turn into list filters and a fit score. It is built from evidence about who already buys, stays and expands, not from who the team wishes would buy.

## When to use

- The company is choosing which accounts to target for outbound, ads or partnerships.
- Win rates are low or sales cycles are long and nobody can say which deals are worth chasing.
- Marketing and sales disagree about what a "good lead" is.
- A new product, segment or region is being added and the existing ICP may not transfer.
- The current ICP is a single sentence like "B2B SaaS companies with 50 to 500 employees" and nothing more.

Do not use this skill to describe individual buyers. Personas (the humans inside the account) are a separate layer that sits on top of the ICP.

## What you need

Ask for these before drafting. If the user has no data, say so plainly and label the output a hypothesis to be tested.

1. **Best customers:** 5 to 15 accounts the team would clone if it could. For each: industry, size, region, deal size, time to close, retention or expansion.
2. **Worst customers:** 3 to 10 accounts that churned fast, needed heavy support, or never adopted.
3. **Lost deals:** the most common loss reasons over the last two to four quarters.
4. **The problem solved:** in the customer's words if possible (call notes, reviews, survey answers).
5. **Commercial constraints:** minimum viable deal size, regions you can serve, languages, compliance limits, integrations you require.
6. **Data available:** what you can actually filter on in your CRM or list sources. A criterion you cannot observe is not a usable criterion.

## Process

1. **Sort the evidence.** Put best, worst and lost accounts side by side. Look for attributes that appear in most best accounts and rarely in worst ones. Those are candidate criteria. Attributes present in both groups are noise, however intuitive they feel.
2. **Layer the criteria.** Organize what you found into three layers:
   - *Firmographic* (observable from outside): industry or vertical, employee band, revenue band, geography, ownership model, business model.
   - *Situational* (true right now): a trigger or state that creates urgency, such as a new leader in the buying function, a recent funding round, a migration, a regulatory deadline, a hiring surge in a specific team.
   - *Technographic and behavioral:* tools they run that you integrate with or replace, process maturity, how they buy (procurement-led, founder-led, committee).
3. **Find the pain link.** For every criterion, write one line explaining why it makes the problem more painful or the solution more valuable. If you cannot write that line, drop the criterion. "Series B" is useless on its own; "Series B, so the board now expects a repeatable pipeline number" is a criterion.
4. **Write disqualifiers.** List hard no's: conditions under which you will not win or the customer will not succeed. Disqualifiers save more rep time than qualifiers do, and they are where the worst-customer list pays off.
5. **Build the fit score.** Convert criteria into a weighted rubric totaling 100 points. Weight by how strongly each criterion separated best from worst accounts, not by how easy it is to measure. Set tiers: Tier 1 (strong fit), Tier 2 (workable), Tier 3 (nurture only).
6. **Test against accounts the weights never saw.** Set weights on one group of accounts, then score a separate group: a held-back slice of customers and lost deals, or accounts won and lost after the period you analyzed. Report the misses in both directions (good customers scored Tier 3, poor ones scored Tier 1) and the hit rate per tier. Change weights only when a miss reveals a pattern across several accounts; keep genuine exceptions as documented exceptions rather than bending the rubric until every account fits, which only memorizes a small sample. With very few accounts, say that the rubric is a hypothesis and name the cohort that will validate it.
7. **Size the result.** Estimate how many accounts match Tier 1. Heuristic: if fewer than a few hundred accounts qualify for a team with several reps, the ICP is probably too narrow for outbound; if tens of thousands qualify, it is probably not specific enough to change behavior.
8. **Name the personas inside.** List the two or three roles that typically initiate, champion and sign, so the ICP hands off cleanly to persona and messaging work.

## Output format

```
ICP: [one-line headline a rep can repeat]

Why these accounts win: [2-3 sentences linking the profile to the problem]

Criteria
| Layer | Criterion | Why it matters | How to observe it | Weight |
|---|---|---|---|---|
| Firmographic | ... | ... | ... | 20 |
| Situational | ... | ... | ... | 25 |
| Technographic | ... | ... | ... | 15 |
| ... | ... | ... | ... | ... |
Total: 100

Tiers
- Tier 1 (75+): [what the team does with these]
- Tier 2 (50-74): [...]
- Tier 3 (below 50): [...]

Disqualifiers (any one = do not pursue)
- ...

Validation
| Account | Group (best/worst) | Score | Tier | Matches expectation? |

Buying roles: [initiator], [champion], [economic buyer]
Estimated Tier 1 count: [number or range, with source]
Open questions / assumptions to test: ...
```

## Quality checklist

- Every criterion has a stated link to the customer's pain and a way to observe it.
- At least three disqualifiers, each traceable to a worst-customer or lost-deal pattern.
- The rubric was validated on accounts not used to set the weights, with misses in both directions reported.
- Firmographics are not the only layer; at least one situational trigger is included.
- The output says clearly which parts are evidence and which are assumptions.
- No criterion depends on data the team cannot get.

## Common mistakes

- **Describing the total market instead of the best slice.** An ICP that fits everyone guides no one. It should exclude most of the market.
- **Building from aspiration.** Teams often write the ICP for the enterprise logos they want rather than the mid-market accounts that actually renew. Start from retention and expansion data, not from logo prestige.
- **Ignoring the worst customers.** Churned and painful accounts teach more about disqualifiers than happy ones teach about fit.
- **Mixing account and person.** "VP of Sales at a fintech" blends ICP and persona. Keep the account profile and the buying roles separate.
- **Unobservable criteria.** "Values innovation" cannot be filtered or scored. Translate it into a signal, such as a recent tool adoption or a new team being built.
- **Never revisiting.** Re-run the analysis at least twice a year, or after any pricing, product or segment change.

## Example prompts

- "Here are our 12 best customers and 6 that churned. Build our ICP with a scoring rubric."
- "Our ICP is 'mid-market SaaS'. Make it specific enough that SDRs can disqualify accounts on their own."
- "We are expanding into DACH. Check whether our current ICP transfers and what to change."
- "Turn this ICP into a 100-point fit score with tiers and disqualifiers."
- "Sales says our marketing leads are bad. Help us define what a good-fit account actually is."
