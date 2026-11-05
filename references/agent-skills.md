# Agent Skills (agentskills.io) — tier A
Sources: /specification, /client-implementation/adding-skills-support, /skill-creation/{best-practices,optimizing-descriptions,evaluating-skills}

- `name`: 1-64 chars, lowercase alphanumeric + hyphens, no leading/trailing/consecutive hyphens, **must match parent directory**. `description`: 1-1024 chars. Harness-Subagents' `name`/`description` rules are copied from here (directory → filename).
- `metadata`: string→string map; "making your key names reasonably unique" recommended. Matches subagent spec wording.
- Progressive disclosure: metadata loaded at startup; "Keep your main SKILL.md under 500 lines" (also ~5000 tokens). **Skills rule only**; nothing equivalent stated for subagents.
- Client guide: scan `<project>/.agents/skills/` and `~/.agents/skills/` as a "widely-adopted convention"; the spec itself does not mandate locations. Project scope overrides user; same-scope collision: first or last found, be consistent; log a warning on collision.
- Trust: project-level skills may be untrusted; gate loading on a trust check.
- Lenient validation: warn but load on name/dir mismatch; skip when description missing/empty or YAML unparseable.
- Catalog read at discovery; body may be read at discovery or at activation (activation picks up edits).
- Descriptions guide: imperative phrasing ("Use this skill when..."); focus on user intent, not implementation; concise, hard 1024 limit; agents consult skills mainly for tasks beyond what they do alone (one-step requests may not trigger).
- Trigger testing: ~20 queries, 8-10 positive / 8-10 negative; near-miss negatives; 3 runs per query; pass threshold 0.5 default; 60/40 train/validation split; "Five iterations is usually enough."; re-check 1024 limit after edits. Example detection script reads agent JSON for a Skill tool call.
- Eval guide: start with 2-3 cases; run with/without (or previous version) baseline; clean context per run; `timing.json` holds `total_tokens`, `duration_ms`; "Require concrete evidence for a PASS"; review assertions that always pass; iterate on failures, human feedback, traces.
- Best practices: pick a default, not a menu; explaining *why* can beat rigid directives for flexible tasks; read execution traces; extract skills from real tasks.
