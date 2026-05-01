# mempacer-marketplace

Plugin marketplace for the MemPacer ecosystem. Compatible with both
[Claude Code](https://docs.claude.com/en/docs/claude-code/plugin-marketplaces)
and [Codex CLI](https://github.com/openai/codex).

## Install

### Claude Code

```
/plugin marketplace add LogPacer/mempacer-marketplace
/plugin install <plugin-name>@mempacer
```

### Codex

```
codex plugin marketplace add git@github.com:LogPacer/mempacer-marketplace.git
```

Then install `memspec` from the MemPacer marketplace in Codex. The Codex
marketplace manifest lives at [`.agents/plugins/marketplace.json`](.agents/plugins/marketplace.json)
and points at the memspec plugin source in
[`LogPacer/memspec`](https://github.com/LogPacer/memspec).

## Plugins

| Name | Version | Description |
|---|---|---|
| [memspec](https://github.com/LogPacer/memspec) | `v0.1.1` | Spec-discipline framework — `.memspec` DSL + pure-Rust toolchain + agent layer (writer / scrutinizer / implementer / reviewer / slicer) for coupled-state work. |

## Adding a plugin

For Claude Code, edit [`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json)
and bump `metadata.version`.

For Codex, edit [`.agents/plugins/marketplace.json`](.agents/plugins/marketplace.json)
and add a `source: "url"` or `source: "git-subdir"` entry for the plugin's
repository.

Marketplace consumers pull the new manifest on the next
`/plugin marketplace upgrade` (Claude Code) or
`codex plugin marketplace upgrade <marketplace-name>` (Codex).
