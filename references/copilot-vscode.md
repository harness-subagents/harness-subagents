# GitHub Copilot / VS Code custom agents — tier A
Sources: docs.github.com/en/copilot/reference/custom-agents-configuration; code.visualstudio.com/docs/copilot/customization/custom-agents; .../docs/agents/run/subagents

- Files: `*.agent.md` (or `.md`), workspace `.github/agents/`. User-level `~/.copilot/agents/` **not confirmed** in fetched pages. Dedup key is the file name minus `.md`/`.agent.md`.
- `name` optional (display name); `description` required; prompt max 30,000 chars.
- `tools`: "If unset, defaults to all tools." **"An empty tools list (tools: []) disables all tools."** `["*"]` = all. Unrecognized tool names are ignored.
- VS Code: "A 'do not edit' instruction alone is not a permission boundary." Match tools to role; a read-only reviewer needs no edit/terminal tools.
- Nesting: local subagents cannot invoke subagents by default; opt-in setting, max depth five.
- Conflicts: lowest level wins (repo over org over enterprise).
- Other fields: `model`, `target`, `user-invocable`, `disable-model-invocation`, `handoffs`.
