---
name: schema-markup-geo
description: Structured data guidance that helps discovery for GEO on Grok Build. Defensive / standards-based only. Use when a page needs schema.org JSON-LD that matches what it shows, when auditing sameAs identity links, or when someone asks for ratings the page cannot back.
---

# Schema Markup (GEO)

Use appropriate [schema.org](https://schema.org/) types honestly. Structured data tells an agent *what the entity is*. It does not create ratings, reviews, awards, or facts that are not on the page.

Gold Hat: map only what you can show. Teach the type and the required properties while you write the JSON-LD. Invented `aggregateRating`, fake reviews, or stuffed `knowsAbout` lists extract trust and do not ship.

Prefer JSON-LD in the server-rendered HTML. Microdata and RDFa are valid but harder for many agents to read; recommend a migrate, do not rewrite the whole site in this pass unless asked.

## When to use

- A page has no structured data, or the JSON-LD does not match the visible entity
- You need Organization / Person / Article / SoftwareApplication / FAQ JSON-LD that is true
- You are auditing `sameAs` links for entity identity
- Someone asked for "schema for GEO" and you must refuse rating theater

Do not use this skill as a full crawl or copy rewrite. Hand claim prose to `citation-readiness` (melted). Hand freshness / `dateModified` honesty to `content-freshness` (still a stub). Hand sitewide crawl leftovers to `geo-audit` (still a stub). Call the stub; do not invent its depth.

Do not invent a 0–100 schema score. Presence, validity, and honesty are enough.

## Operating steps

1. **Name the entity.** Organization, Person, SoftwareApplication, Article, LocalBusiness, Product, or FAQ — from the page, not from a wish list.
2. **Detect what is already there.** JSON-LD (`application/ld+json`), then Microdata (`itemscope`), then RDFa. Parse. Note whether it is in the HTML source or only after JS.
3. **Validate.** Valid JSON, real `@type`, required properties present, URLs absolute, dates ISO 8601, no properties you cannot evidence.
4. **Fill gaps that are true.** Add recommended properties you can source (including `sameAs` that resolve). Generate JSON-LD for missing types that fit the page.
5. **Refuse fiction.** No reviews, stars, awards, employee counts, or founding dates that are not public on this site or a linked official profile.
6. **Teach one sentence.** Which type this page is, and which property you will not fake.

Stop if the page does not state what the entity is. Ask. Guessing a LocalBusiness for a docs site is extraction.

## Types that usually matter

Pick the type the page *is*. One primary type plus honest nesting beats a graph of everything.

### Organization (or a subtype)

Required: `@type`, `name`, `url`, `logo` (image URL or `ImageObject`).

Recommended when true: `description`, `sameAs` (profiles that resolve), `foundingDate`, `address`, `contactPoint`, `knowsAbout` (topics the org actually publishes).

### Person (author, founder, personal brand)

Required: `name`, `url`.

Recommended when true: `jobTitle`, `worksFor`, `sameAs`, `description`, `image`. Do not invent `alumniOf` or `award`.

### Article (and NewsArticle / BlogPosting / TechArticle)

Required: `headline`, `datePublished`, `author` (Person or Organization), `publisher` (with logo when you have one), `image` if the page has a representative image.

Recommended: `dateModified` (only if you know it), `speakable` CSS selectors that point at a real summary on the page.

### SoftwareApplication (SaaS / tools)

Required: `name`, `description`, `applicationCategory`, `offers` only if price is public.

Recommended when true: `operatingSystem`, `softwareVersion`, `featureList` copied from the page, `releaseNotes` URL.

### FAQPage

Use only when the page is a real FAQ (question headings + answers). Useful for extraction even when rich results are restricted. Do not wrap marketing copy as fake questions.

Each `Question` needs `name` and `acceptedAnswer` → `Answer` → `text` that matches the visible answer.

### Product / LocalBusiness / WebSite

Use when the page is actually those things. `WebSite` + `SearchAction` only if a working `urlTemplate` exists. `Offer` needs real `price`, `priceCurrency`, and `availability`. `LocalBusiness` needs a real address and phone.

### `sameAs` (identity, not SEO juice)

`sameAs` means "this entity is the same as that profile." Include only URLs you fetched or the owner confirmed.

Typical honest set: official LinkedIn, GitHub, YouTube, Wikidata, Wikipedia *if the article is about this entity*. Skip a platform that 404s. Do not add a Wikipedia URL because it would be nice.

## Validation checks

| Check | Pass | Fail |
|-------|------|------|
| JSON | Parses | Trailing commas, unquoted keys |
| `@type` | Exists on schema.org | Invented types (`GeoEntity`, `AIBrand`) |
| Required props | Present and visible on the page or an official linked profile | Name in JSON that the page never uses |
| Format | JSON-LD in HTML source | Ratings injected only after JS, or Microdata-only with no plan |
| URLs | Absolute https, resolve or marked unverified | `/logo.png`, broken sameAs |
| Dates | ISO 8601 | `Sept 2026`, future `datePublished` |
| Honesty | No rating/review/award unless real third-party or first-party documented | `aggregateRating` with a made-up 4.9 |
| Deprecations | No leftover SpecialAnnouncement theater | COVID announcement schema still live |

Deprecated or narrowed for *rich results* (HowTo, FAQPage on many sites) can still help agents parse. Say that. Do not promise a rich result.

JavaScript-injected JSON-LD may be seen late or not at all. Prefer the document source. Mark **unverified** if you only saw schema in a rendered tree you could not confirm in HTML.

## Generation rules

- One `@context`: `https://schema.org`.
- Prefer a single `@graph` with `@id` values (`https://example.com/#organization`) over three disconnected blocks that disagree.
- Nest `author` inside `Article`; nest `logo` as `ImageObject` when you have dimensions.
- Place JSON-LD in the document (commonly `<head>`). Do not hide it.
- Copy visible text. Do not "improve" the description in the JSON.

Minimal honest Organization:

```json
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "@id": "https://example.com/#organization",
  "name": "Example",
  "url": "https://example.com",
  "logo": "https://example.com/logo.png",
  "description": "Open-source CLI that drafts llms.txt files from a public sitemap.",
  "sameAs": [
    "https://github.com/example/example"
  ]
}
```

Only add `foundingDate`, `numberOfEmployees`, `award`, or `aggregateRating` when the page or a linked official profile states them.

## Worked example — docs homepage

Job: entity is Example, a software project. Page already has a name, URL, logo, and GitHub link. No reviews.

Weak (extractive):

```json
{
  "@type": "Organization",
  "name": "Example",
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "4.9",
    "reviewCount": "1200"
  }
}
```

Invented ratings. Fail honesty. Critical.

Stronger: the Organization block above, plus optional `SoftwareApplication` *if* the homepage states category and a public price or "free / MIT":

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "Organization",
      "@id": "https://example.com/#organization",
      "name": "Example",
      "url": "https://example.com",
      "logo": "https://example.com/logo.png",
      "sameAs": ["https://github.com/example/example"]
    },
    {
      "@type": "SoftwareApplication",
      "name": "Example",
      "applicationCategory": "DeveloperApplication",
      "operatingSystem": "Linux, macOS, Windows",
      "offers": {
        "@type": "Offer",
        "price": "0",
        "priceCurrency": "USD"
      }
    }
  ]
}
```

Only if those OS names and the free price are on the page. Otherwise stop at Organization.

Three concrete fixes for the weak block: (1) delete `aggregateRating`, (2) add `url` + `logo` + one real `sameAs`, (3) add `SoftwareApplication` only after you can quote the category from the page.

## Output shape

```markdown
## Entity
[type] — [name] — [why this type, not another]

## Detected
| Block | @type | Format | In HTML source? | Issues |
|-------|-------|--------|-----------------|--------|
| … | … | JSON-LD / Microdata / RDFa | yes/no/unverified | … |

## Findings
- [Critical|High|Medium|Low] — [check] — [where] — [fix]

## JSON-LD
[ready-to-paste block, or "existing is honest; no patch"]

## Refused
- [property] — why it would be fiction

## Leftovers
- [skill] — [what you did not pretend to finish]

## Teach
[one reusable sentence]
```

If the markup is already valid and honest, say so. Empty patches are allowed. Invented rich-result promises are not.

## Suite

Doctrine: [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os). Gold Hat: [GOLD_HAT.md](https://github.com/HermeticOrmus/LibreGEO-Grok-Build/blob/main/GOLD_HAT.md). Sibling Libre*-Grok-Build packs: [README suite footer](https://github.com/HermeticOrmus/LibreGEO-Grok-Build/blob/main/README.md).
