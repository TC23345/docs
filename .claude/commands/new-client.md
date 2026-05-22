---
description: Instantiate a new client folder from intake-process assets
argument-hint: "<LastName-FirstName>"
---

Create a new client folder under `workspace/clients/` using the canonical PII-reduced naming convention.

## Argument parsing

Argument is `LastName-FirstName` (hyphen-separated). Parse into:

- `client_id` = `<lastname_lower>-<firstinitial_lower>-<YYYYMM>` (today's year-month)
- `client_display_name` = `<FirstName> <LastInitial>.` (e.g., "Jamie D.") for use inside frontmatter values only — never in file paths or commit messages

Example: `/new-client Doe-Jamie` on 2026-05-22 →
- `client_id` = `doe-j-202605`
- `client_display_name` = `Jamie D.`

If the argument is missing or malformed, ask Rylee for it in `LastName-FirstName` form. Do not guess.

## Procedure

1. **Refuse and report** if `workspace/clients/<client_id>/` already exists. Do not overwrite.

2. Create directory tree:
   - `workspace/clients/<client_id>/`
   - `workspace/clients/<client_id>/observations/`

3. Copy each file from `.claude/skills/intake-process/assets/` into the new client folder, substituting `{client_id}`, `{client_display_name}`, and `{today}` placeholders in frontmatter and headings:
   - `intake-form.md` → `intake.md`
   - `welcome-packet.md` → `welcome-packet.md`
   - `iep-checklist.md` → `iep-checklist.md`
   - `session-log.md` → `session-log.md`

4. Do **not** copy `services-agreement-checklist.md` into the client folder — that one stays at the practice level, not per-client. The attorney drafts the contract once; clients sign the same one.

5. Ask Rylee for the three values worth capturing at instantiation (do not block on more than these):
   - Referral source
   - Presenting concern (≤ 5 words, for the next-step framing)
   - State of IEP (current, expired, none)

6. Populate those into `intake.md` and `session-log.md`'s first dated entry (intake date).

7. Report back:
   - Path created
   - First-session next step ("schedule screening call" or "send intake form" depending on workflow stage)
   - Reminder: never paste full client names in commit messages

## Hard rules

- Never write full last name + full first name to any committed file body or commit message.
- Never write the school district name without abbreviation to any committed file body.
- If Rylee says "actually her name is X Y," reject the full-name spelling in commits — first initial only.
