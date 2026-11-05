# Effort / reasoning parameters — tier A
Claude (platform.claude.com/docs/en/build-with-claude/effort): levels `low`, `medium`, `high`, `xhigh`, `max`. "Most Claude models default to high"; Opus 5.5 and Haiku 5.5 default to medium. Not every model supports every level. Effort is a behavioral signal, not a token budget.
OpenAI (platform.openai.com/docs/guides/reasoning): `reasoning.effort` values are model-dependent: none, minimal, low, medium, high, xhigh, max. "Defaults are also model-dependent rather than universal." gpt-5.5 and GPT-5.6 default to medium; some models reject `none`/`minimal`. `max` sits above `xhigh`.
Claude Code subagent `effort` frontmatter exists (see claude-code.md).
