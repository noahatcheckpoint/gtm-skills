---
name: tam-sizing
description: "Use when a team needs a defensible estimate of its total addressable, serviceable and obtainable market for planning, fundraising, territory design or deciding whether a segment is worth entering. Builds a bottom-up account-count model, sanity-checks it top-down, and shows every assumption so the number can be challenged and updated."
license: MIT
metadata:
  title: "TAM Sizing"
  category: "gtm-strategy"
  author: "harmeet"
  summary: "Size TAM, SAM and SOM bottom-up from account counts and contract values, with a top-down cross-check and every assumption exposed."
  tags: "tam, sam, som, market sizing, planning"
  version: "1.0"
  updated: "2026-10-19"
---
# TAM Sizing

This skill produces a market size the user can defend line by line: how many accounts exist, how many you can serve, what each is worth per year, and how much of that a realistic sales motion can win. The method is bottom-up first, top-down as a check.

## When to use

- Building an annual plan, a board deck or a fundraising narrative.
- Deciding whether to enter a new vertical, region or company-size band.
- Designing territories and needing to know how many accounts each rep would own.
- Someone quoted a giant analyst number and you need something grounded.

## What you need

Ask for these. Where the user has no figure, propose a range and mark it as an assumption.

1. **ICP definition:** industries, size bands, regions, any must-have technology or situation.
2. **Pricing:** current annual contract value by segment, or the pricing model (per seat, per usage, flat).
3. **Account count sources:** where they can count companies (a company database, industry association lists, government business registries, a CRM export).
4. **Current traction:** customers, win rate, average sales cycle, opportunities created per rep per quarter.
5. **Capacity:** number of quota-carrying reps now and planned, and any channel partners.
6. **Purpose:** fundraising, planning or segment choice changes how conservative to be.

## Process

1. **Define the unit.** Decide what you are counting: companies, sites, business units, or seats. Count at the level where a purchase decision happens. If one enterprise buys separately per country, count country entities.
2. **Segment before you multiply.** Split the market into 3 to 6 segments by size band or vertical. Contract values differ widely between a 50-person company and a 5,000-person company; one blended average hides that and inflates the total.
3. **Count accounts per segment.** Use at least one countable source and note it. If sources disagree, show the range. Heuristic: if two sources differ by more than 2x, the definition is probably ambiguous; tighten it before moving on.
4. **Set contract value per segment.** Use actual ACV from current customers where possible. For segments with no customers yet, estimate from pricing logic (seats times price, expected usage) and mark it as an assumption.
5. **Calculate TAM.** Accounts times ACV, summed across segments. This is the annual revenue if every account that fits the definition bought at your price.
6. **Narrow to SAM.** Remove what you cannot serve today: unsupported regions or languages, missing integrations, compliance gaps, segments the product does not fit. State each filter and how many accounts it removes.
7. **Model SOM from capacity, not a percentage.** First name the measure: new bookings per year, or ARR at the end of year three (usually the more useful one). Then build it year by year: ramped rep capacity (hires times months productive, with new reps at partial output while they ramp), opportunities per ramped rep, win rate, and sales-cycle lag (deals created late in a year close the next one). Add inbound and partner deals only where they are not already counted in rep opportunities, then carry the customer base forward with churn and expansion. Compare the year-three figure to SAM. There is no universal ceiling on penetration: check the implied share against your own win history, the number of competitors, and how mature the category is, and challenge any input that drives an unusually high share.
8. **Cross-check top-down.** Take a published industry spend figure and filter it down to your category, segments, regions and use case so it describes the same TAM or SAM. Do not apply your expected market share here; achievable share belongs only in the SOM model. If top-down and bottom-up differ by more than about 3x, explain why or revisit the assumptions. Bottom-up wins ties because it is tied to accounts you can name.
9. **Run sensitivity.** Show what happens to SAM and SOM if ACV, win rate or account count moves 25 percent either way. Point out which assumption the answer is most sensitive to.

## Output format

```
Market sizing: [scope, date, currency]

Unit counted: [company / entity / site] because [reason]

Segment model
| Segment | Definition | Accounts | Source | ACV | ACV basis | TAM |
|---|---|---|---|---|---|---|
| ... | ... | ... | ... | ... | actual / assumed | ... |
| Total | | | | | | ... |

SAM filters
| Filter | Accounts removed | Reason |
SAM: [accounts] x [ACV by segment] = [value]

SOM (capacity-based; measure: [ARR at end of year 3 / annual bookings])
| Year | Ramped reps | Opps per ramped rep | Win rate | Cycle lag | Incremental inbound / partner | Churn / expansion | Value |
- SOM: [value]  ([x]% of SAM, compared with [win history / competitor count])

Top-down cross-check: [method, figure, gap vs bottom-up, explanation]

Sensitivity
| Assumption | -25% | Base | +25% |

Most sensitive assumption: ...
Assumptions to verify: ...
```

## Quality checklist

- Every account count names its source and date.
- ACV is segmented, and each value is labeled actual or assumed.
- SAM filters are listed individually with their effect.
- SOM names its measure and is built year by year from ramped capacity, conversion, cycle timing and churn, not a flat share.
- The top-down check filters spend to the same scope and contains no market-share assumption.
- A top-down figure is used only as a check, with the gap explained.
- The sensitivity table identifies the assumption that matters most.

## Common mistakes

- **Leading with a top-down analyst number.** A large industry figure says little about the accounts you can reach. Investors and executives discount it.
- **One average contract value.** Blending small and large customers inflates TAM and misleads territory planning.
- **Counting the wrong unit.** Counting parent companies when subsidiaries buy independently (or the reverse) can shift the total by an order of magnitude.
- **SOM as a percentage of SAM.** "We'll get 5 percent" has no mechanism. Tie it to reps, pipeline and win rate.
- **Hiding assumptions.** A number nobody can trace cannot be updated when the business learns something new.
- **Never refreshing.** Re-run after pricing changes, new regions, or a major product release.

## Example prompts

- "Size the market for our HR compliance tool in the UK and Germany, bottom-up."
- "We charge per seat. Help me build TAM, SAM and SOM for companies with 200 to 2,000 employees."
- "Our deck says the market is 40 billion. Build a bottom-up version I can defend."
- "Should we enter the healthcare vertical? Size it and compare it to our current segment."
- "How many accounts would each rep own if we hire 6 AEs? Start from the serviceable market."
