---
name: schema-markup
description: "Use when adding or reviewing structured data (schema.org markup, usually JSON-LD) on a B2B website. Chooses the right types for each page template, writes markup that matches visible content, connects entities like the organization, people and products, and flags types whose search features have been restricted so effort goes where it pays off."
license: MIT
metadata:
  title: "Schema Markup"
  category: "seo-ai-search"
  author: "harmeet"
  summary: "Plan and write accurate JSON-LD structured data for each page template, matched to visible content and connected into one entity graph."
  tags: "schema, structured data, json-ld, technical seo, entities"
  version: "1.0"
  updated: "2026-10-19"
---
# Schema Markup

This skill plans and writes structured data that helps search engines and other machines understand who you are, what each page is about, and how your entities connect. It favors accurate, template-level markup that stays in sync with the page over sprawling markup added for hoped-for rich results.

## When to use

- A site has no structured data, or markup was added years ago and never checked.
- A new page template is being built (blog post, product page, event page, job listing).
- Validation tools report errors or warnings.
- The team wants consistent entity information for search and AI systems.

## What you need

Ask for these first:

1. **Page templates:** list the types of pages on the site (home, about, product, pricing, blog post, case study, event, job, location, FAQ).
2. **Sample URLs or page content** for each template.
3. **Organization facts:** legal and brand name, logo URL, website, social profiles, contact points, address if relevant.
4. **People:** authors and leaders who appear on the site, with their role and profile links.
5. **Products or services:** names, descriptions, and whether prices are public.
6. **Platform constraints:** whether markup is added per page by hand, through a content management plugin, or in templates by developers.

## Process

1. **Map templates to types.** Common B2B mappings:
   - Site-wide: `Organization` (or a more specific subtype) and `WebSite`.
   - Blog post or insight: `Article` or `BlogPosting` with author as `Person`.
   - Product or software page: `Product`, `Service` or `SoftwareApplication`, depending on what is sold.
   - Event or webinar page: `Event`, with online attendance mode where relevant.
   - Job listing: `JobPosting`.
   - Location page: `LocalBusiness` subtype, only if visitors can actually visit.
   - Navigation: `BreadcrumbList` on pages with breadcrumbs.
   - Video pages: `VideoObject`.
2. **Respect the visibility rule.** Mark up only information that appears on the page for users. Ratings must come from real reviews shown on the page; prices must match the visible price. Markup that misrepresents content can lead to a manual action that removes rich result eligibility.
3. **Know what is restricted.** Some search features have narrowed: FAQ rich results are now shown mainly for authoritative government and health sites, and how-to rich results have been retired. FAQ markup can still describe content accurately, but do not promise rich results from it. Check the search engine's current documentation before investing in a type for its display benefit.
4. **Build one connected graph.** Give key entities a stable identifier (`@id`, usually the page URL plus a fragment such as `#organization`). Reference the organization as publisher of articles, people as authors, and the website as part of the organization. Use `sameAs` to link to official profiles. Consistent entities help search and AI systems resolve who you are. An `@id` reference does not pull in properties from another page, because consumers generally read each page's markup on its own. Wherever a page's feature needs publisher or organization details (articles, for example), include the Organization node with name, url and logo in that page's graph, reusing the same `@id` and identical values.
5. **Write JSON-LD.** Prefer JSON-LD in the page head or body over inline microdata, because it is easier to maintain. Include required properties for any rich result you target and add recommended ones where the information exists. Use full URLs and ISO 8601 dates.
6. **Template, do not hand-code.** Specify which fields are pulled from the content system (title, author, dates, image) so markup updates when content does. Hand-written markup on hundreds of pages drifts out of date.
7. **Validate.** Test with a schema validator and the search engine's rich results test. Fix errors first; review warnings for missing recommended properties.
8. **Monitor.** Check enhancement reports in search console after deployment and after template changes.

## Output format

```
Structured data plan: [site], [date]

Template map
| Template | Schema types | Key properties | Data source for each field | Rich result eligible? |

Entity graph
- Organization @id: https://example.com/#organization
- WebSite @id: https://example.com/#website
- Person @ids: ...

Markup (one block per template)
Template: [name]
```

Then, for each template, a fenced JSON-LD block, for example:

```
{
  "@context": "https://schema.org",
  "@type": "BlogPosting",
  "headline": "[visible title]",
  "datePublished": "2026-01-15",
  "dateModified": "2026-02-01",
  "author": { "@type": "Person", "@id": "https://example.com/team/jane#person", "name": "[author name]" },
  "publisher": {
    "@type": "Organization",
    "name": "[brand name]",
    "logo": "https://example.com/images/logo.png",
    "url": "https://example.com/",
    "@id": "https://example.com/#organization"
  },
  "mainEntityOfPage": "https://example.com/blog/[slug]",
  "image": "https://example.com/images/[file].jpg"
}
```

Close with a validation and monitoring checklist and a list of open data gaps.

## Quality checklist

- Every marked-up value is visible on the page and matches it exactly.
- Types fit the page's actual purpose; no product markup on blog posts, no local business markup without a visitable location.
- Restricted or retired rich result types are flagged honestly.
- Entities use stable `@id` values and reference each other, and each page still carries the properties its own feature requires.
- Field sources are specified so markup stays in sync with content.
- JSON-LD is syntactically valid (quotes, commas, brackets) and uses absolute URLs and ISO dates.

## Common mistakes

- **Invisible or inflated data.** Marking up reviews, prices or FAQs that are not on the page risks penalties and erodes trust.
- **Expecting guaranteed rich results.** Valid markup makes a page eligible; search engines decide what to display.
- **Organization markup on every page with different details.** Inconsistent names, logos or profiles weaken entity understanding. Keep one canonical set of values and one `@id`, then repeat the properties each page needs instead of relying on a bare reference.
- **Hand-coded markup that goes stale.** Dates and authors change; templated markup keeps up.
- **Choosing types for display rather than accuracy.** Wrong types (recipes for instructions, events for broadcasts) are treated as misleading.
- **Never validating after changes.** A template update can silently break markup across hundreds of pages.

## Example prompts

- "Plan structured data for our B2B site: home, product, pricing, blog, case studies and events."
- "Write JSON-LD for this blog post template with author and publisher linked."
- "Our validator shows 40 errors on product pages. Here's the markup. Fix it."
- "Should we still add FAQ schema to our service pages?"
- "Create an Organization and WebSite graph we can reuse across the whole site."
