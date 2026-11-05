# OpenAI Codex (tier A) and Amp (tier U)
Codex source: developers.openai.com/codex/subagents.md
- Custom agents are **standalone TOML files** in `~/.codex/agents/` and `.codex/agents/`; required fields `name`, `description`. Body instructions live in a TOML field, not Markdown.
- Codex identifies an agent by its `name` field; matching filename is only a convention. Custom agent named like a built-in (`explorer`) takes precedence. Inherits parent permissions/provider/MCP servers.
Amp (ampcode.com): manual pages are JS/login-gated when fetched. A web search found custom agents defined by TypeScript plugins in `.amp/plugins/` (`amp.createAgent`), not Markdown files. Markdown subagent support is **unverified**.
