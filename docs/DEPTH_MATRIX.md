# Depth matrix

Update this table when melting. Status words mean what they say:

| Status | Meaning | Depth |
|--------|---------|-------|
| stub | Thin cue only. Usable as a reminder, not a playbook. | L1–L2 |
| melted | Real Grok skill: when-to-use, steps, measurable checks, example, output shape. | L3–L4 |

This pack is **toward L3–L4**, not L5. Melted skills are playbooks. They are not full reference trees (scripts, multi-file examples, troubleshooting encyclopedias).

Never copy Claude plugin / agent / command totals into this inventory. Upstream [LibreGEO-Claude-Code](https://github.com/HermeticOrmus/LibreGEO-Claude-Code) is proof that the *job* exists, not a count this repo has earned.

| ID | Kind | Status | Source (Claude, for melt) | Notes |
|----|------|--------|---------------------------|-------|
| llms-txt | skill | melted | skills/geo-llmstxt | Spec shape, review + draft, secret scan. No 0–100 score. |
| citation-readiness | skill | melted | skills/geo-citability | Claim checks, severity, rewrites. No citability score theater. |
| schema-markup-geo | skill | melted | skills/geo-schema | Honest JSON-LD, sameAs, refuse fiction. No schema score. |
| geo-audit | skill | stub | skills/geo-audit | Crawlability cue only. |
| ai-search-presence | skill | stub | skills/geo-brand-mentions | Presence cue only. |
| answer-engine-optimize | skill | stub | (content / platform skills) | Extraction-structure cue only. |
| content-freshness | skill | stub | (freshness overlap in several Claude skills) | Date/substance cue only. |
| geo-orchestrator | agent | stub | skills/geo | Coordinates the skills; not a melted specialist. |

This repo now: **3 melted skills**, **4 stub skills**, **1 stub agent**.

Dogfood copies of every skill live at `.grok/skills/<name>/SKILL.md` and must match their source: `plugins/libre-geo-grok/skills/<name>/SKILL.md` for melted skills, `stubs/skills/<name>/SKILL.md` for stubs. CI checks it.

## v1.0.0: where each row lives

Melted skills install as the `libre-geo-grok` plugin. Stubs stay in `stubs/` and never install; each names the pack plugin that holds the real depth. The pack's single `libre-geo` plugin installs from the same marketplace, pinned to one commit of [LibreGEO-Claude-Code](https://github.com/HermeticOrmus/LibreGEO-Claude-Code) (see `.grok-plugin/marketplace.json`). They are installed depth, not this repo's inventory.

| ID | Lives at | Installs | Real depth, installed by this marketplace |
|----|----------|----------|-------------------------------------------|
| llms-txt | `plugins/libre-geo-grok/skills/llms-txt/` | yes, in `libre-geo-grok` | this skill |
| citation-readiness | `plugins/libre-geo-grok/skills/citation-readiness/` | yes, in `libre-geo-grok` | this skill |
| schema-markup-geo | `plugins/libre-geo-grok/skills/schema-markup-geo/` | yes, in `libre-geo-grok` | this skill |
| geo-audit | `stubs/skills/geo-audit/` | no | `geo-audit` skill in `libre-geo` |
| ai-search-presence | `stubs/skills/ai-search-presence/` | no | `geo-brand-mentions` skill in `libre-geo` |
| answer-engine-optimize | `stubs/skills/answer-engine-optimize/` | no | `geo-platform-optimizer` skill in `libre-geo` |
| content-freshness | `stubs/skills/content-freshness/` | no | `geo-content` skill in `libre-geo` |
| geo-orchestrator | `stubs/agents/geo-orchestrator.md` | no | the `geo` skill in `libre-geo` |

## Suite

Doctrine: [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os). Sibling Libre*-Grok-Build packs: [README suite footer](../README.md).
