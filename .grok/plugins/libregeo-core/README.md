# libregeo-core (v0 plugin stub, kept as a dogfood copy)

This was the v0 plugin bundle. It had no manifest and no skills, so it bundled nothing: Grok saw it only as a project plugin with one agent, the stub orchestrator. It stays as the dogfood copy of `stubs/agents/geo-orchestrator.md` (the two files must match; CI checks it).

The installable plugin is now [`plugins/libre-geo-grok/`](https://github.com/HermeticOrmus/LibreGEO-Grok-Build/tree/main/plugins/libre-geo-grok), with its own manifest. Install it with `grok plugin marketplace add HermeticOrmus/LibreGEO-Grok-Build` and `grok plugin install libre-geo-grok@LibreGEO-Grok-Build`.

The melted skills now live in that plugin's `skills/`; the stubs live in `stubs/skills/`. Dogfood copies of both: `.grok/skills/`.
