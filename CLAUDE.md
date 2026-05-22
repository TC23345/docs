# Orientation for Claude

This repo is the agentic harness for the **Pivot into IEP Advocacy** course (iepadvocacytraining.com, Dr. Annie McLaughlin) — an 8-module program that trains behavior analysts to launch a private-pay IEP advocacy practice.

## Who you are talking to

- **Rylee Coteus, MS, BCBA** — the practitioner. Coach and BCBA at NSSEO in Palatine, IL. ~3 years of behavior-analysis experience. Already fluent in IDEA, the IEP process, eligibility categories, ABA assessment and observation methodology. She is pivoting from school-based work into private-pay IEP advocacy.
- **Her brother** — the AI-native integrator who builds and maintains this harness. Will edit skills, commands, and docs. May not be in the room when Rylee is using it.

Default to Rylee as the user unless context says otherwise.

## House rules

- **Skip beginner SpEd content.** Do not explain what an IEP is, what IDEA is, or what an observation is. Assume professional fluency.
- **Default to Illinois** when state varies (entity registration, licensure, ISBE procedure, state advocate directories). Note the IL-specific assumption when you make it.
- **Scope-of-practice gate.** When a request touches entity tax choice, binding contract terms, specific legal strategy for a child's dispute, or insurance coverage selection, defer to the right licensed professional (CPA, attorney, insurance broker). Continue with the non-regulated portions of the work. Do **not** open replies with blanket disclaimers; only invoke `.claude/shared/disclaimer.md` when you are actually crossing the line.
- **PII policy.** Client folders live at `workspace/clients/<lastname-firstinitial>-<yyyymm>/` (e.g., `doe-j-202605/`). Never use full client names in commit messages, file names outside that folder, or shared documents. Never paste school district names without abbreviation when committing to git.
- **Append-only session logs.** `workspace/clients/<id>/session-log.md` is dated headers; new sessions append. Don't rewrite history. New observations go in `observations/<yyyy-mm-dd>.md`, never overwrite.
- **Skill description drift.** When you edit a `SKILL.md` procedure, re-read and re-justify the `description` frontmatter. Stale descriptions break retrieval.

## Where things live

- `.claude/skills/<name>/SKILL.md` — knowledge+procedure capabilities, auto-discovered by description. Templates in `assets/`, long references in `references/`.
- `.claude/commands/<name>.md` — Rylee-initiated rituals. Predictable behavior. See `/session-start`, `/progress`, `/new-client`, `/find`.
- `.claude/shared/disclaimer.md` — single-source scope-of-practice language. Hard-reference from skills.
- `.claude/CHANGELOG.md` — brother logs every skill/command addition here.
- `course/` — Mintlify pages: per-module summaries, IL resources, glossary. Condensed for Rylee's level. Each module page carries a standard header block (`relevance`, `rylee_already_knows`, `new_for_rylee`, `skills`, `commands`).
- `snippets/disclaimer.mdx` — Mintlify import-side of the disclaimer (same content as the shared one).
- `workspace/` — committed mutable practice ledger. Source of truth for business decisions, client folders, referral map, module notes, progress dashboard. **Not** published through Mintlify.

## Conventions to enforce

- **Workspace frontmatter**: every file in `workspace/` carries `client_id` (or `none`), `created`, `last_updated`, `module_context`. `/progress` and `/find` grep this.
- **Skill path templates**: skills reference workspace via `workspace/clients/{client_id}/<file>.md`. Resolve `{client_id}` from the current conversational context or ask once.
- **Bidirectional linkage**: each `course/module-N.mdx` lists skills/commands it activates; each `SKILL.md` body lists the source module(s).
- **One client = one directory, append-only logs.**

## Session-start ritual

At the top of a session, if Rylee does not explicitly say what she's doing, run the `/session-start` command. It reads `workspace/progress.md` and surfaces the resume point.

## Build status (Tier 1)

Tier 0 (orientation) and Tier 1 (Module 1 + cross-cutting commands) are the live scope. Tier 2 (Modules 2–3 thin slice) and Tier 3 (Modules 4–8) scaffold later as Rylee progresses. See `/root/.claude/plans/can-you-please-plan-tranquil-fern.md` for the full plan and `.claude/CHANGELOG.md` for what has actually shipped.
