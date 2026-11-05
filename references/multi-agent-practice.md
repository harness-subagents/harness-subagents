# Multi-agent practice — tier B/C
Anthropic, "How we built our multi-agent research system":
- Each subagent needs "an objective, an output format, guidance on the tools and sources to use, and clear task boundaries"; vague briefs cause duplicated work and gaps. (Spec's Lifecycle/Delegation wording matches.)
- Agents use ~4x chat tokens; multi-agent ~15x. Worth it only for high-value tasks. Scale effort to complexity via explicit rules.
- Subagents write outputs to external storage and pass lightweight references back, reducing "game of telephone" loss. (Supports "point, don't paste".)
- Lead agent cannot steer subagents; synchronous execution is a bottleneck.
- Prefer heuristics over rigid rules in prompts.
Cognition, "Don't Build Multi-Agents" (C): subagents acting on conflicting implicit assumptions produce inconsistent results; share context, actions carry implicit decisions; prefer single-threaded agents by default. (Supports "keep decisions in the parent".)
