# Harness Changelog

Log every skill, command, and structural change so Rylee can see what's new without spelunking the diff. Newest first.

## 2026-05-22 — Tier 0 + Tier 1 ships

### Added
- `CLAUDE.md` — orientation, house rules, conventions
- `.claude/shared/disclaimer.md` + `snippets/disclaimer.mdx` — single-source scope-of-practice language
- `docs.json` — restructured to Course / Reference / Harness tabs
- `course/index.mdx` — course landing with 8-module index and relevance markers
- `course/module-1-business.mdx` — first module page
- **Skills**:
  - `business-name` — name brainstorming + IL Secretary of State availability guidance
  - `entity-setup` — IL LLC/PLLC/sole-prop walkthrough; federal + IL sections partitioned
  - `services-fees` — services catalog + fee schedule
  - `intake-process` — intake form, welcome packet, services-agreement checklist (for attorney review)
- **Commands**:
  - `/session-start` — read `workspace/progress.md`, surface resume point
  - `/progress` — render and update course progress dashboard
  - `/new-client <name>` — instantiate client folder from intake assets
  - `/find <query>` — grep `workspace/`
- **Workspace scaffold**: `workspace/business/`, `workspace/notes/module-1.md`, `workspace/progress.md`, `workspace/clients/README.md`

### Removed
- Mintlify starter pages from nav (`quickstart`, `development`, `essentials/*`, `ai-tools/*`, `api-reference/*`)

## Log entry template

```
## YYYY-MM-DD — short title

### Added
- `<path>` — what it does, why

### Changed
- `<path>` — what changed, why

### Removed
- `<path>` — why
```
