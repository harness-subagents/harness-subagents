# Gemini CLI subagents — tier A
Source: github.com/google-gemini/gemini-cli docs/core/subagents.md

- Markdown + YAML: `.gemini/agents/*.md` (project), `~/.gemini/agents/*.md` (user). Body = system prompt.
- `name`: slug, "lowercase letters, numbers, hyphens, and underscores" (underscore allowed, unlike this spec).
- `tools`: array with wildcards; "If omitted, it inherits all tools from the parent session."
- Recursion protection: "subagents cannot call other subagents", even with `*`.
- Defaults: `max_turns` 30, `timeout_mins` 10; `model` inherits.
