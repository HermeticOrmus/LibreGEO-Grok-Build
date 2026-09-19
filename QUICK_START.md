# Quick Start — LibreGEO for Grok Build

> From zero to a GEO audit in under 5 minutes.

## Prerequisites

- Grok Build installed and working
- A site, docs set, or marketing page to improve

## Install skills (repo-local)

```bash
git clone https://github.com/HermeticOrmus/LibreGEO-Grok-Build.git
cd your-project
mkdir -p .grok/skills
cp -R /path/to/LibreGEO-Grok-Build/skills/* .grok/skills/
```

Or user-global:

```bash
mkdir -p ~/.grok/skills
cp -R /path/to/LibreGEO-Grok-Build/skills/* ~/.grok/skills/
```

## First-run teach cue

1. **Audit** — "Run geo-audit on this URL/page: crawlability, clarity, citeability."
2. **llms.txt** — "Draft an llms.txt for this site using the llms-txt skill."
3. **Harden** — "Run citation-readiness and content-freshness on the hero claim."

## Smoke checklist

- [ ] Skills visible to Grok
- [ ] One GEO audit with measurable gaps
- [ ] One llms.txt draft produced
