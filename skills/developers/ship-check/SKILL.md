---
name: ship-check
description: A pre-push safety check - tests, lint, build, leaked secrets, debug leftovers and risky diffs - so nothing embarrassing reaches main or production.
version: 1.0.0
metadata:
  hermes:
    tags: [developers, review, security]
    category: developers
    requires_toolsets: [terminal]
---

# Ship Check

## When to Use
- "Is this ready to push?", "check before I deploy", before opening a PR.

## Procedure
1. `git status` and `git diff --staged` (or against the base branch). Summarise the change in 2 lines.
2. **Secrets**: scan the diff for keys, tokens, passwords, private URLs and `.env` files. Any hit is a hard stop.
3. **Leftovers**: debug prints, `console.log`, commented-out blocks, TODOs added in this diff, `.only` in tests.
4. **Run** the project's test, lint, typecheck and build commands (from AGENTS.md or the manifest). Record pass/fail.
5. **Risk**: flag database migrations, auth or payment code, deleted files, dependency changes and anything touching config.
6. Report in this shape:

```
READY / NOT READY
Blocking: ...
Worth a look: ...
Ran: tests ✓ lint ✓ build ✗ (error ...)
```

7. Don't push, merge or deploy. That stays the user's call.

## Pitfalls
- Never print a found secret in full. Show the file and line and the first 4 characters only.
- "Tests pass" means you ran them in this session, not that they passed last week.

## Verification
- Every command in "Ran" was executed now.
- No secrets in the diff.
