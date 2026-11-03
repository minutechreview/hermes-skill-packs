---
name: customer-replies
description: Drafts friendly, accurate replies to customer messages (WhatsApp, Instagram, email) using the business's saved prices, hours and policies, and flags anything that needs the owner.
version: 1.0.0
metadata:
  hermes:
    tags: [business, customers, support]
    category: business
---

# Customer Replies

## When to Use
- "Reply to this customer", a pasted customer message, "how do I answer this?".

## Procedure
1. Load the business facts: check memory and a `BUSINESS.md` file in the working folder (prices, hours, location, delivery, refund policy, tone). If they're missing, ask for them once and offer to save them to `BUSINESS.md`.
2. Work out what the customer actually wants: a price, availability, a complaint, a booking, a refund.
3. Draft the reply:
   - Answer the question in the first line.
   - Use the customer's language (reply in Sinhala, Tamil, Arabic, etc. if they wrote in it).
   - Short. 2-4 lines for chat, a little longer for email.
   - End with one clear next step ("Shall I book you for 4pm?").
4. Flag for the owner instead of answering when it involves: refunds over the policy, legal threats, medical or safety issues, discounts not in BUSINESS.md, or an angry repeat customer.
5. Show the draft. Do not send it unless the user has set that up and says so.

## Pitfalls
- Never invent a price, stock level or delivery date. If it isn't in BUSINESS.md, say "Let me check and get back to you".
- Don't promise refunds or discounts on the owner's behalf.

## Verification
- Every fact in the reply is in BUSINESS.md or memory.
- The reply answers the question in the first line.
