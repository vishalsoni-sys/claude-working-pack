---
name: independent-review
description: Get an unanchored second opinion on a design, plan or risky change from another model (or a fresh agent), verify what it says, and cross-judge before acting. Use before committing to a design, before merging security, payment, auth or data-migration code, or when the user says "get it reviewed", "second opinion", "check with <model>".
---

# Independent review

Goal: a review that can disagree with you. Most review value is lost to anchoring (the reviewer only checks
what you showed it) and to scope creep (the reviewer turns every finding into new work).

## Steps

1. **Write your own view first** to a file (design, recommendation, open questions). Do this before reading any
   reviewer output, so you cannot drift toward theirs.
2. **Write two briefs** and save both to files:
   - **Open brief:** the problem, the constraints, the decisions already made by the user, and pointers to the
     relevant files. Do NOT include your draft. Ask for the reviewer's own recommendation.
   - **Critique brief:** your draft, verbatim. Ask it to find what is wrong, checking every factual claim
     against the code or data.
3. **Put these rules in every brief:**
   - Read-only: no edits, builds or network calls.
   - Separate MUST-FIX (unsafe or will not work) from NICE-TO-HAVE.
   - Do not expand scope. If existing code already handles something, say so with `file:line`.
   - Cite `file:line` for code facts and mark anything inferred as INFERRED.
   - Respect decisions the user has already made: state their cost, do not re-argue them.
   - First line is a verdict (APPROVE / APPROVE WITH MUST-FIXES / REJECT). Add a word limit.
4. **Run both briefs in parallel** in the background. Prefer a different model family for at least one of them.
5. **Verify before you relay.** Re-check the reviewer's key claims yourself against the code or logs. A
   reviewer's confident claim is a hypothesis, not a fact.
6. **Cross-judge.** For each finding: verified? accept / partly / reject, and why. If the two runs disagree on
   something important, send the disagreement back to one of them.
7. **Report to the user in a few lines:** verdict, what changes, effort. Keep the full reports in files and give
   their paths.

## Anti-patterns
- A closed yes/no brief ("confirm X is fine") — it anchors the reviewer and hides better options.
- Relaying findings you did not verify, or cheerleading the reviewer.
- Letting a reviewer's nice-to-haves become the plan.
- A single reviewer for the highest-stakes code.
