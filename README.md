# IEP Advocacy Course Harness

Companion site + agentic harness for Rylee Coteus (MS, BCBA) and her brother to work through the 8-module **Pivot into IEP Advocacy** course (iepadvocacytraining.com) while building Rylee's private-pay practice.

## What's in here

- `course/` — Mintlify pages: module summaries, IL resources, glossary
- `harness/` — Mintlify pages documenting the commands and skills
- `.claude/skills/` — auto-discovered knowledge+procedure capabilities
- `.claude/commands/` — Rylee-initiated slash commands (`/session-start`, `/progress`, `/new-client`, `/find`)
- `.claude/shared/disclaimer.md` — single-source scope-of-practice language
- `.claude/CHANGELOG.md` — log of every harness change
- `workspace/` — committed practice ledger (business decisions, client folders, notes, progress)
- `snippets/disclaimer.mdx` — Mintlify import-side of the disclaimer
- `CLAUDE.md` — orientation for Claude

## Running the docs site locally

```
npm i -g mint
mint dev
```

Then open `http://localhost:3000`.

## Using the harness in a Claude Code session

```
/session-start
```

That reads `workspace/progress.md` and surfaces where you left off. Then trigger skills conversationally ("let's brainstorm business names" → `business-name` skill loads).

See `harness/index.mdx` for the full guide and `CLAUDE.md` for house rules.
