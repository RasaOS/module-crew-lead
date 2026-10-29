# module-crew-lead

**Version:** 0.1.0 · `rasa.module.crew.lead` · public

The **lead tier** of a galt crew, as a RasaOS module: the lead tier of a galt crew (galt ADR 0052 D1, 0054 D5): lead cards, each a lead's whole conduct — how it runs a request from ask to landing and whom it hires.

A crew has three tiers, each its own module: [`module-crew-manager`](https://github.com/RasaOS/module-crew-manager) → [`module-crew-lead`](https://github.com/RasaOS/module-crew-lead) → [`module-crew-member`](https://github.com/RasaOS/module-crew-member).

## The cards (`content/crew/leads/`)

| Card | When | Source |
|---|---|---|
| `engineering` | the ask is software: a feature, a fix, an audit of code, infrastructure or a decision about them | galt `router/src/crew/leads.ts` + bus-contract `CREW_BASE_LEADS` at `737a098` |
| `general` | the ask is not one repo's software: research, a lookup, a report, an analysis, or several kinds of work at once | galt `router/src/crew/leads.ts` + bus-contract `CREW_BASE_LEADS` at `737a098` |
| `software-engineer` | the ask is software: a feature, a fix, an audit of code, infrastructure or a decision about them; the operator's own standards apply | RasaOS/module-crew `content/crew/leads/software-engineer.md` at `f6fea0d` |

A card is one markdown file: `key: value` header lines, a blank line, then the conduct (galt ADR 0052 D1, `tags:` from ADR 0054 D2). `{cli}` and `{crew}` are filled by galt when the lead reads its card (`galt crew lead <crew>`).

## Using it

- **Install into a repo** (the brain layer): the cards land in `.claude/crew/leads/`, where galt finds a repo's own cards.
- **Load into a session:** `.claude-plugin/plugin.json` makes the repo loadable (galt ADR 0064).
- **Source of truth today:** galt's in-code copies (`packages/router/src/crew/`) are what runs. This repo is a snapshot of them until galt reads its cards from here, with its code as the fallback.

## Changing a card

Change it here in a PR. `bin/check-cards` must be GREEN (`RASA_SCHEMA_DIR=~/rAI/rasa-os/schema bin/check-cards`). Bump the version: patch for wording, minor for a new card or header key. Until galt reads from here, mirror the change into galt's copy.
