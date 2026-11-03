---
name: quote-builder
description: Turns a customer request into a clean, itemised quote or invoice using the business's saved price list, with totals checked twice and a polite follow-up message.
version: 1.0.0
metadata:
  hermes:
    tags: [business, quotes, invoices]
    category: business
---

# Quote Builder

## When to Use
- "Make a quote for this customer", "invoice for the Perera order", "how much should I charge for…".

## Procedure
1. Load the price list from `BUSINESS.md` or a sheet the user names. If an item isn't listed, ask for the price; never guess.
2. Write the quote:
   - Business name and contact, customer name, date, quote number (ask for the numbering style once and save it).
   - Line items: description, quantity, unit price, line total.
   - Subtotal, discount (only if the owner set it), tax if the business charges it, total.
   - Validity ("valid for 14 days") and payment terms.
3. Calculate totals with a script or calculator tool, not in your head, then check them a second time.
4. Output as a PDF or Word file if the bundled `pdf` or `microsoft-office` skill is available; otherwise clean Markdown.
5. Draft a short message to send with it, plus a follow-up for 3 days later if there's no reply.

## Pitfalls
- Wrong totals destroy trust. Always recompute.
- Don't add tax unless the owner confirms they're registered to charge it.
- Don't put bank details in the file unless the owner gives them for this purpose.

## Verification
- Line totals × quantities and the grand total match on a second calculation.
- Every price came from the price list or the owner.
