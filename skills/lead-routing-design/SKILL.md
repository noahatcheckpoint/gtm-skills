---
name: lead-routing-design
description: Designs lead routing logic as an ordered decision tree: matching leads to existing accounts and owners, territory and segment rules, assignment methods, capacity and out-of-hours fallbacks, escalation timers and a test plan. Use when leads sit unassigned, go to the wrong rep, or when territories or team structure change.
license: MIT
metadata:
  title: "Lead Routing Design"
  category: "revops-crm"
  author: "harmeet"
  summary: "Turn messy assignment rules into an ordered routing tree with account matching, fallbacks, escalation timers and test cases."
  tags: "lead routing, assignment rules, territories, speed to lead, round robin"
  version: "1.0"
  updated: "2026-10-19"
---
# Lead Routing Design

Produces a routing specification that answers, for any inbound lead, "who gets this, how fast, and what happens if they do not act?" The deliverable is an ordered rule tree, an assignment method per branch, fallbacks, escalation timers, and test cases an admin can run before go-live.

## When to use

- Leads wait hours or days because nobody owns them.
- A new contact at an existing customer gets cold-called by a different rep.
- Territories, segments, or headcount are changing.
- Reps complain the round robin is unfair, or managers suspect cherry-picking.
- You are moving routing from manual triage to automated rules.

## What you need

Ask for the following before designing:

1. **Team structure:** roles (SDR, AE, account manager, partner team), headcount, segments they cover.
2. **Territory logic:** geography, company size, industry, named accounts, language.
3. **Lead sources:** demo requests, trials, content downloads, events, partner referrals, outbound replies.
4. **Ownership rules today:** who owns accounts, open opportunities, and customers.
5. **Data available at the moment of routing:** company domain, country, employee count (enriched or self-reported), product interest.
6. **Response expectations:** the follow-up times in your SLA, business hours, time zones.
7. **Current failures:** examples of misrouted or stuck leads.

## Process

1. **Normalise first.** Routing fails on dirty inputs. Before any rule: standardise country and state values, derive the company domain from the email (ignore free email domains), and enrich size and industry if missing. Decide what happens when enrichment returns nothing.
2. **Match to existing records, then decide precedence by intent.** Look up the lead's domain against accounts, resolving subsidiaries, multiple domains and the account hierarchy. A match does not settle ownership on its own. Write the precedence policy from what the inquiry is about: a request tied to an open, active opportunity for the same product and region goes to that opportunity's owner; new demand for a different product, business unit or region follows that segment's owner even inside a known account; a support or renewal question from a customer goes to customer success. Ignore stale opportunities (no activity past a set number of days) when assigning, and notify the other owners on the account instead of assuming one universal order.
3. **Filter out what should not be routed to a person.** Spam, competitors, students, existing support requests (send to support), job applicants. Each gets a destination, not a dead end.
4. **Separate hand-raisers from everything else.** Demo and contact-sales requests get the fastest path and may route to an AE directly. Low-intent leads go to nurture or an SDR queue based on score.
5. **Apply territory or segment rules in a fixed order.** Named accounts first, then segment (size band), then geography, then specialisms such as language or product line. Write them as an explicit top-to-bottom list; the first match wins.
6. **Choose an assignment method per branch.**
   - Direct owner: named accounts and existing relationships.
   - Round robin: equal reps, similar lead quality.
   - Weighted round robin: different ramp levels or quotas.
   - Load-balanced: assign to the rep with the fewest open untouched leads.
   - Pooled queue (first to claim): very high volume, low value, with a claim timer.
7. **Design fallbacks.** Rep out of office or at capacity: skip to next eligible rep. No eligible rep: route to a team queue and alert the manager. Outside business hours: define whether leads wait, go to another time zone, or trigger an automated meeting link.
8. **Set escalation timers.** If a hand-raiser is not touched within the SLA window, reassign or alert. Decide what counts as "touched" (a logged call or email, not a status change).
9. **Log every decision.** Store which rule fired and why on the record. This turns routing disputes into a lookup rather than an argument.
10. **Write test cases** covering every branch, including edge cases: free email domain, unknown country, existing customer, partner-sourced lead, duplicate submission.

## Output format

```
# Lead Routing Specification: [Company]   Effective [date]

## Pre-routing normalisation
[steps and fallback when data is missing]

## Routing tree (first match wins)
| # | Condition | Destination | Assignment method | SLA |
|---|---|---|---|---|
| 1 | Domain matches account with open opp | Opp owner | Direct | [x] min |
| 2 | ... | ... | ... | ... |
| n | No match | [queue] | [method] | ... |

## Exclusions
| Condition | Destination |

## Fallbacks
- Out of office / capacity:
- No eligible rep:
- Outside business hours:

## Escalation timers
| Lead type | Untouched after | Action |

## Logging fields
[routing rule ID, routed at, previous owner]

## Test cases
| Case | Input | Expected owner | Rule # |

## Metrics
Time to first touch by source, % auto-routed, misroute rate, reassignments.
```

## Quality checklist

- Account and owner matching happens before any territory rule.
- The tree is ordered and every lead reaches exactly one destination (including a final catch-all).
- Each branch states its assignment method and SLA.
- Fallbacks exist for absence, capacity, and out of hours.
- "Touched" is defined by a real activity, not a field change.
- The rule that fired is logged on the record.
- Test cases cover every rule plus edge cases.

## Common mistakes

- **Skipping account matching.** The most visible routing failure is two reps calling the same company in one week.
- **Rules without a catch-all.** Any lead that matches nothing ends up owned by an admin or by nobody.
- **Round robin that ignores availability.** Leads go to a rep on holiday and sit for a week.
- **Routing on self-reported company size** without a fallback when it is blank or obviously wrong.
- **Counting a status change as follow-up.** Reps learn to click "working" to stop the escalation timer.
- **Unlogged logic.** When nobody can see why a lead went where it did, every dispute escalates to a manager.
- **Building territories that cannot be balanced.** Review volume per rep each quarter; geography drifts.

## Example prompts

- "Design lead routing for 3 SDRs, 6 AEs split by company size, and a partner team."
- "New contacts at existing customers keep going to SDRs. Fix our routing rules."
- "Write a routing tree with fallbacks for after-hours demo requests across US and EU time zones."
- "Our round robin feels unfair. Propose a weighted or load-balanced alternative."
- "Give me test cases to validate our routing rules before go-live."
