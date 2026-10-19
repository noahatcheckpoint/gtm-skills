---
name: cold-email-writer
description: Use when writing a first-touch B2B cold email to a specific person or a tightly defined segment. Gathers the trigger, the problem and the proof, then drafts short, plain-text emails that read like a note from a peer, with a low-friction ask and two alternative angles to test.
license: MIT
metadata:
  title: "Cold Email Writer"
  category: "outbound"
  author: "carolina"
  summary: "Write short, relevant first-touch cold emails built on a real trigger, one clear problem, believable proof and a low-friction ask."
  tags: "cold email, outbound, prospecting, sdr, copywriting"
  version: "1.0"
  updated: "2026-10-19"
---
# Cold Email Writer

This skill drafts first-touch cold emails that a busy buyer can read in 20 seconds and answer in one line. It favors relevance over cleverness: a real reason for writing, a problem the reader recognizes, a credible proof point, and one easy question.

## When to use

- Writing the opening email of an outbound sequence.
- Rewriting a template that gets opens but few replies.
- Creating variants of one email for an A/B test.
- Writing to a single high-value account where the email must be fully tailored.

For the emails that follow the first one, use a follow-up sequence skill instead.

## What you need

Ask for these before writing. If the user has no trigger or proof, write anyway but mark exactly what is missing and how it would improve the email.

1. **Recipient:** role, seniority, company, and the segment they belong to.
2. **Trigger:** why this person, why now. Examples: a job change, a hiring push in a relevant team, funding, a product launch, an expansion, a public comment, a tool switch.
3. **Problem:** the specific pain your offer removes for people in this role, in their words if possible.
4. **Proof:** one result for a similar company, a recognizable customer type, or a concrete number.
5. **The ask:** what a good outcome looks like (reply, referral to the right person, a short call).
6. **Sender:** who is sending and their credibility (a founder writes differently from an SDR).

## Process

1. **Pick the angle.** Choose one of these shapes based on the inputs:
   - *Trigger led:* "Saw X, which usually means Y." Best when the trigger is strong and recent.
   - *Problem led:* open with a sharp observation about a pain common to the role. Best when there is no individual trigger.
   - *Peer proof led:* "Teams like [similar company type] were dealing with Y; here's what changed." Best when proof is strong.
   - *Insight led:* share a non-obvious observation or data point about their market. Best for senior buyers.
2. **Write the opening line about them.** The first sentence is about the reader's world, not the sender. Test: if you delete the opener and the email still makes sense, the opener is decoration. It should lead directly to the problem.
3. **State the problem in one or two sentences.** Name the consequence, not just the symptom: missed targets, wasted hours, risk exposure.
4. **Add one proof point.** One specific, believable result beats a list. Avoid round, unverified percentages.
5. **Make one low-friction ask.** Interest questions ("Worth a look?", "Is this on your radar this quarter?") usually outperform requests for 30-minute meetings in a first touch. Offer a referral path if you are unsure you have the right person.
6. **Write the subject line last.** Two to four words, lowercase is fine, looks like an internal email, relates to the body. No hype, no fake "Re:", no emojis.
7. **Cut.** Target 50 to 120 words. Remove pleasantries, company history, and adjectives. Read it aloud; if any sentence sounds like an ad, rewrite it.
8. **Produce variants.** Write the primary email plus two alternatives using different angles, so the user can test what resonates.

## Output format

```
Primary email
Angle: [trigger / problem / peer proof / insight]
Subject: ...
Body:
[greeting],

[opener about their world]
[problem + consequence]
[one proof point]
[one-line ask]

[sign-off]

Word count: [n]

Variant B ([angle]): subject + body
Variant C ([angle]): subject + body

Personalization fields used: [list, with where the data comes from]
What would make this stronger: [missing inputs]
```

## Quality checklist

- The first sentence is about the recipient or their company, not the sender.
- Exactly one problem, one proof point and one ask.
- Body under about 120 words; subject two to four words.
- Plain text, no images, at most one link (ideally none in a first touch).
- "You" and "your" outnumber "we" and "our".
- No phrases that read automated: hope-you're-well pleasantries, "noticed your profile and wanted to connect", "quick question" used as filler.
- Claims are specific and could be backed up if the prospect asks.

## Common mistakes

- **Fake personalization.** "Loved your recent post!" with no connection to the problem reads as automation. Personalization should explain why you are writing.
- **Opening with yourself.** "My name is... and I work at..." spends the most valuable line on the least interesting topic.
- **Feature lists.** Three features and two links turn a note into a brochure. Pick the one capability that solves the named problem.
- **Big asks too early.** A calendar link and a 30-minute request in a first email to a stranger usually depresses replies.
- **Unbelievable proof.** "300% ROI" without context triggers skepticism. A modest, specific result is more persuasive.
- **Writing for the segment, sending to the person.** If the trigger applies to everyone on the list, it is not a trigger, it is a category.

## Example prompts

- "Write a cold email to a newly hired VP of Sales at a 200-person fintech. We help teams build pipeline forecasts."
- "Rewrite this template so it sounds less salesy and is under 100 words."
- "Give me three angles for a cold email to heads of RevOps who just switched CRMs."
- "Draft a founder-to-founder cold email for a seed-stage startup selling to logistics companies."
- "Here's a prospect's LinkedIn summary and a recent press release. Write a tailored first touch."
