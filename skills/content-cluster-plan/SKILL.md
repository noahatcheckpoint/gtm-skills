---
name: content-cluster-plan
description: "Use when planning B2B content around a topic so it builds search and AI visibility and supports pipeline. Picks topics from buyer problems and the product's strengths, maps a pillar page with supporting articles by intent and funnel stage, defines internal linking, avoids cannibalization, and sequences production into a realistic calendar."
license: MIT
metadata:
  title: "Content Cluster Plan"
  category: "seo-ai-search"
  author: "noah"
  summary: "Plan a topic cluster: a pillar page plus supporting articles mapped to buyer intent, linked together and sequenced into a calendar."
  tags: "content strategy, topic clusters, pillar pages, keyword research, internal linking"
  version: "1.0"
  updated: "2026-10-19"
---
# Content Cluster Plan

This skill plans a group of related content pieces around one topic: a pillar page covering it broadly and supporting pieces covering each subtopic in depth, all linked together. A well-built cluster shows search engines and AI systems that the site covers the topic thoroughly, and it gives buyers a path from first question to sales conversation.

## When to use

- Starting a content program, or restarting one that produced scattered posts with little traffic.
- Choosing which topics to own for a product line or segment.
- Existing content overlaps and pages compete with each other.
- The team wants content that supports pipeline, not only traffic.

## What you need

Ask for these first:

1. **ICP and personas,** with the problems they research.
2. **Product strengths:** where the offer is clearly better, so content leads toward it.
3. **Candidate topics** or business priorities (a product launch, a segment push).
4. **Existing content:** URLs and titles of published pieces related to the topic.
5. **Search data, if available:** keyword research exports, search console queries, or questions from sales calls and support.
6. **Capacity:** pieces per month the team can realistically publish with quality.

## Process

1. **Choose the cluster topic.** Score candidate topics on: buyer relevance (do target personas research this?), business fit (does it lead to your product?), authority (can you say something credible and specific?), and opportunity (demand and competition). Pick the topic with the best combination, not the biggest search volume.
2. **Collect the questions.** List everything a buyer asks about the topic: definitions, how-to, tools, costs, mistakes, comparisons, templates, examples. Sources: sales and support conversations, community threads, the "people also ask" style questions in search results, prompts buyers type into AI assistants, and keyword tools if available.
3. **Group by intent.** Cluster questions that one page could answer completely. A useful test: if the same pages already rank for two queries, they probably belong on one page. Label each group with intent (learn, solve, compare, buy) and funnel stage.
4. **Define the pillar.** The pillar covers the topic broadly, answers the core question near the top, summarizes each subtopic, and links to the supporting pieces. It should target the main topic query.
5. **Define supporting pieces.** One piece per intent group. For each, set a working title, primary query, the question it answers, the format (guide, checklist, comparison, template, calculator, case example), and the call to action that fits its stage.
6. **Check for cannibalization.** Compare the plan against existing content. For each overlap decide: update the existing piece, merge it into a new one, or redirect. Never let two pages target the same primary query.
7. **Design internal links.** Every supporting piece links up to the pillar; the pillar links down to every supporting piece; related supporting pieces link to each other where it helps the reader. Specify descriptive anchor text. Link from high-traffic existing pages into the cluster.
8. **Plan for citation.** In each piece include something worth citing: a clear definition, original data, a framework, a worked example or expert input. Content with a unique contribution earns links and AI citations; content restating what already ranks rarely does.
9. **Sequence production.** Publish the pillar early (even in a lighter first version), then supporting pieces with the strongest business fit first. Schedule a refresh review for every piece at 6 to 12 months.
10. **Set metrics.** Track rankings and impressions for cluster queries, organic sessions to the cluster, assisted conversions, and citations in AI answers for the main prompts.

## Output format

```
CLUSTER: [topic]   Persona: [...]   Business goal: [...]

Topic choice: [why this topic, scores vs alternatives]

Pillar
- Title: ...
- Primary query: ...
- Core answer (2 sentences): ...
- Sections: ...

Supporting pieces
| # | Working title | Primary query | Intent / stage | Format | Unique contribution | CTA | Priority |

Existing content decisions
| URL | Overlaps with | Action (update / merge / redirect / keep) |

Internal linking
- Up-links: every piece -> pillar with anchor "[...]"
- Cross-links: [piece] -> [piece] ...
- Entry links from existing pages: ...

Calendar
| Month | Pieces | Owner |

Metrics and review: ...
```

## Quality checklist

- The topic connects to both buyer problems and the product's strengths.
- Each supporting piece has one primary query and one intent; no two pieces share a primary query.
- Existing content overlaps are resolved explicitly.
- The linking plan covers up-links, down-links and entry links from existing pages.
- Every piece has a stated unique contribution.
- The calendar fits the stated capacity.

## Common mistakes

- **Chasing volume over fit.** High-volume topics unrelated to the product bring visitors who never buy.
- **One page per keyword variant.** Splitting close variants into separate pages creates thin, competing content.
- **Pillars that are link directories.** A pillar must answer the topic itself, not just list links.
- **Ignoring existing content.** New pieces that duplicate old ones split rankings and confuse readers.
- **Publishing and forgetting.** Clusters decay; scheduled refreshes keep them accurate and competitive.
- **No path to conversion.** Every piece needs a next step suited to its stage, from a related guide to a demo.

## Example prompts

- "Plan a content cluster around 'sales forecasting' for RevOps leaders at mid-market companies."
- "Here are our 60 blog posts. Group them into clusters and find cannibalization."
- "Which of these four topics should we build a cluster around first?"
- "Design the internal linking for this pillar and its 12 supporting articles."
- "Turn this cluster plan into a 6-month calendar for a team that can publish 4 pieces a month."
