# CLAUDE.md — module-crew-lead

You are in **`rasa.module.crew.lead`**, the lead tier of galt's crew roles as a RasaOS module. It is not a codebase and not the tenant.

1. **Cards only.** Everything lives under `content/crew/leads/`. Each card is header lines, a blank line, then the body. Keep the placeholders (`{cli}` and `{crew}`); galt fills them.
2. **Galt's code still runs.** Until galt reads these cards, a change here must also go to galt's copy (`packages/router/src/crew/`) by a galt PR, or the two drift.
3. **Gate.** `RASA_SCHEMA_DIR=~/rAI/rasa-os/schema bin/check-cards` must be GREEN before every commit.
4. **Versions.** Change `VERSION`, `rasa.json`, `.claude-plugin/plugin.json`, the README `**Version:**` line and a new `CHANGELOG.md` heading together. Tag `v<VERSION>`; never move a tag.
5. **Nothing that widens.** No `settings.json`, `.mcp.json` or `hooks/`; `rasa.json` `permissions` stays `[]`.
6. **Public.** No secret, credential, customer data or production data, ever.
