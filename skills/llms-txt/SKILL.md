---
name: llms-txt
description: Draft or review llms.txt for Grok Build / GEO. Use when publishing machine-readable site guidance for AI agents.
---

# llms.txt

Draft honest machine guidance. `llms.txt` is a public Markdown file at the site root that tells agents what the site is and which pages are canonical. It is not `robots.txt` (access rules) and it is not a marketing page.

Gold Hat: name the public facts first, then teach the format while you write. Leave the person able to update the file after the next ship without you. Private URLs, secrets, and invented facts do not ship.

The emerging convention is documented at [llmstxt.org](https://llmstxt.org/) (Jeremy Howard, 2024). Follow that shape. Do not invent a competing dialect.

## When to use

- A site has no `/llms.txt` and you need a first honest draft
- An existing `/llms.txt` needs a review against the live nav and sitemap
- You are choosing which public pages an agent should treat as canonical
- You are deciding whether `/llms-full.txt` is warranted

Do not use this skill as a full GEO audit. After the file is honest, hand crawl/index leftovers to `geo-audit` (still a stub) and presence leftovers to `ai-search-presence` (still a stub). Call the stub; do not invent its depth.

Stop if you cannot name the site purpose in one factual sentence. Ask. Guessing a brand story is extraction.

## Operating steps

1. **Name the job.** What is this site, who is it for, which 3–8 public pages are the source of truth?
2. **Discover what exists.** Fetch `/llms.txt` and `/llms-full.txt`. Record HTTP status (200 / 404 / 403 / redirect). Fetch the homepage, primary nav, and `/sitemap.xml` when available. List candidate pages.
3. **Prioritize.** Keep public, authoritative, unique pages. Drop thin tags, pagination, login, admin, staging, and anything you would not want quoted.
4. **Write or rewrite** using the format below. Absolute `https://` URLs only. Descriptions are facts about the page, not slogans.
5. **Scan for secrets.** No tokens, no private paths, no unpublished URLs, no internal tools.
6. **Teach one sentence.** How the owner should refresh this file after the next content ship.

If a listed URL is unverified (you did not fetch it), mark it **unverified**. Do not claim 200.

## Format (measurable)

Root location:

```
https://example.com/llms.txt
```

Required shape:

```markdown
# [Official site or product name]

> [One factual sentence: what it is and who it serves. Under 200 characters.]

## Docs

- [Page title](https://example.com/canonical-path): What a reader actually finds on this page.
```

| Check | Pass | Fail |
|-------|------|------|
| Location | Served at `/llms.txt` on the canonical host, no auth | Only in a repo, or behind login, or a random `/ai/llms.txt` path you cannot move |
| Title | First line is `#` official name | H1 is a slogan or missing |
| Description | Immediate `>` blockquote, ≤200 chars, no superlatives | Marketing fluff, or longer than a tweet |
| Sections | At least one `##` group that matches real nav | One undifferentiated dump, or sections that do not exist on the site |
| Entries | 8–30 public pages; each `- [title](absolute-url): fact` | Relative paths, missing descriptions, or 80 thin URLs |
| Order | Most authoritative page first inside each section | Blog index above the product or docs source of truth |
| Secrets | Public pages only | Staging, admin, preview, or credentialed URLs |
| Length | Roughly 40–150 lines for `llms.txt` | A novel, or five lines of vibes |

Recommended (not required): `## Key Facts` (dated, public, checkable) and `## Contact` (a real public email or support URL). Skip a fact you cannot source.

`llms-full.txt` is optional. Use it when the short file cannot hold the docs graph (more pages, longer per-page notes). Do not generate a "full" file that repeats marketing.

### What to include vs skip

**Usually include:** homepage, product or docs landing, pricing (if public), about, contact, the 3–5 pages you want cited.

**Include when they are actually strong:** a flagship guide, a changelog, a real FAQ, a case study with named outcomes.

**Skip:** tag/category indexes, pagination, login/signup, legal boilerplate unless the job is legal, near-duplicates, pages blocked from the agents you care about.

Coordinate with `robots.txt`: do not list a page you are telling AI crawlers to skip.

### Description quality

| Weak | Stronger |
|------|----------|
| Our amazing pricing page! | Lists Free, Pro, and Enterprise with monthly and annual prices. |
| Learn more about the company. | Founding year, team size if public, and office locations as stated on /about. |
| Click here for the API. | Auth, rate limits, and the three primary endpoints documented on /docs/api. |

Banned in descriptions: best, leading, revolutionary, seamless, click here.

## Review mode (existing file)

Walk this table. Severity ranks findings. Do not invent a 0–100 score.

| Element | If missing or wrong | Severity |
|---------|---------------------|----------|
| `#` title | File has no official name | Critical |
| `>` description | Missing, >200 chars, or unsourced boast | High |
| One `##` section | No grouping | Critical |
| ≥5 real entries | Too thin to be useful | High |
| Absolute https URLs | Relative or protocol-less | High |
| Reachable URLs | 404 / 403 / unexpected redirect | Medium (mark unverified if unfetched) |
| Description after colon | Title-only bullets | Medium |
| Key Facts / Contact | Absent | Low (recommend, do not fail the file) |
| Secret or private URL | Present | Critical — delete |

Then compare to nav + sitemap. List important public pages that are absent. List entries that are stale (page retitled, redirected, or emptied).

## Worked example — small docs site

Job: help agents cite the product, the install guide, and the public API. Site: `https://example.com` (fictional).

Weak:

```markdown
# Welcome!!

We are the leading next-gen platform.

- /docs
- /admin/metrics
```

Relative path, slogan, and an internal URL.

Stronger:

```markdown
# Example Docs

> Public documentation for Example, an open-source CLI that turns site maps into llms.txt drafts.

## Docs

- [Home](https://example.com/): What Example is and the current stable version.
- [Install](https://example.com/docs/install): Supported OS list and the two install methods (binary, source).
- [llms.txt format](https://example.com/docs/llms-txt): Required title, blockquote, and link-entry rules with examples.
- [API](https://example.com/docs/api): Auth header, rate limits, and the `/draft` and `/review` endpoints.

## Key Facts

- First public release: 2026-03-01
- License: MIT
- Canonical repo: https://github.com/example/example

## Contact

- Website: https://example.com
- Issues: https://github.com/example/example/issues
```

Three concrete fixes if you only have the weak file: (1) replace the slogan with one factual sentence, (2) promote `/docs` to an absolute URL with a real description, (3) delete `/admin/metrics`.

## Output shape

```markdown
## Job
[site / audience / which pages must be citeable]

## Status
- /llms.txt: [200 | 404 | 403 | redirect | unverified]
- /llms-full.txt: [same]

## Findings
- [severity] — [element] — [current] → [needed]

## Draft
[complete llms.txt, ready to save at site root]

## Leftovers
- [page] — why it was excluded, or which stub skill owns the next pass

## Teach
[one reusable sentence for the next update]
```

If the existing file is already honest, say so. Empty findings are allowed. Invented pages are not.

## Suite

Doctrine: [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os). Gold Hat: [GOLD_HAT.md](https://github.com/HermeticOrmus/LibreGEO-Grok-Build/blob/main/GOLD_HAT.md). Sibling Libre*-Grok-Build packs: [README suite footer](https://github.com/HermeticOrmus/LibreGEO-Grok-Build/blob/main/README.md).
