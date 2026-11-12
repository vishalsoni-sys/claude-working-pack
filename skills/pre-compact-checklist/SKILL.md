---
name: pre-compact-checklist
description: Before compacting a long session, handing over to a new session, or writing a "where are we" summary, build it from a mechanical checklist instead of memory. Use when the user says compact, handover, "summarize where we are", "did we miss anything", or when context is running low.
---

# Pre-compact checklist

In long sessions, details from the middle of the conversation get less attention than the start and the most
recent work. A summary written from memory silently drops them. Build it from commands and lists instead.

## Steps (run commands; do not recall)

1. **Repositories:** `git status` and unpushed commits (`git log @{u}..HEAD`) for every repo or worktree touched.
   List uncommitted files, and mark the ones you did NOT create ("not mine — never stage").
2. **Documents:** for every document written or overwritten this session, diff it against its previous version.
   Is anything that is still referenced now gone?
3. **Decisions:** what was decided (by whom, when), and what is still waiting on the user.
4. **Tasks:** done, in progress, not started. Give the next concrete step for each.
5. **Side findings** noticed but not acted on.
6. **Stale claims:** committed docs or notes that a later change made wrong.
7. **Paths:** the absolute path of every temporary or scratch file referenced.
8. **Environment:** what is needed to resume (tool locations, logins that expired, long-running jobs).
9. **Lessons:** save durable lessons and user corrections to memory or project rules **before** compacting.

## Output
A paste-ready block grouped as SETUP / DONE / UNCOMMITTED / NEXT / PENDING / DECISIONS / SIDE FINDINGS /
WORKING STYLE. Then ask the user one question: "Anything I missed?"
