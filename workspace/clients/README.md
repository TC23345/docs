---
client_id: none
created: 2026-05-22
last_updated: 2026-05-22
module_context: cross-cutting
---

# Client folder conventions

One folder per client. Created by `/new-client <LastName-FirstName>`.

## Naming

`<lastname>-<firstinitial>-<YYYYMM>/`

Examples:
- `doe-j-202605/` — Jamie Doe, intake May 2026
- `garcia-r-202609/` — Robin Garcia, intake September 2026

The year-month suffix disambiguates if two clients share a last name + first initial. It also makes the folder sortable by intake order.

## Folder contents

| File | Purpose |
|---|---|
| `intake.md` | Intake form, returned and recorded once |
| `welcome-packet.md` | Customized welcome packet sent to family |
| `iep-checklist.md` | Ongoing IEP advocacy checklist |
| `session-log.md` | Append-only dated session entries |
| `observations/<yyyy-mm-dd>.md` | One file per observation, never edited |

## PII rules

- Never use the family's full first name + full last name in any file body or commit message.
- Use `<First> <LastInitial>.` as the display name inside frontmatter values when needed (e.g., for a welcome packet).
- Abbreviate school district names in committed files. Maintain the full district name only in a password manager or off-repo.
- The full EIN, policy numbers, bank info, etc. live in a password manager, never in `workspace/`.

## Why these conventions

- Sortable by intake date when the folder list grows
- PII-reduced if the repo is ever shared or backed up incorrectly
- Append-only logs preserve history; observations are never overwritten so audit trails hold up if a dispute escalates
