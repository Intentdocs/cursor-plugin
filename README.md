# IntentDocs plugin for Cursor

A Cursor plugin that connects [IntentDocs](https://www.intentdocs.com/connect/cursor) and carries the spec and build steps. Cursor discovers `.cursor-plugin/plugin.json`, `mcp.json` and `skills/`. [cursor.directory](https://cursor.directory) discovers `.mcp.json` and the same `skills/` tree.

| File | What it is |
|---|---|
| `.cursor-plugin/plugin.json` | Cursor plugin manifest (name, author, homepage, repository, licence, keywords, logo). |
| `mcp.json` | The IntentDocs MCP server for Cursor. |
| `.mcp.json` | The same server, so a cursor.directory scan finds it. |
| `skills/spec-my-idea/SKILL.md` | Generated from `packages/docs/src/lib/spec-my-idea.ts`. |
| `skills/build-a-story/SKILL.md` | Generated from the claimed-story build loop in `src/lib/agent-build-loop.ts`. |
| `assets/logo.svg` | The IntentDocs logo (`public/logo-mark.svg`, the mark shipped with the ChatGPT plugin). |

## Placeholder repository

The `repository` field in `.cursor-plugin/plugin.json` is `https://github.com/intentdocs/cursor-plugin`.

**That URL is a placeholder.** The public repository does not exist yet. Do not treat it as the source of this package, and do not publish or clone it, until the repository is created and this field is updated to the real URL.

## Licence

MIT. See `LICENSE`.

## MCP

Both `.mcp.json` and `mcp.json` point at `https://www.intentdocs.com/api/mcp`. They contain no API keys, tokens or other secrets. Cursor asks the person to sign in when they connect.

## Skills

Do not edit the `SKILL.md` files by hand. In the IntentDocs repo, regenerate them from the single sources:

```bash
node scripts/generate-cursor-plugin-skills.mjs
```

`node scripts/generate-cursor-plugin-skills.mjs --check` exits 1 if the committed skills have drifted. The Vitest suite checks the same thing.

## Export a standalone folder

From the IntentDocs repo, copy this package to a directory you can push to its own public repository. The command does not create a repository and does not push.

```bash
node scripts/export-cursor-plugin.mjs
```

An optional path overrides the default destination, `cursor-plugin-export/` at the repo root (gitignored):

```bash
node scripts/export-cursor-plugin.mjs /path/to/dest
```

## Try it locally

Copy the exported folder to `~/.cursor/plugins/local/intentdocs` and reload Cursor. Connecting opens IntentDocs sign-in. Nothing in this package authenticates on its own.
