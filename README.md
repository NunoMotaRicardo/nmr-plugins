# nmr-plugins — a marketplace for my plugins

The marketplace for the AI plugins I build. One place to add, and each plugin lives in its own repo.

I built it for myself, but the plugins are usable by anyone and contributions are welcome.

## Plugins

| Plugin | What it is | Repo |
|---|---|---|
| `adlc` | My agentic planning and coding workflow: brainstorm, research, plan, implement, review. | [nmr-adlc](https://github.com/NunoMotaRicardo/nmr-adlc) |
| `etoro` | eToro Public API for agents: market data, portfolio, demo-first trading, guided key setup. | [e-toro-plugin-ai](https://github.com/NunoMotaRicardo/e-toro-plugin-ai) |
| `ibkr-cli` | Token-lean Go CLI and skill for the Interactive Brokers MCP connector, guided OAuth connect. | [ibkr-cli](https://github.com/NunoMotaRicardo/ibkr-cli) |
| `etoro-cli` | Token-lean Go CLI and skill for the eToro Public API, guided API-key connect. | [etoro-cli](https://github.com/NunoMotaRicardo/etoro-cli) |

## Add the marketplace and install a plugin

**Claude Code**

```bash
claude plugin marketplace add NunoMotaRicardo/nmr-plugins
claude plugin install adlc@nmr-plugins
# or install one of the CLI plugins:
claude plugin install etoro-cli@nmr-plugins
claude plugin install ibkr-cli@nmr-plugins
```

**Codex**

```bash
codex plugin marketplace add NunoMotaRicardo/nmr-plugins
codex plugin add adlc@nmr-plugins
# or: codex plugin add etoro-cli@nmr-plugins / ibkr-cli@nmr-plugins
```

**GitHub Copilot CLI**

```bash
copilot plugin marketplace add NunoMotaRicardo/nmr-plugins
copilot plugin install adlc@nmr-plugins
# or: copilot plugin install etoro-cli@nmr-plugins / ibkr-cli@nmr-plugins
```

**Cursor** — add `NunoMotaRicardo/nmr-plugins` as a plugin marketplace and install `adlc`, `etoro-cli`, or `ibkr-cli`.

**Gemini CLI, Antigravity** — install directly from a plugin's repo (for example `gemini extensions install https://github.com/NunoMotaRicardo/etoro-cli`); see that plugin's README.

For the CLI plugins (`etoro-cli` and `ibkr-cli`), the plugin installs the Agent Skill; install the matching Go binary separately (`go install`) and run `connect` once in a terminal before using it with an agent:

```bash
go install github.com/NunoMotaRicardo/etoro-cli/cmd/etoro-cli@latest
go install github.com/NunoMotaRicardo/ibkr-cli/cmd/ibkr@latest
```

Claude Code is what I use daily. The other tools are supported on a best-effort basis, so if something doesn't work in yours, please open an issue.

## How it is organised

This repo only holds the marketplace indexes, one per tool format, all listing the same plugins:

```
.claude-plugin/marketplace.json   Claude Code and Copilot CLI
.agents/plugins/marketplace.json  Codex
.cursor-plugin/marketplace.json   Cursor
```

Plugins are referenced by their git repo, so each is developed, versioned and released on its own.

## Contributing

Contributions are welcome: fixes for a tool's marketplace format, support for more tools, and ideas for plugins. Open an issue or a pull request; see [`AGENTS.md`](AGENTS.md) for the conventions. Plugin-specific changes belong in that plugin's repo.

More documentation is on the [wiki](https://github.com/NunoMotaRicardo/nmr-plugins/wiki).

## License

[MIT](LICENSE)
