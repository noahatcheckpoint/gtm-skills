---
name: signal-based-prospecting
description: Use when a team wants to prioritize outbound around buying signals instead of static lists. Identifies which observable events predict a purchase for this offer, defines how to detect and verify each one, weights them into a simple priority score with time decay, and maps every signal to a play and message angle.
license: MIT
metadata:
  title: "Signal-Based Prospecting"
  category: "outbound"
  author: "harmeet"
  summary: "Find the buying signals that predict deals for your offer, score them with time decay, and map each to a specific outreach play."
  tags: "buying signals, intent, prospecting, prioritization, triggers"
  version: "1.0"
  updated: "2026-10-19"
---
# Signal-Based Prospecting

This skill builds a signal playbook: a short list of observable events that make an account more likely to buy now, how to detect each one, how much weight it deserves, how fast it goes stale, and what to say when it fires. The goal is to spend rep time on accounts that are moving, not on accounts that merely fit.

## When to use

- Reps work through static lists alphabetically and reply rates are low.
- The team has access to intent, hiring or technology data but no rules for using it.
- Leadership wants outbound to focus on "in-market" accounts.
- An ICP exists, but there is no way to decide which fitting accounts to contact this week.

## What you need

Ask for these first:

1. **ICP:** the fit criteria, so signals are only applied to accounts worth pursuing.
2. **Recent wins:** 10 to 20 closed-won deals and, if known, what was happening at those accounts in the 90 days before the first conversation.
3. **Data sources available:** for example job postings, funding news, leadership changes, technology detection, website visit data, review sites, community activity, public filings, product usage for existing customers.
4. **Rep capacity:** how many accounts a rep can work per week.
5. **Offer:** what you sell and the problem it solves, to judge which events create that problem.

## Process

1. **Reverse-engineer from wins.** For each recent win, list what changed at the account before it engaged: new hire in the buying function, funding, new market, a tool they replaced, a compliance event, a spike in hiring for a specific role. Patterns that appear in several wins are your strongest candidates.
2. **Brainstorm additional signals.** Group them by type:
   - *Change signals:* new executive in the buying role, reorganization, merger, funding, new office or market.
   - *Pain signals:* job postings that describe the problem you solve, negative reviews of a competitor, public complaints, rising headcount without matching tooling.
   - *Technology signals:* adoption or removal of a related tool, contract renewal timing for an incumbent.
   - *Engagement signals:* visits to pricing or comparison pages, repeat content consumption, event attendance, replies to past outreach.
   - *Relationship signals:* a former customer or champion joining the account, a mutual connection, a shared investor.
3. **Explain the causal link.** For each signal write one sentence on why it creates or reveals the problem you solve. Drop signals you cannot explain; correlation without a reason tends to disappear.
4. **Assess detectability.** For each signal note the source, how reliably it can be detected, and the false-positive risk. A job posting is verifiable; a vague third-party intent spike may not be.
5. **Weight and decay.** Assign points by predictive strength (for example 10 to 40). Pick one decay model and use it for every signal. The default here is stepped windows, because reps can read them: each signal gets a relevance window (a funding round perhaps 90 days, a pricing-page visit a week or two, a new executive their first 3 to 6 months) split into named steps. Teams with enough outcome data can use an exponential half-life instead, but not both. Treat the starting points and windows as guesses, then check them against which signals actually preceded meetings and wins, and adjust.
6. **Combine with fit.** Only score accounts that pass the ICP. Multiple signals at once (stacking) should push an account to the top; one weak signal alone should not.
7. **Map signals to plays.** For each signal write the angle and the opener: what you would say to someone at that moment. The message should reference the situation, not the data source.
8. **Set the operating rhythm.** Decide how often scores refresh, the threshold that triggers outreach, how many accounts per rep per week, and how to log outcomes so weights can be recalibrated quarterly.

## Output format

```
Signal playbook: [offer], [date]

| Signal | Type | Why it predicts a purchase | Source | Reliability (H/M/L) | Points | Freshness window | Play / angle |
|---|---|---|---|---|---|---|---|

Scoring rule
- Only ICP Tier 1-2 accounts are scored.
- Score = sum of (points x freshness factor). Decay model: stepped windows. Fresh (first third of the window) 100%, aging (middle third) 50%, fading (last third) 25%, expired 0. Starting values, to be recalibrated against meetings and wins.
- Outreach threshold: [score]. Stacking bonus: [rule].

Openers by signal
- [Signal]: "[first line referencing the situation]"

Operating rhythm
- Refresh: [daily / weekly]
- Accounts per rep per week: ...
- Outcome logging: [fields]
- Recalibration: [quarterly, method]
```

## Quality checklist

- Signals are derived at least partly from real wins, or the output says it is a hypothesis.
- Each signal has a causal explanation, a source and a reliability rating.
- Every signal has a freshness window.
- Scoring applies only to accounts that fit the ICP.
- Each signal maps to a specific opener that references the situation, not the surveillance.
- The plan includes logging outcomes and recalibrating weights.

## Common mistakes

- **Signal without fit.** A perfect trigger at an account you cannot serve is still a waste of time.
- **Creepy openers.** "I saw you visited our pricing page three times" alarms people. Speak to the likely situation instead.
- **Treating all signals equally.** A new head of the buying function is usually worth far more than a single content download.
- **No time decay.** A funding round from two years ago is trivia, not a signal.
- **Too many signals.** Twenty weak signals produce noise. Start with five to eight strong ones and add only when data supports it.
- **Never closing the loop.** Without tracking which signals led to meetings and deals, weights stay guesses forever.

## Example prompts

- "Here are our last 15 wins and what happened before each. Build a signal playbook."
- "What buying signals should we track for a security compliance product sold to mid-market SaaS?"
- "Create a scoring model with time decay for these 8 signals."
- "Write openers for each of these triggers that don't sound like we're watching them."
- "Reps can handle 40 accounts a week each. Design the weekly operating rhythm for signal-based outbound."
