# LibreGEO-Grok-Build

**GEO / AI-search / llms.txt depth for [Grok Build](https://github.com/HermeticOrmus/grok-build-reality-os)** — ported and melted from [LibreGEO-Claude-Code](https://github.com/HermeticOrmus/LibreGEO-Claude-Code), not a dumb copy.

> Status: **v0 public scaffold** — honest stubs. Melt depth next.

## Why this exists

Answer engines and AI search change discovery. LibreGEO owns GEO patterns (llms.txt, citation readiness, presence). Grok Build needs the same *job* with Grok-native skills — especially relevant near xAI / Grok surfaces.

## Install (<5 min)

See [QUICK_START.md](./QUICK_START.md).

```bash
mkdir -p .grok/skills
cp -R skills/* .grok/skills/
```

Doctrine: install [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os) `AGENTS.md` on the machine first.

## Depth matrix (honest)

| Artifact | v0 scaffold | Upstream Claude (proof) |
|----------|-------------|-------------------------|
| Skills (melted bodies) | 7 stubs → fill next | see upstream suite |
| Agents | 1 (`geo-orchestrator`) | upstream agents |

Counts on the right are **upstream proof**, not this repo's claim until melted.

## First skills

| Skill | Job |
|-------|-----|
| geo-audit | Audit a site/page for AI-search readiness |
| llms-txt | Draft or review llms.txt |
| ai-search-presence | Presence across answer engines |
| citation-readiness | Make claims citeable |
| schema-markup-geo | Structured data that helps discovery |
| answer-engine-optimize | Structure content for answer extraction |
| content-freshness | Freshness signals without spam |

Agent: `AGENTS/geo-orchestrator.md` — full GEO pass.

## Layout (Grok Build)

```
skills/                 # install into .grok/skills or ~/.grok/skills
AGENTS/                 # suite agents
.grok/plugins/          # optional plugin bundle
docs/                   # DEPTH_MATRIX, MELT_RULES
```

## Gold Hat

[GOLD_HAT.md](./GOLD_HAT.md) — empower or extract?

## Suite

- Doctrine: [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os)
- Sibling: [LibreUIUX-Grok-Build](https://github.com/HermeticOrmus/LibreUIUX-Grok-Build)
- Skills packs: [grok-skills](https://github.com/HermeticOrmus/grok-skills) · [grok-build-skills](https://github.com/HermeticOrmus/grok-build-skills)
- Claude proof: [LibreGEO-Claude-Code](https://github.com/HermeticOrmus/LibreGEO-Claude-Code)
- https://ormus.solutions

## License

MIT — see [LICENSE](./LICENSE).
