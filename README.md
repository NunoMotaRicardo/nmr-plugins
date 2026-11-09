# nmr-plugins — a marketplace for my plugins

The marketplace for the AI plugins I build. One place to add, and each plugin lives in its own repo.

I built it for myself, but the plugins are usable by anyone and contributions are welcome.

## Plugins

| Plugin | What it is | Repo |
|---|---|---|
| `adlc` | My agentic planning and coding workflow: brainstorm, research, plan, implement, review. | [nmr-adlc](https://github.com/NunoMotaRicardo/nmr-adlc) |
| `etoro` | eToro plugin (work in progress, not listed yet). | [e-toro-plugin-ai](https://github.com/NunoMotaRicardo/e-toro-plugin-ai) |

## Add the marketplace

**Claude Code**

```bash
claude plugin marketplace add NunoMotaRicardo/nmr-plugins
claude plugin install adlc@nmr-plugins
```

**Codex**

```bash
codex plugin marketplace add NunoMotaRicardo/nmr-plugins
codex plugin add adlc@nmr-plugins
```

**GitHub Copilot CLI**

```bash
copilot plugin marketplace add NunoMotaRicardo/nmr-plugins
copilot plugin install adlc@nmr-plugins
```

**Cursor** — add the repo as a plugin marketplace and install `adlc`.

**Gemini CLI, Antigravity** — these install directly from a plugin's repo; see that plugin's README.

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
