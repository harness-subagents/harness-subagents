# Claude Code subagents — tier A
Sources: code.claude.com/docs/en/sub-agents.md, headless.md, cli-reference.md

- Files: Markdown + YAML frontmatter in `.claude/agents/` (project, walked up to repo root) and `~/.claude/agents/` (user); scanned recursively. Only `name` and `description` required.
- `name`: up to 256 chars, cannot contain `:`; "The filename doesn't have to match." Duplicate names in one tree: one loaded by filesystem order, no documented precedence.
- `tools`: comma-separated string or YAML list; "Inherits every tool available to subagents if omitted." If no entry resolves to a tool the subagent usually fails to launch (empty ≠ documented as inherit). `disallowedTools` also exists.
- Always removed from subagents even if listed: `AskUserQuestion`, `EnterPlanMode`, `ScheduleWakeup`, others. Background subagents get a reduced built-in tool set.
- Nesting: default "up to three layers below the main conversation"; `CLAUDE_CODE_MAX_SUBAGENT_SPAWN_DEPTH` changes it. Listing `Agent` in `tools` lets a subagent spawn.
- Task tool renamed to Agent in v2.1.63 (`Task(...)` still aliased).
- Subagents "receive only this system prompt plus basic environment details like the working directory", not the parent conversation.
- Subagents can be resumed / sent follow-ups; `isolation: worktree` exists.
- Frontmatter also has `model`, `effort` (low/medium/high/xhigh/max), `permissionMode`, `maxTurns`, `skills`, `mcpServers`, `hooks`.
- Descriptions cost context; warning when combined descriptions exceed 15,000 tokens. No documented subagent body-length guidance.
- `/agents` command exists; docs say it prints a reminder to edit files; a new `agents` directory created mid-session needs a restart.
- Headless: `--output-format json` = "structured JSON with result, session ID, and metadata" (single result payload; no tool-call trace). Tool calls need `--output-format stream-json --verbose`. `--forward-subagent-text` surfaces subagent transcripts.
