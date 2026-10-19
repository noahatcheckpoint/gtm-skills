---
name: ai-search-optimization
description: "Use when a company wants to be cited or recommended in AI answer engines such as ChatGPT, Perplexity, Google AI Overviews, Gemini, Copilot or Claude. Audits how the brand currently appears for buyer prompts, separates being cited as a source from being named as a recommendation, and builds a prioritized plan across technical access, citable content and off-site presence."
license: MIT
metadata:
  title: "AI Search Optimization"
  category: "seo-ai-search"
  author: "noah"
  summary: "Get your brand cited and recommended in AI answers: audit buyer prompts, fix access, publish citable content and build off-site presence."
  tags: "ai search, geo, aeo, llm visibility, answer engines"
  version: "1.0"
  updated: "2026-10-19"
---
# AI Search Optimization

This skill builds a plan to improve how a brand shows up in AI-generated answers. It distinguishes two different goals that need different work: being **cited** (your page is used as a source) and being **named** (your brand appears in the answer as a recommended option). Many brands are cited but rarely named, or the reverse.

## When to use

- Buyers say they asked an AI assistant for recommendations and the company was not mentioned.
- Organic search traffic is falling while AI answers appear above results.
- Leadership asks "what does ChatGPT say about us?"
- Planning content and PR with AI visibility as a goal.

## What you need

Ask for these first:

1. **Brand and website,** plus the main product categories.
2. **Competitors** buyers compare you with.
3. **Buyer prompts:** 15 to 30 questions real buyers might ask an assistant, across stages: problem ("how do I reduce churn in SaaS"), category ("best tools for X"), comparison ("X vs Y"), and brand ("is X good for mid-market").
4. **Current results:** if the user can run the prompts in several assistants, collect the answers and cited sources. If not, provide the prompt set and a simple log for them to fill in.
5. **Technical access:** robots.txt contents and whether a firewall or bot protection service is active.
6. **Off-site footprint:** review site profiles, directory listings, community presence, press coverage, partner pages.

## Process

1. **Build the prompt set.** Group prompts by stage and intent. Weight category and comparison prompts most, since that is where recommendations happen.
2. **Baseline visibility.** For each prompt in each assistant, record: brand named (yes/no, position), competitors named, sources cited, and whether your domain is among them. AI answers vary between runs, so run important prompts more than once and treat results as a sample, not a ranking.
3. **Check technical access first.** Confirm that search engine crawlers and the main AI crawlers are not blocked in robots.txt or by bot protection at the network level. Examples of user agents to review: Googlebot, Bingbot, OAI-SearchBot, GPTBot, PerplexityBot, ClaudeBot. Map each user agent to the purpose its operator documents (model training, search indexing, or fetching a page when a user asks) and decide per purpose: blocking training crawlers is a policy choice, while blocking search or user-triggered agents can reduce direct discovery, freshness and citation eligibility. It does not guarantee absence, since engines may still answer from existing indexes, partner indexes or third-party pages, so verify the effect engine by engine. Make sure key content is in the HTML as text, not only rendered by scripts or locked in images and PDFs.
4. **Diagnose citation gaps.** For prompts where competitors or third parties are cited and you are not, study the cited pages. Common traits: a direct answer near the top, clear headings that mirror the question, specific numbers and definitions, recent dates, named authors with expertise, and structured comparisons or tables.
5. **Diagnose naming gaps.** Being recommended depends heavily on what the wider web says. Look at which third-party sources the assistants cite for category prompts: review sites, comparison articles, community threads, industry lists, analyst and media coverage. Treat absence from those sources as a hypothesis, not the verdict: naming also depends on how well the brand fits the query, what the model already knows, which sources each engine retrieves, and the evidence about the product itself. Compare prompts where you are named with prompts where you are not, engine by engine, and prioritize the sources whose presence actually tracks being named.
6. **Plan on-site work (to be cited).** Create or rework pages that answer high-value prompts directly: definitions, how-to guides, comparison pages, pricing explanations, original data. Lead each with a two or three sentence answer, then depth. Keep facts consistent across pages and update dates when content truly changes. Use structured data that matches visible content; it helps machines interpret pages but is not a shortcut.
7. **Plan off-site work (to be named).** Prioritize the third-party sources that the naming comparison linked to being recommended: get listed and reviewed on relevant review platforms, contribute expert input to industry articles, participate genuinely in communities, pursue inclusion in credible comparison lists, publish original research that others reference. Make sure your brand's description is consistent everywhere.
8. **Set measurement.** Re-run the prompt set monthly. Track share of prompts where the brand is named, share where your domain is cited, and competitor share. Also watch referral traffic from assistant domains in analytics.

## Output format

```
AI visibility plan: [brand], [date]

Baseline (sample of [n] prompts x [assistants])
| Prompt | Stage | Named? (position) | Domain cited? | Competitors named | Top cited sources |

Summary
- Named in [x]% of prompts; cited in [y]%.
- Main competitor share: ...
- Biggest gap: [cited but not named / named but not cited / neither]

Technical access
| Check | Status | Fix |

Priority actions
| # | Action | Goal (cite / name / access) | Prompts affected | Effort | Owner |

On-site content plan: [pages to create or rework, with the prompt each answers]
Off-site plan: [target sources, why each matters]
Measurement: [cadence, metrics, log format]
```

## Quality checklist

- Citation and naming are measured and planned separately.
- Technical access is checked before content work is recommended.
- The baseline is described as a sample, with run-to-run variation acknowledged.
- Off-site actions target sources the assistants actually cite, not generic PR.
- Every recommended page maps to specific prompts.
- No tactic promises guaranteed placement; no manipulation such as hidden text or fake reviews.

## Common mistakes

- **Treating it as a new trick.** Search engines state that AI features rely on the same fundamentals: crawlable, indexable, helpful content. There is no secret file or markup that guarantees inclusion.
- **Blocking crawlers by accident.** Bot protection or a copied robots.txt rule can silently remove a site from live AI answers.
- **Only on-site work.** Recommendations often draw on what others say about you. A perfect website with no third-party presence is rarely named.
- **One-off checks.** A single prompt run is anecdotal. Track a stable prompt set over time.
- **Writing for machines.** Keyword-stuffed or robotic content hurts trust with humans and does not reliably help with AI systems.
- **Inconsistent facts.** Different pricing, founding dates or descriptions across pages and profiles confuse both readers and models.

## Example prompts

- "Audit how our brand appears in ChatGPT, Perplexity and Google AI Overviews for our category."
- "Build a set of 25 buyer prompts for a payroll software company and a tracking sheet."
- "We're cited often but never recommended. What should we do?"
- "Check our robots.txt for anything blocking AI search crawlers."
- "Create a 90-day plan to get named in AI answers for 'best customer onboarding tools'."
