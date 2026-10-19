---
name: seo-audit
description: "Use when a B2B website needs a structured SEO review because traffic dropped, a redesign or migration is planned, or nobody knows why pages do not rank. Audits crawlability, indexation, site structure, on-page relevance, content quality, internal linking, performance and authority, and returns findings ranked by business impact with clear fixes."
license: MIT
metadata:
  title: "SEO Audit"
  category: "seo-ai-search"
  author: "noah"
  summary: "Run a structured B2B SEO audit across crawl, index, structure, content and authority, then rank fixes by business impact."
  tags: "seo, technical seo, audit, content, indexation"
  version: "1.0"
  updated: "2026-10-19"
---
# SEO Audit

This skill runs a structured SEO audit and turns findings into a ranked fix list. It focuses on what matters for B2B sites: getting the pages that drive pipeline crawled, indexed and ranking for queries buyers actually use. A finding without a business consequence is noted but not prioritized.

## When to use

- Organic traffic or leads dropped and the cause is unclear.
- A site redesign, domain change or platform migration is coming.
- Important pages do not rank despite good content.
- A new team takes over the website and needs a baseline.

## What you need

Ask for what is available; unavailable items become checks the user runs.

1. **Domain and key pages:** homepage, top product or service pages, pricing, main content hubs.
2. **Business priorities:** which pages and queries matter most for pipeline.
3. **Search console data:** queries, pages, impressions, clicks, indexing report, any manual actions. Exports are fine.
4. **Analytics:** organic sessions and conversions over 12 to 16 months, with any known events (migrations, redesigns, algorithm updates).
5. **Crawl data:** output from any site crawler, if available, or the sitemap and robots.txt.
6. **Competitors** who rank for the target queries.

## Process

1. **Frame the question.** If traffic dropped, establish when, which pages and which queries. A drop across the whole site points to technical or sitewide quality causes; a drop on a few pages points to relevance, competition or cannibalization.
2. **Crawlability.** Check robots.txt for accidental blocks, server errors, redirect chains and loops, orphan pages (no internal links), and whether important content renders without heavy scripts. Confirm the XML sitemap lists only canonical, indexable URLs.
3. **Indexation.** Compare pages you want indexed with pages actually indexed. Look for stray noindex tags, conflicting canonical tags, duplicate URLs from parameters or trailing slashes, thin tag and archive pages, and staging sites exposed to search.
4. **Site structure and internal linking.** Important pages should be reachable within about three clicks from the homepage and receive internal links from related content with descriptive anchor text. Check that topic hubs link to their supporting pages and back.
5. **On-page relevance.** For each priority page: does the title tag target the main query and describe the page, is there one clear H1, does the content answer the query's intent (informational, comparison, transactional), and is the meta description written to earn the click? Look for keyword cannibalization: several pages competing for the same query.
6. **Content quality.** Assess whether priority content is original, specific, current and written by someone with evident expertise. Thin, outdated or duplicate pages can weigh down a whole section. Decide for each weak page: improve, merge, redirect or remove. Redirect only to a page that genuinely replaces it; a removed page with no true equivalent should return 404 or 410, come out of internal links and the sitemap, and have anything valuable merged elsewhere first. Redirecting everything to the homepage or a loosely related page tends to be treated as a soft 404.
7. **Performance and experience.** Check core web vitals in the field data available, mobile usability, intrusive interstitials and HTTPS. Prioritize templates (all blog posts, all product pages) over individual pages.
8. **Structured data.** Verify markup is valid, matches visible content and uses types relevant to the page. Note that eligibility for some rich results has narrowed over time.
9. **Authority.** Compare referring domains and the quality of links to priority pages against competitors. Identify linkable assets you already have and pages that deserve more internal links.
10. **Prioritize.** Score each finding on impact (traffic or pipeline at stake), effort and confidence. Fix blockers first (crawling, indexation, migrations), then relevance on high-value pages, then content and authority.

## Output format

```
SEO AUDIT: [domain], [date]

Executive summary
- Main issues: 1) ... 2) ... 3) ...
- Estimated impact: ...
- First three actions: ...

Findings
| # | Area | Finding | Evidence | Pages affected | Impact (H/M/L) | Effort (H/M/L) | Fix |
|---|---|---|---|---|---|---|---|

Priority page review
| Page | Target query | Intent match | Title / H1 | Internal links in | Issue | Fix |

Content decisions
| URL | Action (improve / merge / redirect / remove) | Reason |

Roadmap
- Weeks 1-2: ...
- Weeks 3-6: ...
- Weeks 7-12: ...

Checks the user still needs to run: ...
```

## Quality checklist

- Findings are tied to specific evidence and pages, not general advice.
- Crawl and indexation blockers are evaluated before content recommendations.
- Each finding has impact, effort and a concrete fix.
- Priority pages connected to pipeline get individual review.
- Weak content gets a decision (improve, merge, redirect, remove), not just a flag.
- Unknowns are listed as checks rather than guessed.

## Common mistakes

- **A 200-item list with no priorities.** Teams cannot act on everything. Rank by business impact.
- **Chasing tool scores.** Automated health scores flag many issues that do not affect rankings. Judge each one on consequence.
- **Ignoring intent.** A product page will struggle to rank for an informational query, and a blog post for a transactional one. Match page type to intent.
- **Removing pages without a plan.** Deleting pages that have links or traffic without redirecting them to a genuine equivalent throws away value, but redirecting to an unrelated page is no better: with no true replacement, return 404 or 410, clean up internal links and the sitemap, and merge any valuable content first.
- **Migrations without a redirect map.** Most severe traffic losses follow redesigns and domain moves done without a full URL mapping and post-launch checks.
- **Treating SEO as separate from AI search.** The same crawlable, helpful, well-structured content underpins both.

## Example prompts

- "Our organic traffic dropped 30 percent in March. Here's our search console export. Audit it."
- "We're migrating to a new CMS next quarter. What should the SEO audit and checklist cover?"
- "Review our five main service pages for on-page SEO and intent match."
- "Find keyword cannibalization in this list of URLs and target queries."
- "Give me a prioritized 90-day SEO roadmap from these crawl results."
