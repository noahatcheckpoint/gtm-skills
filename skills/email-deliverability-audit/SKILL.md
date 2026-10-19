---
name: email-deliverability-audit
description: Use when outbound or marketing emails land in spam, open or reply rates drop suddenly, a new sending domain is being set up, or before scaling volume. Audits authentication, domain and sending infrastructure, list quality, sending behavior and content, then ranks fixes by impact and gives a recovery or warm-up plan.
license: MIT
metadata:
  title: "Email Deliverability Audit"
  category: "outbound"
  author: "harmeet"
  summary: "Diagnose why emails miss the inbox across authentication, reputation, list quality, volume and content, then fix in priority order."
  tags: "deliverability, spf, dkim, dmarc, sender reputation"
  version: "1.0"
  updated: "2026-10-19"
---
# Email Deliverability Audit

This skill runs a structured audit of why email is or might be missing the inbox, and produces a prioritized fix list. It works for cold outbound and for marketing or lifecycle email, and it is equally useful before a problem (pre-scale check) and after one (incident recovery).

## When to use

- Open or reply rates dropped suddenly with no change in copy.
- Prospects say they found your email in spam.
- Bounce rates or spam complaints are rising.
- A new domain or mailbox is being set up for outbound.
- The team plans to increase sending volume significantly.

## What you need

Ask for what is available. Missing items become the first steps of the audit.

1. **Domains and mailboxes:** the sending domains, whether outbound uses the primary company domain or separate domains, number of mailboxes, their age.
2. **DNS records:** SPF, DKIM and DMARC records as text (the user can copy them from their DNS provider or an online lookup tool).
3. **Volumes:** emails per mailbox per day, total per day, and recent changes.
4. **Metrics for the last 30 to 60 days:** bounce rate, spam complaint rate (from mailbox provider dashboards where available), open and reply rate trends.
5. **List sourcing:** where contacts come from, whether and how they are verified, how old the data is.
6. **Sample emails:** two or three recent messages as sent, including links and signature.
7. **Sending platform type:** a sales engagement tool, a marketing platform, or direct from mailboxes. Named as an example only.

## Process

1. **Authentication.** Check that:
   - SPF exists, includes every service that sends as the domain, has only one SPF record, and stays under the 10 DNS lookup limit.
   - DKIM is enabled for every sending service, with keys of at least 1024 bits (2048 preferred).
   - DMARC exists. Start at `p=none` with reporting to monitor, then move to quarantine or reject once all legitimate sources pass.
   - The visible From domain aligns with the SPF or DKIM domain, so DMARC can pass.
   Major mailbox providers now require authentication, and bulk senders face stricter rules including DMARC and easy unsubscribe for marketing mail.
2. **Domain strategy.** Heavy cold outbound from the primary domain puts company-wide email at risk. A common practice is to send outbound from separate, similar domains that redirect to the main site, each with its own authentication. Check domain age: very new domains need warm-up before volume.
3. **Volume and pacing.** Heuristic for cold outbound: keep each mailbox to a modest daily volume (often cited around 30 to 50 cold emails), ramp new mailboxes gradually over several weeks, and avoid sudden spikes. Spread sends through the working day rather than in one burst.
4. **List quality.** Hard bounces above roughly 2 percent are a warning sign; aim well below. Verify addresses before sending, remove role addresses where inappropriate, drop catch-all domains or send to them cautiously, and refresh data older than a few months. Never use purchased lists of unknown origin.
5. **Engagement and complaints.** Keep spam complaint rates very low; mailbox providers flag senders that approach 0.3 percent, and a healthy target is below 0.1 percent. Stop mailing contacts who never engage, honor opt-outs immediately, and make unsubscribing easy.
6. **Content and format.** Plain text, few or no links in a first touch, no link shorteners, no large images, no attachments in cold email, consistent sender name. Avoid tracking pixels and branded tracking domains that are not set up correctly. Spam trigger words matter less than reputation, but excessive hype and all caps still hurt.
7. **Diagnose the incident (if any).** Line up the timeline: when did metrics drop, what changed just before (new list, volume jump, new domain, new tool, new link). Most incidents trace to one recent change.
8. **Prioritize fixes.** Rank by impact and urgency: authentication failures and blocklist issues first, then volume and list problems, then content.
9. **Plan recovery or warm-up.** For a damaged domain: pause cold sends, send only to engaged contacts, rebuild slowly, monitor daily. For new domains: a multi-week ramp with gradual volume increases.

## Output format

```
DELIVERABILITY AUDIT: [domains], [date]

Summary: [healthy / at risk / incident], main cause: ...

Findings
| Area | Check | Status (pass / warn / fail / unknown) | Evidence | Fix |
|---|---|---|---|---|
| Authentication | SPF single record, under 10 lookups | ... | ... | ... |
| Authentication | DKIM on all senders | ... | ... | ... |
| Authentication | DMARC present and aligned | ... | ... | ... |
| Domain | Outbound separated from primary | ... | ... | ... |
| Volume | Per-mailbox daily volume | ... | ... | ... |
| List | Bounce rate / verification | ... | ... | ... |
| Engagement | Complaint rate / opt-out handling | ... | ... | ... |
| Content | Links, tracking, format | ... | ... | ... |

Priority fixes
1. [fix] (impact: high, effort: low)
2. ...

Recovery / warm-up plan
| Week | Daily volume per mailbox | Audience | Watch |

Monitoring: [metrics, thresholds, check frequency]
```

## Quality checklist

- Each of SPF, DKIM, DMARC and alignment is explicitly checked or listed as unknown.
- Metrics are compared to thresholds, and thresholds are labeled as heuristics.
- The audit separates cold outbound risks from marketing email risks where both exist.
- Fixes are ranked, not just listed.
- An incident diagnosis names the most likely recent change.
- Advice is tool-agnostic and does not require a specific vendor.

## Common mistakes

- **Blaming copy first.** Swapping spam words rarely fixes an authentication or reputation problem.
- **Multiple SPF records.** Adding a second SPF record for a new tool instead of merging breaks SPF entirely.
- **Jumping to DMARC reject.** Enforcing before all legitimate senders pass can block your own invoices and newsletters.
- **Cold outbound from the main domain at volume.** One bad campaign can put sales, support and billing email in spam.
- **Skipping verification.** A list with high bounce rates damages reputation within days.
- **Scaling too fast.** Doubling volume overnight on young mailboxes is one of the most common causes of sudden inbox loss.

## Example prompts

- "Our reply rates halved this week. Here are our DNS records and send volumes. What's wrong?"
- "Audit our setup before we scale outbound from 500 to 3,000 emails a day."
- "Check this SPF, DKIM and DMARC configuration and tell me what to fix."
- "We just bought three new domains for outbound. Give me a warm-up plan."
- "Prospects say our emails land in spam. Walk me through a full deliverability audit."
