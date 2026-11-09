# nmr-plugins — marketplace

Marketplace repo that indexes my AI plugins and publishes them to Claude Code, Codex, GitHub Copilot CLI, Gemini CLI, Antigravity and Cursor. Each plugin lives in its **own repo**; this repo only lists them.

`CLAUDE.md` is a symlink to this file. Edit `AGENTS.md` only.

## Principles
- The portable unit is an Agent Skills folder (`skills/<name>/SKILL.md`). Tool-specific files are packaging.
- This repo holds the marketplace indexes, not plugin content. Plugins are referenced by git source.
- Never hand-edit a generated file; change the source and re-run the generator (once it exists).
- Tool-specific behavior (subagents, `allowed-tools`, etc.) must be flagged in the plugin that uses it, not assumed portable.

## Layout
```
AGENTS.md / CLAUDE.md   agent instructions (symlink)
wiki/                   documentation, mirrored to the GitHub wiki
.github/workflows/      CI (wiki-sync.yml)
```
Indexes (each lists the same plugins, in that tool's format): `.claude-plugin/marketplace.json` (Claude Code, Copilot CLI), `.agents/plugins/marketplace.json` (Codex), `.cursor-plugin/marketplace.json` (Cursor). Gemini CLI and Antigravity install straight from a plugin repo's URL. Planned: `scripts/` to generate the indexes from one source list.

## Conventions
- Adding a plugin: add one entry to the source list, regenerate, validate, document it in `wiki/`.
- Plugin names are kebab-case and unique across the marketplace.
- Versions are owned by the plugin repo, never duplicated here.

## Wiki
- `wiki/` is the source of truth; `Home.md` is the landing page. Do not edit the GitHub wiki directly: the `wiki-sync` workflow overwrites it on push to `main`.
- First-time setup: enable Wikis in repo settings and create one page by hand so the wiki repo exists.
