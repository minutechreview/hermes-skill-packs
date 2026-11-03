---
name: project-memory
description: Keeps a running memory of the projects you're building - decisions, current status, next steps and gotchas - so you never re-explain a project at the start of a session.
version: 1.0.0
metadata:
  hermes:
    tags: [developers, memory, projects]
    category: developers
---

# Project Memory

## When to Use
- At the end of a work session: "save where we are", "remember this".
- At the start: "where were we on X?", "what's left on X?".
- When a decision is made that someone would otherwise forget.

## Procedure
**Saving**
1. Write one short memory entry per project with the memory tool:
   `PROJECT <name> | path <folder> | status <one line> | next <one line> | updated <date>`
2. Decisions and gotchas go in the project's own `AGENTS.md` or a `DECISIONS.md`, not in memory. Memory is small; files are not.
   - Decision format: date, what was decided, why, what was rejected.
3. Update the existing entry instead of adding a new one. Delete entries for finished or abandoned projects.

**Recalling**
1. Read the memory entry, then the project's AGENTS.md / DECISIONS.md.
2. Search past sessions for the project name if something is missing.
3. Answer with: status, next step, open questions. Then ask if the next step is still right.

## Pitfalls
- Memory is a frozen snapshot per session: a save shows up in the system prompt next session, not this one.
- Never save secrets, tokens or passwords to memory or to these files.
- Keep entries one line. Long entries fill memory and push out other facts.

## Verification
- One entry per active project, each with a date.
- Every decision has a "why".
