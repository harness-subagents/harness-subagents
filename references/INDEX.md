# References index

Distilled sources for asserting documentation claims without refetching.
Fetched 2026-11-05. Quotes are under 30 words; everything else is paraphrase.
Trust order when sources disagree: **A** vendor/spec docs → **B** vendor engineering posts → **C** expert/community → **U** unverified.

| File | Source (URL) | Tier | Use it to assert |
|------|--------------|------|------------------|
| [agent-skills.md](agent-skills.md) | agentskills.io: specification, client-implementation/adding-skills-support, skill-creation/{best-practices,optimizing-descriptions,evaluating-skills} | A | name/description limits, `metadata`, `.agents/` cascade, collisions, trust, lenient validation, 500-line rule, eval/description-testing method |
| [claude-code.md](claude-code.md) | code.claude.com/docs/en/{sub-agents,headless,cli-reference} | A | Claude Code paths, `tools` inheritance, nesting depth, `AskUserQuestion` removal, name≠filename, `--output-format` behavior |
| [copilot-vscode.md](copilot-vscode.md) | docs.github.com custom-agents-configuration; code.visualstudio.com custom-agents + subagents | A | Copilot/VS Code paths, `tools: []` semantics, nesting, "instructions are not a permission boundary" |
| [gemini-cli.md](gemini-cli.md) | gemini-cli docs/core/subagents.md | A | Gemini paths, name charset, no nesting, `tools` inheritance |
| [opencode.md](opencode.md) | opencode.ai/docs/agents | A | OpenCode paths, name = filename, `tools` deprecated |
| [codex-amp.md](codex-amp.md) | developers.openai.com/codex/subagents; ampcode.com | A / U | Codex uses TOML; Amp file format unverified |
| [model-effort.md](model-effort.md) | platform.claude.com effort; platform.openai.com reasoning | A | real `effort` values and defaults |
| [multi-agent-practice.md](multi-agent-practice.md) | anthropic.com/engineering/multi-agent-research-system; cognition.com/blog/dont-build-multi-agents | B / C | delegation brief contents, token cost, files-not-prose, shared-decision failure |
| [protocols.md](protocols.md) | modelcontextprotocol.io; a2a-protocol.org | A | what MCP and A2A actually connect |

Not found in any source (treat as **U**): "a subagent without edit tools stops considering edits"; "parents match boundary keywords like trigger keywords"; "several hundred lines" for subagent bodies (the 500-line figure is a *skills* rule); `.agents/agents/` as an existing convention; Amp markdown subagents; Markdown/YAML-only claim for Codex.
