# Hermes Skill Packs

Free skill packs and a setup guide for [Hermes Agent](https://github.com/NousResearch/hermes-agent), the open-source agent from Nous Research. There are three packs: one for **creators**, one for **developers** and one for **small business owners**.

Each skill is a plain `SKILL.md` file in the [agentskills.io](https://agentskills.io) format, so you can read every line before you install it.

---

## Set up Hermes in 4 steps

### 1. Install
Use the desktop app from [hermes-agent.nousresearch.com](https://hermes-agent.nousresearch.com/), or install from the terminal:

```bash
# macOS / Linux / WSL2
curl -fsSL https://hermes-agent.nousresearch.com/install.sh | bash
```

```powershell
# Windows (PowerShell)
iex (irm https://hermes-agent.nousresearch.com/install.ps1)
```

Then reload your shell (`source ~/.zshrc` or `source ~/.bashrc`) and run `hermes`.

### 2. Connect a model
```bash
hermes model    # pick a provider and model
```
You can sign in with a supported subscription or paste an API key from a provider (OpenRouter, OpenAI, Anthropic, Nous Portal, a local model and more). `hermes setup` runs the full wizard if you'd rather do everything at once.

### 3. Give it instructions
- **`~/.hermes/SOUL.md`** is who the agent is: personality, tone, what to avoid. Start from [`starter/SOUL.md`](starter/SOUL.md).
- **`AGENTS.md`** in your working folder is how it works on that project: commands, rules, workflow. Starters: [creator](starter/AGENTS.creator.md), [developer](starter/AGENTS.developer.md). Business owners: fill in [`starter/BUSINESS.md`](starter/BUSINESS.md) instead.

### 4. Memory
Hermes saves important facts to its own memory files (`USER.md` about you, `MEMORY.md` for what it learned) and can search your past conversations. Tell it "remember this" and it's there next session.

> Memory is loaded when a session starts, so something saved mid-chat shows up from the next session on.

### Coming from another agent?
Hermes can import your persona, memories and skills from OpenClaw, Claude Code, Codex CLI or Cursor. `hermes setup` offers this automatically, or run it any time:

```bash
hermes plugins install agent-importers
hermes import-agent openclaw --dry-run    # preview first
hermes import-agent openclaw              # then import
```
(`hermes claw migrate` still works as the older spelling for OpenClaw.)

---

## Install the skill packs

**Option A: one skill at a time**
```bash
hermes skills install minutechreview/hermes-skill-packs/skills/creators/reel-script
```

**Option B: a whole pack.** Clone the repo and point Hermes at it:
```bash
git clone https://github.com/minutechreview/hermes-skill-packs ~/hermes-skill-packs
```
Then add this to `~/.hermes/config.yaml`:
```yaml
skills:
  external_dirs:
    - ~/hermes-skill-packs/skills/creators     # pick the packs you want
    - ~/hermes-skill-packs/skills/developers
    - ~/hermes-skill-packs/skills/business
```

Use a skill by name (`/reel-script write a script about …`) or just ask in plain words. Hermes loads the matching skill by itself.

---

## 🎬 Creators

| Skill | What it does |
| --- | --- |
| [`ai-news-digest`](skills/creators/ai-news-digest/SKILL.md) | Today's AI and tech news, checked against the original source and ranked by how well each story works as a video |
| [`content-ideas`](skills/creators/content-ideas/SKILL.md) | 10 ideas in mixed formats, with hooks, and an idea bank saved to memory so it never repeats |
| [`reel-script`](skills/creators/reel-script/SKILL.md) | A 30-60 s script in your voice: hook, beats, the catch, comment-keyword CTA |
| [`caption-writer`](skills/creators/caption-writer/SKILL.md) | Captions for IG, TikTok, X and LinkedIn from one script |
| [`repurpose-post`](skills/creators/repurpose-post/SKILL.md) | One video or podcast turned into a week of posts |

Built-in Hermes skills worth turning on: `youtube-content`, `humanizer`, `xurl`, `manim-video`.

## 💻 Developers

| Skill | What it does |
| --- | --- |
| [`repo-onboarding`](skills/developers/repo-onboarding/SKILL.md) | Maps a new codebase and writes its AGENTS.md |
| [`project-memory`](skills/developers/project-memory/SKILL.md) | Remembers status, decisions and next steps for every project you're building |
| [`bug-triage`](skills/developers/bug-triage/SKILL.md) | Reproduce, find the root cause, write a failing test, make the smallest fix |
| [`release-notes`](skills/developers/release-notes/SKILL.md) | Changelog and release notes from git history, plus a launch post |
| [`ship-check`](skills/developers/ship-check/SKILL.md) | A pre-push check for tests, lint, build, leaked secrets and risky changes |

Built-in Hermes skills worth turning on: `github`, `systematic-debugging`, `test-driven-development`, `requesting-code-review`, `claude-code`, `codex`.

## 🏪 Small business

| Skill | What it does |
| --- | --- |
| [`customer-replies`](skills/business/customer-replies/SKILL.md) | Customer message replies drafted from your real prices and policies, in the customer's language |
| [`daily-brief`](skills/business/daily-brief/SKILL.md) | A morning brief on your phone: bookings, messages waiting, money, and 3 things to do |
| [`review-responder`](skills/business/review-responder/SKILL.md) | Replies to Google and Facebook reviews, plus the patterns across them |
| [`social-calendar`](skills/business/social-calendar/SKILL.md) | A month of posts around your products and local holidays |
| [`quote-builder`](skills/business/quote-builder/SKILL.md) | Itemised quotes and invoices from your price list, with totals checked twice |

Built-in Hermes skills worth turning on: `email-inbox-triage`, `google-workspace`, `pdf`, `microsoft-office`, `weekly-review-planning`, `competitor-news-monitor`.

---

## More free stuff from me
- [Claude video effects](https://github.com/minutechreview/claude-video-effects): film one clip and have an agent edit it.
- [Motion Index](https://motion-index-library.vercel.app): a visual library of motion-graphics styles with copy-ready prompts.

## Safety
- Read a skill before you install it. These are plain text; nothing runs on install.
- These skills tell the agent to show drafts before anything is sent, posted, paid or deleted. Keep it that way.
- Never put passwords, bank logins or card numbers in SOUL.md, AGENTS.md, BUSINESS.md or memory.

Hermes Agent is made by Nous Research. This repo is an independent community pack and isn't affiliated with them.

MIT licensed. PRs with new skills are welcome.
