---
name: first-principles-gate
description: Before presenting or accepting a design, plan or estimate, strip it to the minimum that meets the goal and check how proven systems already solve the same problem. Use when a design is about to be proposed, when an estimate grows, or when the user asks "why so long", "is this over-complicated", "think from first principles", "what is the minimum".
---

# First-principles gate

AI agents are good at completeness and weak at restraint. Each review round tends to add machinery. Run this gate
before a design reaches the user, and again whenever the estimate grows.

## Steps

1. **Goal in one sentence**, stated as what the user will see or be able to do.
2. **The only new thing.** What must change for that outcome? Everything else stays as it is. Prefer producing
   today's artifact (record, format, API) through a new path over building a parallel system that the rest of the
   code then has to learn about.
3. **Prior art.** Name two or three proven systems that solved the same problem, and what they do. Prefer the
   proven pattern over a clever new one, especially for security, payments and data integrity.
4. **Line-by-line cut.** For every element of the draft: is it needed for the goal? If not, remove it and say why.
5. **Beside, behind a switch.** Prefer adding the new path next to the old one with a kill switch over replacing
   working code.
6. **Friction check.** Any mitigation that adds user steps (refresh this, re-scan that, confirm again)? Flag it and
   find a design that does not need it.
7. **Estimate split:** coding / tests / review and fixes / device or staging verification / total. The code is often
   a third of it; show that, so the user can push back on the right part.

## Output (few words)
- One recommendation.
- What was removed and why (one line each).
- Remaining risks, each with its mitigation.
- The estimate split.
- What the user must decide, as a question.
