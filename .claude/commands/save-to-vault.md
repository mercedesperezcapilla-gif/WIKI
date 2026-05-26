---
description: Capture key insights, decisions, and open threads from the current session into the wiki
argument-hint: [optional: one-line description of what this session was about]
---

You are running the **save-to-vault operation** at the end of a Claude Code session on the wiki at `C:/Users/merce/Projects/wiki/`.

Session topic (optional): $ARGUMENTS

The goal is to make sure nothing important from this conversation evaporates when the session closes.

## Workflow

### 1. Read the schema
Read `C:/Users/merce/Projects/wiki/CLAUDE.md` to refresh wiki conventions and the rules for what belongs where.

### 2. Reflect on the session
Look back at the entire conversation and identify:

- **Decisions made** — choices that may not be remembered exactly later
- **Key insights** — non-obvious things that emerged from the work
- **Open threads** — questions raised but not resolved, work not finished
- **New entities/concepts** — people, projects, tools, ideas that came up for the first time
- **Changes in thinking** — places where a position was updated
- **Useful artefacts produced** — drafts, structures, plans worth keeping

Don't include: routine back-and-forth, refinements that landed in a final artefact already.

### 3. Propose what to save

Present a structured plan before writing anything:

**To the wiki** (`C:/Users/merce/Projects/wiki/`):
- Which page(s) should be updated or created (use the right subfolder)
- What specific content goes where
- Any new cross-references to add

**To the log** (`C:/Users/merce/Projects/wiki/log.md`):
- A one-line entry summarising this session

### 4. Wait for confirmation
The user reviews and approves/edits the plan before you write. They may say "skip that page" or "add this to a different page instead."

### 5. Execute the writes
- Update or create wiki pages with the agreed content
- Add `[[wikilinks]]` between related pages
- Update `C:/Users/merce/Projects/wiki/index.md` if new pages were created
- Append to log:

```
[SAVE] YYYY-MM-DD | <session topic> | <N pages touched>
```

### 6. Report
End with a short summary: pages updated/created, open threads carried forward.

## Constraints
- Be selective. A good save-to-vault touches 1–5 files, not 20.
- If nothing meaningful happened (quick question, one-off task), say so and skip the save. Not every session deserves an entry.
- If the session produced a draft or artefact the user might publish (article, message, document), make sure it's either filed in `sources/` or the user has explicitly chosen to keep it elsewhere.
