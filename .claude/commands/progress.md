---
description: Render or update the course progress dashboard
argument-hint: "[check <module>.<item>] | [uncheck <module>.<item>] | [note <module> <text>]"
---

Manage `workspace/progress.md`.

## With no arguments

Read `workspace/progress.md` and render it as-is. Highlight:
- the current module
- count of checked vs. total items per module
- any blocker notes

## With `check <module>.<item>` argument

Mark the named item complete in `workspace/progress.md`. Update `last_updated` frontmatter to today. Echo the updated row.

Example: `/progress check module-1.business-name` toggles the `business-name` line under Module 1 to `[x]` and stamps the date.

## With `uncheck <module>.<item>` argument

Reverse of check. Toggle to `[ ]`. Update `last_updated`.

## With `note <module> <text>` argument

Append a dated bullet to the "Notes" section for that module in `workspace/progress.md`.

## Convention

- Each module section has the same shape: a checklist of deliverables, a Notes subsection, and a "Blockers" subsection.
- Never delete history. To revise a note, append a new dated note that supersedes the old one.
- If the file doesn't exist, refuse to create it via this command — direct Rylee to `/session-start` which has the bootstrap path.
