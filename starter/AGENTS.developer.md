# AGENTS.md: project instructions

<!-- Put this at the root of a repo, renamed to AGENTS.md. The `repo-onboarding` skill can fill it in for you. -->

## Commands
- Install: `<npm install>`
- Dev: `<npm run dev>` (port <3000>)
- Test: `<npm test>`
- Lint / typecheck: `<npm run lint>` / `<npm run typecheck>`
- Build: `<npm run build>`

## Layout
- `src/` - <app code>
- `tests/` - <tests>

## Conventions
- <naming, state management, error handling>

## Rules
- Run `ship-check` before every push.
- Bugs: `bug-triage` (reproduce → failing test → smallest fix).
- Never commit `.env` files or secrets. Never push to main or deploy without asking.
- Record decisions in `DECISIONS.md` (`project-memory` skill).
