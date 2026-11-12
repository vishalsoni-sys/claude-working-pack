# Working-with-Claude pack

Three small skills from months of building a real product with an AI coding agent. Companion to the article "12 rules I now follow when building with an AI coding agent".

| File | What it does | When it switches on |
|---|---|---|
| `skills/independent-review/SKILL.md` | Unanchored second opinion from another model: an open brief plus a critique brief, must-fix vs nice-to-have, verify and cross-judge | Before a design, a risky merge, or "get it reviewed" |
| `skills/first-principles-gate/SKILL.md` | Strips a design to the minimum, checks prior art, splits the estimate | Before presenting a design, or when an estimate grows |
| `skills/pre-compact-checklist/SKILL.md` | Builds a compact or handover summary from commands, not memory | Before /compact, a handover, or "where are we" |

## Install (Claude Code)
- Personal, all projects: copy each skill folder to `~/.claude/skills/<skill-name>/SKILL.md`.
- One project: copy to `<repo>/.claude/skills/<skill-name>/SKILL.md`.

## Why it's split this way
Skills load only when their situation comes up, so keep each one narrow. Preferences you want in every reply
(short answers, "decisions are mine", evidence) belong in CLAUDE.md, which is always read. A single big "work
better" skill would be overkill and would rarely trigger at the right moment.

The ideas are not Claude-specific: the briefs, the gate and the checklist work with any capable coding agent.
