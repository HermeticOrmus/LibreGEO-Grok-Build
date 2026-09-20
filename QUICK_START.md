# Quick Start — LibreGEO for Grok Build

> From a clean machine to one honest llms.txt (and a citation + schema pass) in under 5 minutes.

Doctrine first: put [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os) `AGENTS.md` on the machine (global Grok doctrine). This pack does not replace it.

## Prerequisites

- `git`
- Grok Build installed and able to see skills under `.grok/skills/` or `~/.grok/skills/`
- A site, docs set, or marketing page you own, **or** this repo as the working tree

## Layout this file assumes

Verified against this repository (do not invent extra folders):

```
skills/<name>/SKILL.md          # canonical skill bodies (copy these)
AGENTS/geo-orchestrator.md
docs/DEPTH_MATRIX.md
docs/MELT_RULES.md
.grok/skills/<name>/SKILL.md    # dogfood copy; must match skills/
.grok/plugins/libregeo-core/    # plugin stub; not required for first run
```

Melted (usable now): `skills/llms-txt/SKILL.md`, `skills/citation-readiness/SKILL.md`, `skills/schema-markup-geo/SKILL.md`.
Still stubs: `geo-audit`, `ai-search-presence`, `answer-engine-optimize`, `content-freshness`, plus the orchestrator. Honest table: [docs/DEPTH_MATRIX.md](./docs/DEPTH_MATRIX.md).

## Install (pick one)

### A. Dogfood this repo (fastest)

```bash
git clone https://github.com/HermeticOrmus/LibreGEO-Grok-Build.git
cd LibreGEO-Grok-Build
# Skills are already at .grok/skills/ — open this folder in Grok Build.
```

### B. Install into your site or docs project

```bash
git clone https://github.com/HermeticOrmus/LibreGEO-Grok-Build.git ~/LibreGEO-Grok-Build
cd /path/to/your-site-or-docs-project
mkdir -p .grok/skills
cp -R ~/LibreGEO-Grok-Build/skills/* .grok/skills/
```

Confirm the copy landed:

```bash
test -f .grok/skills/llms-txt/SKILL.md
test -f .grok/skills/citation-readiness/SKILL.md
test -f .grok/skills/schema-markup-geo/SKILL.md
ls .grok/skills
```

You should see seven skill directories, matching `skills/` in this repo.

### C. User-global

```bash
git clone https://github.com/HermeticOrmus/LibreGEO-Grok-Build.git ~/LibreGEO-Grok-Build
mkdir -p ~/.grok/skills
cp -R ~/LibreGEO-Grok-Build/skills/* ~/.grok/skills/
```

Same three `test -f` checks as B, under `~/.grok/skills/`.

Copy `AGENTS/geo-orchestrator.md` only when you want a multi-skill GEO pass. It is still a stub coordinator.

## First-run teach cue

In Grok Build, on a real public page you own:

1. **llms.txt** — "Draft an llms.txt for this site using the llms-txt skill. Public pages only. Mark unverified URLs."
2. **Citation** — "Run citation-readiness on the hero claim: answer-first, self-contained, evidence or unverified. No 0–100 score."
3. **Schema** — "Run schema-markup-geo for the real entity type. JSON-LD only if the facts are on the page. Refuse invented ratings."
4. **Harden (stub)** — "List leftover crawl and freshness items for geo-audit and content-freshness. Do not invent a full GEO score."

You used melted LibreGEO depth on Grok — not a Claude paste, not a fake agent count.

## Smoke checklist

- [ ] `llms-txt`, `citation-readiness`, and `schema-markup-geo` files exist at the install path you chose
- [ ] Grok can see those three skills
- [ ] One llms.txt draft with a factual blockquote and absolute public URLs
- [ ] One citation pass with severity-ranked claims and residual unverified items (no `/100` score)
- [ ] One schema pass that refuses fiction (no invented `aggregateRating`)
- [ ] No secrets, admin paths, or private URLs in prompts, examples, or output

## Suite

- Doctrine: [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os)
- This pack: [LibreGEO-Grok-Build](https://github.com/HermeticOrmus/LibreGEO-Grok-Build)
- Sibling Libre*-Grok-Build packs: [Arch](https://github.com/HermeticOrmus/LibreArch-Grok-Build) · [Copy](https://github.com/HermeticOrmus/LibreCopy-Grok-Build) · [DevOps](https://github.com/HermeticOrmus/LibreDevOps-Grok-Build) · [Embed](https://github.com/HermeticOrmus/LibreEmbed-Grok-Build) · [FinTech](https://github.com/HermeticOrmus/LibreFinTech-Grok-Build) · [GameDev](https://github.com/HermeticOrmus/LibreGameDev-Grok-Build) · [UIUX](https://github.com/HermeticOrmus/LibreUIUX-Grok-Build) · [MLOps](https://github.com/HermeticOrmus/LibreMLOps-Grok-Build) · [MobileDev](https://github.com/HermeticOrmus/LibreMobileDev-Grok-Build) · [SecOps](https://github.com/HermeticOrmus/LibreSecOps-Grok-Build) · [SessionFlow](https://github.com/HermeticOrmus/LibreSessionFlow-Grok-Build) · [WhatsApp](https://github.com/HermeticOrmus/LibreWhatsApp-Grok-Build)
- Skills collections: [grok-skills](https://github.com/HermeticOrmus/grok-skills) · [grok-build-skills](https://github.com/HermeticOrmus/grok-build-skills)
- Claude proof (upstream, not this inventory): [LibreGEO-Claude-Code](https://github.com/HermeticOrmus/LibreGEO-Claude-Code)
- https://ormus.solutions
