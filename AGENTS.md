# Agent Instructions

## Project perspective

Harness Subagents is a small, portable, harness-neutral format for defining
subagents. Keep the format small: new requirements impose costs on every
implementation and should address demonstrated interoperability needs, not
hypothetical completeness.

A subagent is a single Markdown file: frontmatter metadata plus a body that a
harness gives the subagent as its system prompt. The body is loaded in full at
spawn; there are no bundled references by design. Conditional knowledge belongs
in skills, which subagents can use where the harness supports them.

Use progressive disclosure in this repository too. Keep details in their natural
source instead of repeating commands, configuration, or policy here.

## Authority and boundaries

`docs/specification.mdx` is authoritative for format requirements.
Explanatory documentation, examples, and guides do not add requirements to the
format. Preserve the distinction between the format and choices made by
subagent authors, harnesses, parents, or models.

When these surfaces disagree, surface the discrepancy and resolve it at the
appropriate authority rather than treating existing implementation behavior as
normative.

The `complexity` field is a suggestion for harnesses to adapt, not a hard
requirement. Do not add fields that pin model identifiers or other
harness-specific behavior to the portable format.

## Documentation

The documentation under `docs/` is a Mintlify site. Treat rendered behavior and
published routes—not source text alone—as part of documentation correctness.

## Contributions

`CONTRIBUTING.md` owns current contribution scope, routing, and AI-assistance
disclosure policy. Read and follow it before beginning work intended for
upstream submission or participating in an issue, Discussion, or pull request.
