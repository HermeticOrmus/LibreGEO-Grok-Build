---
name: citation-readiness
description: Make claims citeable for answer engines using Grok Build. Use when content must survive quotation.
---

# Citation Readiness

Make claims extractable and attributable. An answer engine cites a passage it can lift without lying: a self-contained sentence (or short block) that names its subject, states a checkable fact, and points at evidence.

Gold Hat: teach the *why* of each rewrite. A pass that only slaps a fake "citability score" on the page extracts attention. A pass that leaves a reusable claim pattern empowers the next draft.

Do not invent a 0–100 citability score. Severity ranks are enough. Do not invent "expected lift" percentages.

## When to use

- A hero claim, docs page, or blog section must survive being quoted out of context
- Copy is narrative, weasel-heavy, or buried-answer
- You need to list which claims are evidenced vs still unverified

Use `answer-engine-optimize` (still a stub) for page-level extraction structure after the claims are honest. Use `content-freshness` (still a stub) when the problem is a stale date or version, not the sentence shape. Use `schema-markup-geo` (melted) when the missing piece is structured identity, not prose. Call stubs; do not invent their depth.

## Operating steps

1. **Name the job.** Who is asking, what question should this page answer, what is the one primary claim?
2. **Isolate claims.** Pull every sentence that an engine might quote. Drop decoration.
3. **Score each claim on the checks below** — pass / fail / unverified. No composite number.
4. **Rewrite the failures** into quotable sentences. Attach evidence (primary source, dated figure, or first-party method). If evidence is missing, mark the claim **unverified** or cut it.
5. **Teach one sentence.** The pattern the next writer should reuse (answer first, name the subject, attach a source).

Stop if you cannot name the primary question. Ask. Optimizing slogans for "AI visibility" is extraction.

## What makes a passage citeable

Four properties. All four matter. None is a score.

| Property | Pass | Fail |
|----------|------|------|
| Answer-first | First 1–2 sentences answer the question | Hook, tease, or "it depends" with the fact in paragraph four |
| Self-contained | Subject is named; readable with no prior paragraph | Opens with "This", "It", "They", "But" that needs context |
| Fact-bearing | Specific number, date, name, or defined term | Many, leading, significant, seamless, best-in-class |
| Attributable | Evidence link, named source, or first-party method | "Studies show", "experts agree", unsourced superlative |

Useful shape (not a magic word count): one definition or answer sentence, then one supporting fact, in a block an engine can lift. Roughly 40–180 words is enough. Do not pad to a folklore "optimal" length.

### Claim patterns that extract cleanly

- **Definition:** "X is [category] that [does Y]."
- **Measured fact:** "X is [number] [unit] as of [date] ([source])."
- **Comparison:** "X differs from Y in [n] ways: …"
- **Procedure:** "To do X: (1) … (2) … (3) …"

### Weasel list (fail the claim)

best, leading, revolutionary, seamless, blazing, world-class, cutting-edge, "many users", "studies show" (unnamed), "experts agree", "up to" with no floor, "as much as" with no method.

If a number is real but you did not open the source in this pass, keep the number and mark **unverified**.

## Checks per claim

Walk every isolated claim:

1. Can a stranger understand it with only this sentence / short block?
2. Is the subject a noun the query would use, not a pronoun?
3. Is there at least one specific fact (number, date, name, or formal definition)?
4. Is the evidence attached or explicitly missing?
5. Would you be willing to see this sentence quoted next to your name?

A "no" on 1–3 is a High (or Critical if it is the hero claim). A "no" on 4 is High if the claim is strong, Medium if it is color. A "no" on 5 means cut or rewrite — that is Gold Hat, not style.

## Severity

| Rank | Meaning | Example |
|------|---------|---------|
| Critical | Hero claim is unsourced, false, or unquotable | Homepage: "The #1 GEO platform" with no definition and no evidence |
| High | A section answer is buried or weasel-shaped | "CDNs can really help performance" as the only definition |
| Medium | Passage needs the previous heading to make sense | "It reduces latency by caching at the edge." |
| Low | Extra adjective; the fact still stands | "Our comprehensive 2026 guide explains …" |

If unsure, pick the higher rank and say why.

## Worked example — CDN explainer

Job: answer "What is a CDN?" so an engine can quote the opening. Primary claim: a CDN is a distributed cache close to users.

Weak:

```markdown
If you've ever wondered why some sites feel faster, the answer might
surprise you. There's this technology that's been around for a while.
It's changed how we think about performance.
```

No subject, no fact, no source. Critical on the hero block.

Stronger:

```markdown
A content delivery network (CDN) is a set of cache servers that serve
static assets from a location near the reader instead of one origin.
The opening of a page can name the mechanism (cache + proximity) in
one sentence, then attach a dated measurement from a named source.

As of 2025, public vendor documentation from Cloudflare, Amazon
CloudFront, and Akamai describes this edge-cache model; treat any
"50–70% faster" figure as unverified unless you open the study.
```

Critique (abridged):

```markdown
## Job
Reader asks what a CDN is. Primary claim: distributed cache near the user.

## Claims
1. **Critical — answer-first / fact-bearing.** Opening teases and never defines CDN.
   Remediation: "A CDN is …" in sentence one.
2. **High — attributable.** No source for the implied speed claim.
   Remediation: cite a named vendor doc or mark unverified.
3. **Medium — self-contained.** "It's changed how we think" has no subject.

## Fixes now
1. Definition sentence that names CDN.
2. One dated, sourced (or unverified) performance fact — or drop the number.
3. Delete the surprise hook.

## Residual unverified
- Any specific latency-percent claim until a primary source is opened.
```

That is citation-readiness: claims, severity, remediations, leftovers. Not a scorecard.

## Output shape

```markdown
## Job
[who / question / primary claim]

## Claims
| Claim (quote) | Answer-first | Self-contained | Fact-bearing | Evidence | Severity |
|---------------|--------------|----------------|--------------|----------|----------|
| "…" | pass/fail | pass/fail | pass/fail | url or unverified | … |

## Rewrites
1. **[heading or location].** Was: "…" → Now: "…"
   Why: [pattern taught]

## Residual unverified
- [claim] — what would verify it

## Leftovers
- [stub or melted skill] — [what you did not pretend to finish]

## Teach
[one reusable sentence]
```

If every claim already stands, say so. Invented statistics are not allowed. Empty rewrite lists are allowed.

## Suite

Doctrine: [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os). Gold Hat: [GOLD_HAT.md](https://github.com/HermeticOrmus/LibreGEO-Grok-Build/blob/main/GOLD_HAT.md). Sibling Libre*-Grok-Build packs: [README suite footer](https://github.com/HermeticOrmus/LibreGEO-Grok-Build/blob/main/README.md).
