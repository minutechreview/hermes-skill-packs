---
name: bug-triage
description: Turns a vague bug report or error into a reproduced, root-caused issue with a minimal fix and a test that would have caught it.
version: 1.0.0
metadata:
  hermes:
    tags: [developers, debugging]
    category: developers
    requires_toolsets: [terminal]
---

# Bug Triage

## When to Use
- "This is broken", a pasted stack trace, a failing CI run, a user complaint.

## Procedure
1. **Restate** the bug in one line: expected vs actual, and where.
2. **Reproduce** it. Write the exact command, input or click path. If you can't reproduce it, stop and ask for the missing detail instead of guessing.
3. **Narrow** it down: read the stack trace from the bottom of your own code up, check recent commits (`git log -p` on the suspect files), and bisect if it used to work.
4. **Root cause**: state it in one sentence that names the file and line. "It's a race condition" is not a root cause until you can point at it.
5. **Test first**: add a test that fails because of the bug.
6. **Fix**: the smallest change that makes the test pass. Don't refactor in the same change.
7. Run the full test suite. Report: root cause, fix, test, anything else that looked wrong but you left alone.

For a deeper method, the bundled `systematic-debugging` skill goes further.

## Pitfalls
- Don't "fix" by catching and hiding the error.
- Don't change several things at once; you won't know which one worked.

## Verification
- The new test failed before the fix and passes after.
- The whole suite passes.
