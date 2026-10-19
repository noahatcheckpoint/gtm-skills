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

1. **Authentication.** Check the points below, then compare the setup with each provider's bulk-sender rules in the matrix after these steps. Check that:
   - SPF exists, includes every service that sends as the domain, has only one SPF record, and stays under the 10 DNS lookup limit.
   - DKIM is enabled for every sending service, with keys of at least 1024 bits (2048 preferred).
   - DMARC exists. Start at `p=none` with reporting to monitor, then move to quarantine or reject once all legitimate sources pass.
   - The visible From domain aligns with the SPF or DKIM domain, so DMARC can pass.
2. **Domain strategy.** Heavy cold outbound from the primary domain puts company-wide email at risk, so separate it, preferring transparent options. A branded subdomain (for example outreach.yourbrand.com) keeps the brand visible, though it shares some reputation with the parent and counts toward the parent's Gmail bulk volume. A small number of clearly branded secondary domains is the next option. Lookalike domains that redirect to the main site are a risk-assessed exception, not the default: they can confuse recipients, resemble impersonation, and mask reputation problems rather than fix them. If you use them, keep the number small, name the company plainly in every email and on the domain itself, authenticate fully, share one opt-out suppression list across all domains, never rotate in fresh domains to escape a poor reputation, and get legal and brand sign-off. Check domain age: very new domains need warm-up before volume.
3. **Volume and pacing.** Heuristic for cold outbound: keep each mailbox to a modest daily volume (often cited around 30 to 50 cold emails), ramp new mailboxes gradually over several weeks, and avoid sudden spikes. Spread sends through the working day rather than in one burst.
4. **List quality.** Hard bounces above roughly 2 percent are a warning sign; aim well below. Verify addresses before sending, remove role addresses where inappropriate, drop catch-all domains or send to them cautiously, and refresh data older than a few months. Never use purchased lists of unknown origin.
5. **Engagement and complaints.** Keep spam complaint rates very low; mailbox providers flag senders that approach 0.3 percent, and a healthy target is below 0.1 percent. Stop mailing contacts who never engage, honor opt-outs within the provider windows in the matrix below (well inside the 10 business days US law allows), and make unsubscribing easy.
6. **Content and format.** Plain text, few or no links in a first touch, no link shorteners, no large images, no attachments in cold email, consistent sender name. Avoid tracking pixels and branded tracking domains that are not set up correctly. Spam trigger words matter less than reputation, but excessive hype and all caps still hurt.
7. **Diagnose the incident (if any).** Line up the timeline: when did metrics drop, what changed just before (new list, volume jump, new domain, new tool, new link). Most incidents trace to one recent change.
8. **Prioritize fixes.** Rank by impact and urgency: authentication failures and blocklist issues first, then volume and list problems, then content.
9. **Plan recovery or warm-up.** For a damaged domain: pause cold sends, send only to engaged contacts, rebuild slowly, monitor daily. For new domains: a multi-week ramp with gradual volume increases.
10. **Check the legal gate.** Deliverability does not make a send lawful. Confirm per recipient jurisdiction: in the US, CAN-SPAM applies to B2B mail and needs accurate headers, a valid postal address and a working opt-out; in the EU, GDPR needs a lawful basis for the data, and national ePrivacy rules can require prior consent even for business recipients (Germany's UWG does). Flag unknowns for legal review instead of guessing.

### Mailbox provider requirements (as of October 2026)

| Requirement | Gmail | Yahoo | Outlook.com |
|---|---|---|---|
| Bulk threshold | Around 5,000 messages a day to personal Gmail accounts, counting the primary domain and its subdomains together; the status does not expire | No published number ("significant volume") | Domains sending over 5,000 a day to consumer addresses (outlook.com, hotmail.com, live.com) |
| Authentication for bulk | SPF and DKIM, plus DMARC at p=none or stricter | SPF and DKIM, plus a passing DMARC policy at p=none or stricter | SPF pass, DKIM pass, DMARC at p=none or stricter |
| Alignment | From domain aligned with the SPF or DKIM domain | Same; relaxed alignment accepted | Aligned with SPF or DKIM, preferably both |
| Unsubscribe | Marketing and subscribed mail: RFC 8058 one-click (`List-Unsubscribe` with an HTTPS URL and `List-Unsubscribe-Post: List-Unsubscribe=One-Click`) plus a visible link in the body | One-click `List-Unsubscribe` header (RFC 8058 POST strongly recommended, mailto accepted) plus a visible body link | Clear, working unsubscribe link recommended |
| Opt-out processing | Within 48 hours recommended | Within 2 days | Not specified |
| Spam complaint rate | Under 0.3% in its postmaster dashboard, target under 0.1% | Under 0.3%, measured only on mail delivered to the inbox | Not specified |
| Enforcement | Progressive since November 2025, including temporary and permanent rejections | Phased in from February 2024 | Failing mail rejected with error 550 5.7.515 since May 2025 |

All senders also need SPF or DKIM at minimum, valid forward and reverse DNS for sending IPs, and correctly formatted messages; Gmail also requires TLS. Providers revise these rules, so re-check their sender guidelines before relying on the table.

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
| Authentication | Provider bulk-sender matrix met | ... | ... | ... |
| Domain | Outbound separated from primary; lookalike guardrails | ... | ... | ... |
| Volume | Per-mailbox daily volume | ... | ... | ... |
| List | Bounce rate / verification | ... | ... | ... |
| Engagement | Complaint rate / one-click headers / opt-out time | ... | ... | ... |
| Legal | Jurisdiction gate (postal address, opt-out, lawful basis) | ... | ... | ... |
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
- Provider requirements are compared per provider, with the date they were verified.
- Lookalike domains, if present, are treated as an exception with guardrails, and domain rotation is flagged.
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
- **Rotating domains to outrun a bad reputation.** Fresh domains reset nothing about the underlying list or behavior, and patterns of disposable domains get filtered.
- **Skipping verification.** A list with high bounce rates damages reputation within days.
- **Scaling too fast.** Doubling volume overnight on young mailboxes is one of the most common causes of sudden inbox loss.

## Example prompts

- "Our reply rates halved this week. Here are our DNS records and send volumes. What's wrong?"
- "Audit our setup before we scale outbound from 500 to 3,000 emails a day."
- "Check this SPF, DKIM and DMARC configuration and tell me what to fix."
- "We just bought three new domains for outbound. Give me a warm-up plan."
- "Prospects say our emails land in spam. Walk me through a full deliverability audit."
