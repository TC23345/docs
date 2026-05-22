---
description: Grep workspace/ for a string and return matching files with one-line context
argument-hint: "<query>"
---

Search `workspace/` recursively for the argument string. Use ripgrep if available, fall back to `grep -rn`.

## Behavior

1. Run case-insensitive search across `workspace/**`.
2. Return matches as:

   ```
   <relative path>:<line> — <one line of context>
   ```

3. Group by file. Show at most 3 hits per file; if more, note "+N more in this file."
4. If a match is inside frontmatter (between the leading `---` blocks), label it `[frontmatter]` so Rylee knows.
5. If zero matches, say so plainly. Do **not** suggest fuzzy variants automatically — Rylee will refine.

## Argument

The full argument string is the query. Pass it through unchanged; do not strip quotes or normalize whitespace.

## Out of scope

- Do not search `.claude/` (skills are not the practice ledger)
- Do not search `course/` (those are read-only reference pages)
- Do not open files for full reads unless Rylee asks
