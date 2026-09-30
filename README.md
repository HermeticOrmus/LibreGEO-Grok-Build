<p align="center">
  <img src="https://ormus.solutions/mascot/pixellab_liquid_to_compass.gif" alt="LibreGEO Grok Build" width="128" style="image-rendering: pixelated;" />
</p>

<h1 align="center">LibreGEO Grok Build</h1>

<p align="center">
  <em>GEO in your Grok Build session: honest llms.txt, citation and schema skills melted for Grok, plus the LibreGEO pack by pinned commit</em>
</p>

<p align="center">
  <a href="https://github.com/HermeticOrmus/LibreGEO-Grok-Build/stargazers"><img src="https://img.shields.io/github/stars/HermeticOrmus/LibreGEO-Grok-Build?style=flat-square&color=aa8142" alt="Stars" /></a>
  <a href="https://github.com/HermeticOrmus/LibreGEO-Grok-Build/blob/main/LICENSE"><img src="https://img.shields.io/github/license/HermeticOrmus/LibreGEO-Grok-Build?style=flat-square&color=aa8142" alt="License" /></a>
  <a href="https://github.com/HermeticOrmus/LibreGEO-Grok-Build/commits"><img src="https://img.shields.io/github/last-commit/HermeticOrmus/LibreGEO-Grok-Build?style=flat-square&color=aa8142" alt="Last Commit" /></a>
  <img src="https://img.shields.io/badge/GEO-aa8142?style=flat-square" alt="GEO" />
  <img src="https://img.shields.io/badge/Grok_Build-aa8142?style=flat-square&logo=x&logoColor=white" alt="Grok Build" />
</p>

---

**GEO / AI-search / llms.txt depth for [Grok Build](https://github.com/HermeticOrmus/grok-build-reality-os)** — ported and melted from [LibreGEO-Claude-Code](https://github.com/HermeticOrmus/LibreGEO-Claude-Code), not a dumb copy.

> Status: **v1.0.0**. The three melted skills (`llms-txt`, `citation-readiness`, `schema-markup-geo`) install as the `libre-geo-grok` plugin, and the pack's `libre-geo` plugin (the whole LibreGEO-Claude-Code pack is one plugin) installs beside them from the same marketplace, pinned by commit. The four stubs stay in `stubs/` and do not install. See [docs/DEPTH_MATRIX.md](./docs/DEPTH_MATRIX.md) and the [kintsugi ledger](./LEDGER.md).

## Why this exists

Answer engines and AI search change discovery. LibreGEO owns GEO patterns (llms.txt, citation readiness, presence). Grok Build needs the same *job* with Grok-native skills — especially relevant near xAI / Grok surfaces. This repo counts only what it has melted.

## Install (<5 min)

See [QUICK_START.md](./QUICK_START.md) for the marketplace, dogfood, and copy paths.

```bash
grok plugin marketplace add HermeticOrmus/LibreGEO-Grok-Build
grok plugin install libre-geo-grok@LibreGEO-Grok-Build
# The whole LibreGEO-Claude-Code pack, one plugin, pinned by commit:
grok plugin install libre-geo@LibreGEO-Grok-Build
grok plugin list
```

Doctrine: install [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os) `AGENTS.md` on the machine first.

## Depth (honest)

| Artifact | This repo now | Installed from the pack |
|----------|---------------|-------------------------|
| Skills | 3 melted, in the `libre-geo-grok` plugin; 4 stubs in `stubs/skills/`, not installed | The skills inside `libre-geo` |
| Agents | 1 stub (`geo-orchestrator`) in `stubs/agents/`, not installed | The `libre-geo` plugin's GEO agents |
| Plugins | 1 (`libre-geo-grok`, v1.0.0) | 1 (`libre-geo`, the whole pack), pinned by commit in `.grok-plugin/marketplace.json` |

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

The melted skills install as the `libre-geo-grok` plugin. The stubs live in `stubs/skills/` and do not install; each one names the pack plugin that holds the real depth, and [docs/DEPTH_MATRIX.md](./docs/DEPTH_MATRIX.md) maps them all.

Agent: `stubs/agents/geo-orchestrator.md`, the stub coordinator for a full GEO pass. It does not install.

## Layout (Grok Build)

```
.grok-plugin/marketplace.json  # marketplace: the Grok-native plugin, then the pack's plugins by pinned commit
plugins/libre-geo-grok/        # the Grok-native plugin (manifest in .grok-plugin/plugin.json)
  skills/                      # the melted SKILL.md bodies (canonical)
stubs/skills/                  # stub cues; not installed; each names the pack plugin with the depth
stubs/agents/                  # the stub orchestrator; not installed
scripts/pin-pack.sh            # re-pins the pack entries to the pack's main HEAD
docs/                          # DEPTH_MATRIX, MELT_RULES
LEDGER.md                      # kintsugi ledger: the cracks and their seals
.grok/skills/                  # dogfood copy of the plugin skills and the stubs (CI keeps it in sync)
.grok/plugins/libregeo-core/   # v0 bundle stub, kept as the dogfood copy of the stub orchestrator
```

Claude's `.claude/` maps to Grok skills + `AGENTS.md` + `.grok/`. Melt rules: [docs/MELT_RULES.md](./docs/MELT_RULES.md).

## Gold Hat

[GOLD_HAT.md](./GOLD_HAT.md) — empower or extract? For this pack: no fake GEO scores, no invented ratings, no secrets in llms.txt.

The pack's `libre-geo` plugin installs from the same marketplace and does report 0-100 scores (for example its `geo-citability` and `geo-audit` skills). The three Grok-native skills here do not. When you want a score-free pass, call them by name: `libre-geo-grok:citation-readiness`, `libre-geo-grok:llms-txt`, `libre-geo-grok:schema-markup-geo` ([LEDGER.md](./LEDGER.md)).

## Kintsugi ledger

[LEDGER.md](./LEDGER.md) lists every crack found in the v0 edition, the evidence, and the seal this release put on it. Open cracks stay open in plain sight until someone seals them.

## Feedback

Tell us what worked and what is missing: [feedback form](https://github.com/HermeticOrmus/LibreGEO-Grok-Build/issues/new?template=feedback.yml). Grok picked the wrong skill? [Report a routing miss](https://github.com/HermeticOrmus/LibreGEO-Grok-Build/issues/new?template=routing-miss.yml). Want a new skill or plugin? [Propose it](https://github.com/HermeticOrmus/LibreGEO-Grok-Build/issues/new?template=plugin-proposal.yml). Ways to contribute: [CONTRIBUTING.md](./CONTRIBUTING.md).

## Suite

- Doctrine: [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os)
- This pack: [LibreGEO-Grok-Build](https://github.com/HermeticOrmus/LibreGEO-Grok-Build)
- Sibling Libre*-Grok-Build packs: [Arch](https://github.com/HermeticOrmus/LibreArch-Grok-Build) · [Copy](https://github.com/HermeticOrmus/LibreCopy-Grok-Build) · [DevOps](https://github.com/HermeticOrmus/LibreDevOps-Grok-Build) · [Embed](https://github.com/HermeticOrmus/LibreEmbed-Grok-Build) · [FinTech](https://github.com/HermeticOrmus/LibreFinTech-Grok-Build) · [GameDev](https://github.com/HermeticOrmus/LibreGameDev-Grok-Build) · [UIUX](https://github.com/HermeticOrmus/LibreUIUX-Grok-Build) · [MLOps](https://github.com/HermeticOrmus/LibreMLOps-Grok-Build) · [MobileDev](https://github.com/HermeticOrmus/LibreMobileDev-Grok-Build) · [SecOps](https://github.com/HermeticOrmus/LibreSecOps-Grok-Build) · [SessionFlow](https://github.com/HermeticOrmus/LibreSessionFlow-Grok-Build) · [WhatsApp](https://github.com/HermeticOrmus/LibreWhatsApp-Grok-Build)
- Skills collections: [grok-skills](https://github.com/HermeticOrmus/grok-skills) · [grok-build-skills](https://github.com/HermeticOrmus/grok-build-skills)
- Claude proof: [LibreGEO-Claude-Code](https://github.com/HermeticOrmus/LibreGEO-Claude-Code)
- https://ormus.solutions

## License

MIT — see [LICENSE](./LICENSE).
