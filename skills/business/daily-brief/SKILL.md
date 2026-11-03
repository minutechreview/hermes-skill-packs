---
name: daily-brief
description: A morning brief for a small business owner - today's bookings and deadlines, unanswered messages, money in and out, and the 3 things worth doing today - sent to Telegram or WhatsApp.
version: 1.0.0
metadata:
  hermes:
    tags: [business, planning, schedule]
    category: business
---

# Daily Brief

## When to Use
- "What's on today?", "morning brief", or on a schedule. Hermes has a built-in scheduler: just say "every day at 7:30am, send me my daily brief on Telegram".

## Procedure
1. Gather what is connected. Skip any source that isn't set up and say which ones were skipped:
   - Calendar (bookings, meetings, deliveries) - the bundled `google-workspace` skill covers Google Calendar.
   - Email or inbox - the bundled `email-inbox-triage` skill.
   - A sales or orders sheet the user points you to.
   - Open tasks and follow-ups saved in memory.
2. Build the brief, short enough to read on a phone:

```
Good morning ☀️  <date>
Today: 3 bookings (10:00 Nimal, 13:30 Sara, 16:00 delivery)
Waiting on you: 2 customer messages, 1 supplier invoice
Money: yesterday Rs 48,500 in · Rs 12,000 out
Do today:
1. ...
2. ...
3. ...
```

3. Pick the 3 "do today" items by: money at stake, a customer waiting, a deadline today.
4. Save new follow-ups to memory so tomorrow's brief can check them.

## Pitfalls
- Don't show full card numbers, bank details or customer phone numbers in the brief.
- If a source fails, say so. Don't fill gaps with guesses.

## Verification
- Every number traces to a source you read this run.
- The brief fits on one phone screen.
