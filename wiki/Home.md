# nmr-plugins

Marketplace for my AI plugins, installable from Claude Code, Codex, Copilot CLI, Gemini CLI, Antigravity and Cursor.

## Plugins

| Plugin | Repo | Description |
|---|---|---|
| `adlc` | [NunoMotaRicardo/nmr-adlc](https://github.com/NunoMotaRicardo/nmr-adlc) | Developer lifecycle skills |
| `etoro` | [NunoMotaRicardo/e-toro-plugin-ai](https://github.com/NunoMotaRicardo/e-toro-plugin-ai) | eToro Public API for agents (demo-first trading) |
| `ibkr-cli` | [NunoMotaRicardo/ibkr-cli](https://github.com/NunoMotaRicardo/ibkr-cli) | Go CLI + skill for the IBKR MCP connector (guided OAuth connect) |
| `etoro-cli` | [NunoMotaRicardo/etoro-cli](https://github.com/NunoMotaRicardo/etoro-cli) | Go CLI + skill for the eToro Public API (guided API-key connect) |

## Install

### Claude Code

```bash
claude plugin marketplace add NunoMotaRicardo/nmr-plugins
claude plugin install adlc@nmr-plugins
claude plugin install etoro-cli@nmr-plugins
claude plugin install ibkr-cli@nmr-plugins
```

### Codex

```bash
codex plugin marketplace add NunoMotaRicardo/nmr-plugins
codex plugin add adlc@nmr-plugins
codex plugin add etoro-cli@nmr-plugins
codex plugin add ibkr-cli@nmr-plugins
```

### GitHub Copilot CLI

```bash
copilot plugin marketplace add NunoMotaRicardo/nmr-plugins
copilot plugin install adlc@nmr-plugins
copilot plugin install etoro-cli@nmr-plugins
copilot plugin install ibkr-cli@nmr-plugins
```

### Cursor, Gemini CLI, Antigravity

- **Cursor**: add `NunoMotaRicardo/nmr-plugins` as a plugin marketplace and install the plugin you want.
- **Gemini CLI / Antigravity**: install straight from a plugin's repo URL (for example `gemini extensions install https://github.com/NunoMotaRicardo/etoro-cli`).

## CLI binaries for `etoro-cli` and `ibkr-cli`

The marketplace plugins ship the Agent Skills; the CLI binaries are installed separately with Go (or from each repo's GitHub Releases) and need a one-time `connect` in a terminal:

```bash
go install github.com/NunoMotaRicardo/etoro-cli/cmd/etoro-cli@latest
go install github.com/NunoMotaRicardo/ibkr-cli/cmd/ibkr@latest
```

Make sure `$(go env GOPATH)/bin` is on your `PATH`. See the [etoro-cli wiki](https://github.com/NunoMotaRicardo/etoro-cli/wiki) and [ibkr-cli wiki](https://github.com/NunoMotaRicardo/ibkr-cli/wiki) for full CLI and skill instructions.

## Pages

- Architecture and conventions: see [`AGENTS.md`](https://github.com/NunoMotaRicardo/nmr-plugins/blob/main/AGENTS.md) in the repo.
