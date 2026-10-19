---
name: crm-data-hygiene-audit
description: "Runs a structured CRM data quality audit across completeness, duplicates, validity, consistency, freshness and ownership, scores each area, estimates business impact and produces a prioritised cleanup and prevention plan. Use before a scoring, routing or reporting project, after a migration, or when reps and leaders stop trusting CRM data."
license: MIT
metadata:
  title: "CRM Data Hygiene Audit"
  category: "revops-crm"
  author: "harmeet"
  summary: "Score CRM data quality across six dimensions, size the business impact, and get a prioritised fix-and-prevent plan."
  tags: "CRM data quality, deduplication, data hygiene, RevOps, data governance"
  version: "1.0"
  updated: "2026-10-19"
---
# CRM Data Hygiene Audit

Produces a scored audit of CRM data quality, a short list of the problems that actually cost revenue, and a plan that fixes existing records and stops new bad data from entering. The aim is not a perfect database; it is data good enough for routing, scoring, segmentation, and reporting to work.

## When to use

- Before building lead scoring, routing, territory planning, or attribution (all of them depend on clean fields).
- After a CRM migration, a merger of databases, or a large list import.
- Reports disagree, reps keep their own spreadsheets, or bounce rates are rising.
- Annually, as routine maintenance.

## What you need

Ask for these. The audit can run on summary counts if raw exports are not shareable.

1. **Objects in scope:** contacts, companies or accounts, deals, and any custom objects.
2. **Record counts** and, ideally, an export or field-level fill-rate report.
3. **Critical fields** for your processes: the ones routing, scoring, and reporting rely on.
4. **Data sources** feeding the CRM: forms, imports, enrichment, integrations, manual entry.
5. **Known symptoms:** duplicate complaints, bounce rates, misrouted leads, report disputes.
6. **Ownership:** who is allowed to create, edit, merge, and delete records.

## Process

1. **List the business processes that consume data** (routing, scoring, segmentation, forecasting, billing handoff) and the fields each one needs. These become the critical fields. A field nobody uses is not worth cleaning.
2. **Measure six dimensions for each critical field or object:**
   - Completeness: share of records where the field is filled.
   - Validity: values in an allowed format or picklist (valid email syntax, ISO country, real phone format).
   - Uniqueness: duplicate candidates, then confirmed duplicates. A shared email or domain only nominates a pair: shared inboxes (info@, sales@), reused addresses, subsidiaries and multi-brand domains collide legitimately. Confirm with composite keys (email plus name, domain plus legal entity and country) and report candidate and confirmed rates separately.
   - Consistency: the same fact recorded the same way ("US," "USA," "United States").
   - Freshness: share of records updated or verified in the last 12 months; bounce rate on recent sends as a proxy.
   - Ownership: records with no owner, or owned by inactive users.
3. **Use heuristics to grade each area** (adjust to your context):
   - Green: critical field completeness above 90%, confirmed duplicates under 2%, fewer than 5% unowned.
   - Amber: completeness 70 to 90%, duplicates 2 to 5%.
   - Red: completeness below 70%, duplicates above 5%, or any critical process failing because of data.
   Freshness erodes continuously as people change jobs and companies restructure, so some staleness is normal, not negligence. Published annual decay figures vary widely by market, role and how decay is defined, so measure your own rate (hard bounces, job-change flags, failures when re-verifying a random sample) instead of borrowing a benchmark.
4. **Find the sources of bad data.** For each problem, trace where it enters: a form with a free-text country field, an integration that creates contacts without checking for duplicates, an import with no mapping rules. Fixing the source matters more than fixing the records.
5. **Size the impact.** Translate problems into consequences: leads unrouted per month, emails bouncing, accounts double-worked, revenue reported under the wrong segment. Leaders fund impact, not completeness percentages.
6. **Prioritise with an impact versus effort grid.** Quick wins first (picklists replacing free text, a duplicate rule on creation), then structured cleanups (merges, enrichment of key fields), then governance.
7. **Define merge rules before merging.** Which record survives (oldest, most active, owned by a current rep), which field values win, and what must never be overwritten (owner of an open deal, lifecycle dates). Treat automated matches as candidates: merge automatically only above a high-confidence threshold on composite identifiers, send the rest to human review, respect account hierarchy (a subsidiary is not a duplicate of its parent), and exclude records with open deals, active contracts or consent history from automatic merging. Test merges on a sample first.
8. **Plan prevention:** required fields at creation, validation rules, picklists, duplicate checks on every entry point, owner reassignment when users leave, and a retention policy set per object and lifecycle status. Inactivity alone never justifies archiving: exclude active customers, long-cycle accounts, and records you must keep for contracts, consent evidence or legal retention, check which reports and attribution depend on a record, and keep its audit history when it is archived.
9. **Set ongoing monitoring:** a monthly data quality dashboard with the same metrics, so the score is tracked rather than re-audited from scratch.

## Output format

```
# CRM Data Hygiene Audit: [Company]   Date [ ]   Records in scope [ ]

## Executive summary
Overall grade [ ]. Top three problems and their business impact.

## Scorecard
| Object | Dimension | Metric | Value | Grade | Process affected |
|---|---|---|---|---|---|

## Critical field fill rates
| Field | Used by | Fill rate | Valid rate | Grade |

## Root causes
| Problem | Entry point | Fix at source |

## Impact estimate
[quantified consequences]

## Remediation plan
| Priority | Action | Type (quick win / cleanup / governance) | Owner | Effort | Due |

## Merge rules
[survivor logic, field precedence, protected fields]

## Prevention controls
[validation, required fields, duplicate checks, retention policy with exclusions]

## Monitoring
Metrics, cadence, threshold that triggers action.
```

## Quality checklist

- Critical fields are tied to named processes.
- All six dimensions are measured or explicitly marked as not measurable.
- Each problem has a root cause at an entry point, not just a symptom.
- Impact is expressed in business terms.
- Duplicate figures separate candidates from confirmed duplicates; ambiguous matches go to human review.
- Merge rules exist before any merge action is recommended.
- Archiving rules differ by object and status and list their exclusions.
- The plan includes prevention, not only cleanup.
- Monitoring metrics match the audit metrics.

## Common mistakes

- **Cleaning everything.** Hundreds of unused fields do not need fixing; archiving or hiding them is often the better move.
- **Mass merging without survivor rules.** Merges are hard to undo and can wipe owners, dates, and deal links.
- **Fixing records but not entry points.** The same duplicates return within a month.
- **Treating decay as a one-time problem.** People change jobs constantly; freshness needs a recurring process.
- **Free-text fields for anything used in rules.** Country, industry, and lead source must be picklists.
- **Deleting instead of archiving.** Deleted records take their history with them, including attribution.
- **No owner for data quality.** Without a named person and a monthly metric, quality drifts back.

## Example prompts

- "Audit our CRM data quality. Here is a fill-rate report for contacts and companies."
- "We are about to build lead routing. What data needs fixing first?"
- "Write duplicate merge rules for contacts and accounts that will not break deal ownership."
- "Our email bounce rate hit 9%. Plan a data hygiene cleanup and prevention process."
- "Create a monthly data quality dashboard spec for our RevOps team."
