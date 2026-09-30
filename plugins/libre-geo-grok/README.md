# libre-geo-grok

The Grok-native layer of [LibreGEO-Grok-Build](https://github.com/HermeticOrmus/LibreGEO-Grok-Build): three skills melted for Grok Build.

| Skill | Job |
|-------|-----|
| `llms-txt` | Draft or review `/llms.txt` |
| `citation-readiness` | Make claims extractable and attributable |
| `schema-markup-geo` | Honest schema.org JSON-LD |

## Install

```bash
grok plugin marketplace add HermeticOrmus/LibreGEO-Grok-Build
grok plugin install libre-geo-grok@libre-geo-grok
```

The same marketplace offers the whole LibreGEO-Claude-Code pack as one plugin, `libre-geo`, pinned by commit.

The stubs (`geo-audit`, `ai-search-presence`, `answer-engine-optimize`, `content-freshness`) and the stub orchestrator are not part of this plugin. They live in [`stubs/`](https://github.com/HermeticOrmus/LibreGEO-Grok-Build/tree/main/stubs), and each names the pack plugin with the real depth. Honest table: [docs/DEPTH_MATRIX.md](https://github.com/HermeticOrmus/LibreGEO-Grok-Build/blob/main/docs/DEPTH_MATRIX.md).

Gold Hat: [GOLD_HAT.md](https://github.com/HermeticOrmus/LibreGEO-Grok-Build/blob/main/GOLD_HAT.md)
