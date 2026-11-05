# Harness Subagents

A standardized way to define reusable subagents for AI agent harnesses.

## What are Harness Subagents?

Harness Subagents are a lightweight, open format for packaging delegated work so a parent agent can hand it off, reliably, to a child agent.

At its core, a subagent is a single Markdown file. This file includes metadata (`name` and `description`, at minimum) and a body of instructions that a harness gives to the subagent as its system prompt when the parent delegates work to it.

```markdown
---
name: repo-explorer
description: Maps how a codebase implements a feature. Use before planning changes.
complexity: low
---

You explore a codebase and report structure. You do not edit files.
...
```

## Why Harness Subagents?

A parent agent's context is its most expensive resource, and output is a lot more. Subagents solve this by moving focused work into an isolated context and returning only the result. This gives agent harnesses:

- **Context isolation**: Search noise, long tool output and intermediate drafts stay inside the subagent. The parent receives the deliverable, not the process.
- **Reliable delegation**: The `description` is all the parent reads before delegating, so well-written files make the parent delegate at the right times.
- **Cheaper, faster results**: Less expensive agentic work is done by efficient models, faster and avoiding over-expenditure.
- **Cross-harness reuse**: Build a subagent once and use it across any compatible harness.

## How do Harness Subagents work?

A subagent runs through a four-stage lifecycle:

1. **Discovery**: At startup, the harness loads each subagent's name and description, just enough for the parent to know when delegation might help.

2. **Delegation**: When a task matches a subagent's description, the parent delegates it with an objective, an expected deliverable and clear task boundaries.

3. **Execution**: The harness spawns the subagent with the file's body as its system prompt, in an isolated context with no human in the loop.

4. **Return**: The subagent reports the deliverable directly back to the parent, which keeps only what it needs.

The subagent works without directly steering, pausing or questions to the user. All user-facing communication flows through the parent.

## Where can I use Harness Subagents?

Subagent support is spreading fast across agentic tools. File-based subagent formats exist today in Claude Code, GitHub Copilot, VS Code, Gemini CLI, OpenCode, OpenAI Codex and Amp, among others. This format mirrors their common shape, so a subagent written once maps naturally onto each of them, leaving room for custom adaptations for their model catalog and thinking effort.

## Open development

The Harness Subagents format is developed in the open and is open to contributions from the broader ecosystem — see [`CONTRIBUTING.md`](CONTRIBUTING.md) for how to get involved. The project is maintained by [Italo Israel Baeza Cabrera (@darkghosthunter)](https://github.com/darkghosthunter) and is not affiliated with, endorsed by or supported by Anthropic or any other company.

## Acknowledgements

This project is based on the original [Agent Skills](https://agentskills.io) standard. It reuses that standard's structure, format conventions and documentation approach, adapted for subagents.

## Getting started

- **[Specification](docs/specification.mdx)** — Format details
- **[Quickstart](docs/subagent-creation/quickstart.mdx)** — Create your first subagent
- **[Best practices](docs/subagent-creation/best-practices.mdx)** — Write subagents that delegate and return well

## License

Code in this repository is licensed under [Apache 2.0](LICENSE). Documentation is licensed under [CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/). See individual directories for details.
