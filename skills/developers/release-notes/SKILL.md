---
name: release-notes
description: Writes human release notes and a changelog entry from git history and merged PRs, grouped by what users will notice, plus a short social post for the launch.
version: 1.0.0
metadata:
  hermes:
    tags: [developers, changelog, release]
    category: developers
    requires_toolsets: [terminal]
---

# Release Notes

## When to Use
- "Write the changelog", "release notes for v1.4", "what changed since last release?".

## Procedure
1. Find the range: last tag to HEAD (`git describe --tags --abbrev=0`, then `git log <tag>..HEAD --oneline`). Ask if there are no tags.
2. If the repo is on GitHub and the `gh` CLI is logged in, also read merged PR titles and bodies for that range.
3. Group changes:
   - **New** (features users can try)
   - **Improved**
   - **Fixed**
   - **Breaking** (put first if any, with what users must change)
   - Skip internal chores unless they matter to users.
4. Write each line as what the user gets, not what the code did: "Exports are 3x faster" beats "refactor export worker".
5. Credit contributors by their GitHub handle.
6. Add a 2-3 line launch post for X/LinkedIn.
7. Show the draft. Only write to CHANGELOG.md or create a GitHub release when the user says so.

## Pitfalls
- Don't claim numbers ("3x faster") unless a commit, PR or benchmark says so.
- Don't publish a release yourself without a clear yes.

## Verification
- Every line maps to at least one commit or PR in the range.
- Breaking changes are listed first with migration steps.
