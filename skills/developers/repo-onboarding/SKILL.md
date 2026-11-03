---
name: repo-onboarding
description: Maps an unfamiliar codebase in minutes - how to run it, where things live, how data flows - and writes a short AGENTS.md so every future session starts with that knowledge.
version: 1.0.0
metadata:
  hermes:
    tags: [developers, codebase, onboarding]
    category: developers
    requires_toolsets: [terminal]
---

# Repo Onboarding

## When to Use
- "Explain this repo", "I just cloned this", "where do I start?".
- Any time you work in a repo that has no AGENTS.md.

## Procedure
1. Read the README, the package manifest (package.json, pyproject.toml, Cargo.toml, go.mod) and any CI config. CI shows the real build and test commands.
2. List the top two levels of folders. Name the entry points (main, server, app router, CLI).
3. Run the install and test commands in a safe way. Don't run scripts that deploy, migrate a database or need secrets. Note what passed and failed.
4. Trace one real request or user action end to end through the code and write it down as 4-6 steps with file paths.
5. Write `AGENTS.md` at the repo root (ask before overwriting an existing one) with:
   - Commands: install, dev, test, lint, build.
   - Layout: one line per important folder.
   - Conventions you saw (naming, state management, error handling).
   - Gotchas: env vars needed, ports, slow tests.
6. Give the user a 10-line summary and the list of things you could not run.

## Pitfalls
- Don't read `.env` files or print secrets. Note only the variable names that are required.
- Don't guess commands. If a command isn't in the repo, say so.

## Verification
- The commands in AGENTS.md were actually run, or marked "not run".
- File paths in the flow trace exist.
