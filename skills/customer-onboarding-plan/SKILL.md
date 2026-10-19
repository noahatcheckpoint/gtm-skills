---
name: customer-onboarding-plan
description: "Creates a B2B customer onboarding plan from signed contract to first value and full adoption: sales-to-success handoff brief, kickoff agenda, success criteria, phased milestones with owners on both sides, time-to-value targets, risk triggers and a graduation checklist. Use for each new customer, when designing a repeatable onboarding programme, or when new customers take too long to see value."
license: MIT
metadata:
  title: "Customer Onboarding Plan"
  category: "customer-success"
  author: "esther"
  summary: "Plan onboarding from handoff to first value: success criteria, phased milestones, owners on both sides, risk triggers and graduation."
  tags: "customer onboarding, time to value, handoff, implementation plan, customer success"
  version: "1.0"
  updated: "2026-10-19"
---
# Customer Onboarding Plan

Produces an onboarding plan that gets a new customer to a meaningful first result quickly and then to steady adoption. It covers the handoff from sales, the kickoff, measurable success criteria, a phased timeline with owners on both sides, early warning triggers, and the point at which the customer "graduates" from onboarding.

## When to use

- A new customer has signed and onboarding is about to start.
- Designing or rebuilding a standard onboarding programme for a segment.
- New customers repeat to the onboarding team what they already told sales.
- Time to first value is long or unpredictable, or early churn is high.
- Moving from a high-touch to a lighter-touch onboarding for smaller customers.

## What you need

Ask for these before planning:

1. **Customer and deal context:** company, contract value, products purchased, contract start date, renewal date.
2. **Why they bought:** the problem, the outcomes promised in the sales process, and any mutual action plan or proposal.
3. **Stakeholders:** sponsor, project lead, admins, end-user teams, and their availability.
4. **Implementation scope:** integrations, data migration, configuration, training needs.
5. **Your onboarding capacity:** who works on it and typical durations.
6. **Constraints:** customer deadlines, holidays, competing projects, security or IT reviews.

## Process

1. **Run a structured handoff before kickoff.** Sales and the onboarding owner complete a handoff brief: goals in the customer's words, success metrics, stakeholders and their attitudes, promises made (including anything non-standard), risks, and technical details. The seller should join the kickoff so the customer does not have to repeat themselves.
2. **Define first value and full value.** First value is the earliest moment the customer gets a real result they care about (first report used in a meeting, first campaign sent, first workflow automated). Full value is the outcome they bought for. Both need a measurable definition and a target date.
3. **Set time-to-value targets.** Measure from contract signature. Split the clock into three segments (signature until kickoff, kickoff until first value, first value until full adoption) so delays can be located. Targets depend on your product; light self-serve products may reach first value in days, complex implementations in weeks or months.
4. **Plan the kickoff.** Agenda: introductions and roles, confirm goals and success criteria, walk the plan, agree communication rhythm, confirm what the customer must provide (people, data, access), and agree the first milestone date. Send the plan in writing within 24 hours.
5. **Build phases with milestones.** For example: Setup (access, integrations, data), Configure (workflows, permissions), Enable (training by role), Launch (first live use, first value), Adopt (usage across teams, first review). Each milestone has an owner on each side, a date, and a definition of done.
6. **Front-load the critical path.** Identify dependencies that usually slip (IT approvals, data exports, security reviews) and start them first.
7. **Train by role and by task.** Admins, managers, and end users need different training. Tie each session to a task they will do the following week.
8. **Set risk triggers.** For example: kickoff not held within the target window, a milestone missed by more than a week, sponsor absent from two check-ins, low logins two weeks after launch. Each trigger has an action and an escalation path.
9. **Define graduation.** The checklist that moves the customer from onboarding to ongoing success management: first value achieved, adoption threshold met, success plan for the next quarter agreed, and a satisfaction check completed.
10. **Capture lessons.** After graduation, note what slowed this customer down and feed it into the standard plan and the sales handoff brief.

## Output format

```
# Onboarding Plan: [Customer]   Signed [date]   Kickoff [date]   Renewal [date]

## Handoff brief
- Why they bought (their words):
- Success metrics:
- Promises made in the sales process:
- Stakeholders and attitudes:
- Risks:
- Technical scope:

## Success definitions
First value: [definition]  Target date: [ ]
Full value: [definition]   Target date: [ ]

## Kickoff agenda
[items, owners, timing]

## Milestone plan
| Phase | Milestone | Definition of done | Customer owner | Our owner | Date | Status |
|---|---|---|---|---|---|---|

## Customer responsibilities
[people, data, access, approvals, with dates]

## Training plan
| Audience | Session | Task it enables | Date |

## Risk triggers
| Trigger | Action | Escalate to |

## Graduation checklist
- [ ] First value achieved and confirmed by sponsor
- [ ] Adoption threshold met: [ ]
- [ ] Next-quarter success plan agreed
- [ ] Satisfaction check completed

## Time-to-value tracking
Signature until kickoff: [ ] days. Kickoff until first value: [ ] days. First value until adoption: [ ] days.
```

## Quality checklist

- A handoff brief exists and records promises made during the sale.
- First value and full value are measurable with target dates.
- Time to value is tracked in separate segments.
- Every milestone has a definition of done and owners on both sides.
- Customer responsibilities are explicit with dates.
- Slow dependencies are started first.
- Risk triggers have actions and escalation paths.
- Graduation criteria are defined.

## Common mistakes

- **Starting from zero after the sale.** Customers who repeat their story feel the company does not talk to itself. Use the handoff brief.
- **Defining success as "implementation complete."** Configuration finished is not value delivered. Track a business outcome.
- **One training session for everyone.** Admins and end users need different things at different times.
- **Ignoring customer-side work.** Plans fail when the customer did not know they owed data, access, or people.
- **Long silent periods.** Weeks without contact during setup make customers anxious; keep a steady rhythm.
- **No escalation triggers.** Slipping milestones only become visible when the renewal is at risk.
- **Treating every customer the same.** Match the depth of onboarding to contract value and complexity.

## Example prompts

- "Create an onboarding plan for a new 250-seat customer who bought our platform to shorten their sales cycle."
- "Write a sales-to-success handoff brief template and kickoff agenda."
- "Our customers take three months to see value. Redesign our onboarding to cut that in half."
- "Define first value and graduation criteria for our mid-market onboarding programme."
- "Build a lighter onboarding track for customers under a certain contract value."
