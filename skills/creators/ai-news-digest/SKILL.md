---
name: ai-news-digest
description: Daily AI and tech news digest for creators. Finds what actually happened in the last 24-48 hours, checks it against primary sources, and ranks each story by how well it would work as a short video.
version: 1.0.0
metadata:
  hermes:
    tags: [creators, news, research]
    category: creators
---

# AI News Digest

## When to Use
- "What happened in AI today?", "any news worth a video?", "morning digest".
- On a schedule. Say "every morning at 8, run my AI news digest and send it to Telegram" and Hermes's built-in scheduler handles it.

## Procedure
1. Search the last 24-48 hours for AI, dev tools, open-source releases and big tech product news. Use several queries; one query misses things.
2. For every candidate story, open the primary source: the company blog, the GitHub repo, the paper or the official post. Do not report a story you only saw in a repost.
3. Drop anything you can't confirm. Drop rumours unless the user asked for them, and label them "rumour" if kept.
4. Score each story 1-5 on:
   - **Visual**: can it be shown on screen (a demo, a UI, a number)?
   - **Normal-person value**: would someone who isn't technical care?
   - **Freshness**: is it less than a day old, and is anyone else covering it yet?
5. Return the top 5, best first, in this shape:

```
1. <headline in plain English>  (score 4.3)
   What: one sentence.
   Why people care: one sentence.
   Hook idea: "<a first line for a reel>"
   Source: <url>
```

6. Ask: "Want a script for any of these?" If yes, hand off to the `reel-script` skill.

## Pitfalls
- Dates: check the publish date on the page. Old stories resurface constantly.
- Numbers: copy them exactly from the source (stars, users, prices). Never round up to make a hook stronger.
- Don't invent quotes from real people. Paraphrase and link.

## Verification
- Every item has a working source link that you actually opened.
- No item is older than the window the user asked for.
