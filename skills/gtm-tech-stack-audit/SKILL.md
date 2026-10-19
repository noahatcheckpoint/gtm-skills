---
name: gtm-tech-stack-audit
description: Audits the go-to-market tool stack (CRM, marketing automation, sales engagement, data, analytics, CS tools) for adoption, overlap, integration gaps and total cost including admin time, then recommends keep, consolidate, replace or retire with a renewal calendar. Use before budget planning, a renewal cycle, a CRM change, or when the team complains about too many tools.
license: MIT
metadata:
  title: "GTM Tech Stack Audit"
  category: "revops-crm"
  author: "noah"
  summary: "Inventory every GTM tool, score adoption, overlap and true cost, and decide what to keep, consolidate, replace or retire."
  tags: "tech stack audit, RevOps tools, software spend, tool consolidation, integrations"
  version: "1.0"
  updated: "2026-10-19"
---
# GTM Tech Stack Audit

Produces a full inventory of the tools your marketing, sales, and customer teams pay for, an honest score for each, a map of how data flows between them, and a decision per tool with the savings and risks attached. The goal is a stack that fewer people have to maintain and more people actually use.

## When to use

- Annual budget planning or ahead of a cluster of renewals.
- Spend on GTM software has grown faster than headcount.
- Reps juggle many tabs and still keep notes in spreadsheets.
- Data does not match between systems, or integrations break silently.
- A new leader is inheriting a stack and needs to understand it quickly.

## What you need

Ask for these before auditing. Partial data is fine; mark gaps.

1. **Tool list:** name, category, owner, annual cost, contract end date, notice period, seats purchased.
2. **Usage evidence:** active users in the last 30 days, or admin console login reports.
3. **Integrations:** what connects to what, and whether the sync is native, middleware, or manual export.
4. **Team context:** headcount by function, main GTM motions, upcoming changes (new segment, new CRM, hiring plan).
5. **Pain points:** the complaints you hear about tools, data, and workflows.

## Process

1. **Build the inventory by category.** Group tools into a standard map so overlaps become visible: CRM, marketing automation, sales engagement, data and enrichment, conversation intelligence, scheduling, intent and website identification, analytics and BI, CS platform, content and enablement, contract and quoting, integration middleware. Include tools bought on personal cards; they are often the most redundant.
2. **Score each tool on five dimensions (1 to 5):**
   - Utilization: measured in the unit the tool's value comes in. For seat-based user tools, active users divided by paid seats (below about half is a warning sign; use quarterly active users for seasonal tools). For API, middleware, enrichment and admin-only tools, use records processed, workflows completed or credits consumed versus purchased.
   - Overlap: does another tool already do the core job?
   - Integration: does it write back to the CRM cleanly, or create an island of data?
   - Outcome link: the result the category exists for, even roughly. Pipeline or retention for revenue tools; hours saved, errors avoided or processes kept running for infrastructure and admin tools; risk controlled for compliance and security tools. Do not score a tool low only because it cannot be attributed to revenue.
   - Switching cost: data migration, retraining, and workflow rebuild effort.
3. **Calculate total cost of ownership.** License plus admin hours per month (at a loaded hourly rate) plus middleware costs plus any agency fees. Admin time is often the largest hidden cost, especially for tools that need constant rule maintenance.
4. **Map the data flow.** Draw the path of a lead from first touch to closed won to renewal, noting which system is the source of truth for each key field (owner, lifecycle stage, revenue). Two systems both claiming to own a field is a red flag.
5. **Identify the workflow gaps.** Where do people export to spreadsheets, re-key data, or switch tools to complete one job? Those are the places where a tool is missing, misconfigured, or unloved.
6. **Decide per tool:**
   - Keep: high utilization, unique job, integrated.
   - Optimise: right tool, poor configuration or training.
   - Consolidate: core job covered by another tool you already pay for.
   - Replace: needed job, wrong tool.
   - Retire: no clear job or owner.
7. **Check the risks before recommending a cut.** Who loses what workflow? What data must be exported first? Is anything contractually locked? Which reports or automations depend on it?
8. **Build the renewal calendar.** List decision dates as notice deadline minus the time needed to evaluate (usually 60 to 90 days before renewal). Missed notice windows are where most savings disappear.
9. **Sequence the change.** One consolidation at a time, starting with the highest savings and lowest switching cost. Assign an owner to each and a success metric (adoption after 60 days, admin hours saved).

## Output format

```
# GTM Tech Stack Audit: [Company]   Date [ ]

## Summary
Total annual spend [ ], tools [n], estimated savings [ ], top three recommendations.

## Inventory and scores
| Tool | Category | Owner | Annual cost | Utilization measure and value | Utilization score | Overlap | Integration | Outcome link | Switching cost | TCO | Decision |
|---|---|---|---|---|---|---|---|---|---|---|---|

## Overlap map
| Job to be done | Tools doing it | Recommended single owner tool |

## Source of truth by field
| Field | Owning system | Conflicts |

## Workflow gaps
[where people leave the stack and why]

## Recommendations
| Tool | Decision | Savings | Risk | Dependencies | Owner |

## Renewal calendar
| Tool | Renewal date | Notice deadline | Decision needed by |

## Sequencing plan
[ordered steps with success metrics]

## Assumptions and data gaps
```

## Quality checklist

- Every tool appears in a category, including card-paid tools.
- Utilization uses a measure that fits the tool's category (seats, records, workflows, credits), or is marked unknown.
- TCO includes admin time and middleware, not just license.
- Each key field has one source of truth, and conflicts are named.
- Every retire or consolidate decision lists the workflows and data affected.
- The renewal calendar shows notice deadlines and decision dates.
- Recommendations are sequenced with owners and success metrics.

## Common mistakes

- **Judging tools by license cost alone.** A cheap tool that needs ten admin hours a month is expensive.
- **Cutting without checking dependencies.** Retiring a tool can silently break a report, a form, or a routing rule.
- **Buying a tool to fix a process problem.** If nobody follows the stage definitions, a new forecasting tool will not help.
- **Two systems owning the same field.** Sync conflicts overwrite good data with stale data.
- **Missing notice windows.** Auto-renewals lock in another year of a tool you meant to drop.
- **Consolidating everything onto one suite** without checking whether the suite's version of the feature is good enough for the team that relies on it.
- **No adoption plan for the tools you keep.** Low usage is often a training problem, not a tool problem.

## Example prompts

- "Audit our GTM stack. Here is a list of 23 tools with costs, seats and renewal dates."
- "We pay for three tools that seem to do the same thing. Help me decide which to keep."
- "Map where each key field lives across our CRM, marketing automation and CS platform."
- "Build a renewal calendar with decision deadlines for our sales and marketing tools."
- "Estimate the true cost of our stack including admin time."
