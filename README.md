# LibreGEO-Grok-Build

**GEO / AI-search / llms.txt depth for [Grok Build](https://github.com/HermeticOrmus/grok-build-reality-os)** — ported and melted from [LibreGEO-Claude-Code](https://github.com/HermeticOrmus/LibreGEO-Claude-Code), not a dumb copy.

> Status: **public v0 toward L3–L4** — three skills melted (`llms-txt`, `citation-readiness`, `schema-markup-geo`); the rest are honest stubs. See [docs/DEPTH_MATRIX.md](./docs/DEPTH_MATRIX.md).

## Why this exists

Answer engines and AI search change discovery. LibreGEO owns GEO patterns (llms.txt, citation readiness, presence). Grok Build needs the same *job* with Grok-native skills — especially relevant near xAI / Grok surfaces. This repo counts only what it has melted.

## Install (<5 min)

See [QUICK_START.md](./QUICK_START.md) for clone, dogfood, project-local, and user-global paths.

```bash
git clone https://github.com/HermeticOrmus/LibreGEO-Grok-Build.git
cd LibreGEO-Grok-Build
# Dogfood: .grok/skills/ already has the skill bodies.
# Other project: cp -R skills/* /path/to/your-project/.grok/skills/
```

Doctrine: install [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os) `AGENTS.md` on the machine first.

## Depth (honest)

| Artifact | This repo now | Upstream Claude |
|----------|---------------|-----------------|
| Skills | 3 melted + 4 stubs | Proof the job exists; not our inventory |
| Agents | 1 stub (`geo-orchestrator`) | Proof the job exists; not our inventory |
| Plugins | 1 core bundle stub | Proof the job exists; not our inventory |

Melted = L3–L4 playbook (when-to-use, steps, checks, example, output shape). Stub = L1–L2 cue. Do not paste Claude plugin/agent/command totals here. Update [docs/DEPTH_MATRIX.md](./docs/DEPTH_MATRIX.md) when something melts.

## Skills

| Skill | Status | Job |
|-------|--------|-----|
| llms-txt | melted | Draft or review `/llms.txt` |
| citation-readiness | melted | Make claims extractable and attributable |
| schema-markup-geo | melted | Honest schema.org JSON-LD |
| geo-audit | stub | Site/page AI-search readiness |
| ai-search-presence | stub | Presence across answer engines |
| answer-engine-optimize | stub | Structure for answer extraction |
| content-freshness | stub | Freshness signals without fake dates |

Agent: `AGENTS/geo-orchestrator.md` — stub coordinator for a full GEO pass.

## Layout (Grok Build)

```
skills/                 # canonical SKILL.md bodies
AGENTS/                 # suite agents
docs/                   # DEPTH_MATRIX, MELT_RULES
.grok/skills/           # dogfood copy of skills/ (keep in sync)
.grok/plugins/          # optional plugin bundle stub
```

Claude's `.claude/` maps to Grok skills + `AGENTS.md` + `.grok/`. Melt rules: [docs/MELT_RULES.md](./docs/MELT_RULES.md).

## Gold Hat

[GOLD_HAT.md](./GOLD_HAT.md) — empower or extract? For this pack: no fake GEO scores, no invented ratings, no secrets in llms.txt.

## Suite

- Doctrine: [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os)
- This pack: [LibreGEO-Grok-Build](https://github.com/HermeticOrmus/LibreGEO-Grok-Build)
- Sibling Libre*-Grok-Build packs: [Arch](https://github.com/HermeticOrmus/LibreArch-Grok-Build) · [Copy](https://github.com/HermeticOrmus/LibreCopy-Grok-Build) · [DevOps](https://github.com/HermeticOrmus/LibreDevOps-Grok-Build) · [Embed](https://github.com/HermeticOrmus/LibreEmbed-Grok-Build) · [FinTech](https://github.com/HermeticOrmus/LibreFinTech-Grok-Build) · [GameDev](https://github.com/HermeticOrmus/LibreGameDev-Grok-Build) · [UIUX](https://github.com/HermeticOrmus/LibreUIUX-Grok-Build) · [MLOps](https://github.com/HermeticOrmus/LibreMLOps-Grok-Build) · [MobileDev](https://github.com/HermeticOrmus/LibreMobileDev-Grok-Build) · [SecOps](https://github.com/HermeticOrmus/LibreSecOps-Grok-Build) · [SessionFlow](https://github.com/HermeticOrmus/LibreSessionFlow-Grok-Build) · [WhatsApp](https://github.com/HermeticOrmus/LibreWhatsApp-Grok-Build)
- Skills collections: [grok-skills](https://github.com/HermeticOrmus/grok-skills) · [grok-build-skills](https://github.com/HermeticOrmus/grok-build-skills)
- Claude proof: [LibreGEO-Claude-Code](https://github.com/HermeticOrmus/LibreGEO-Claude-Code)
- https://ormus.solutions

## License

MIT — see [LICENSE](./LICENSE).
