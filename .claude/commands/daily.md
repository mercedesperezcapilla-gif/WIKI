---
description: Daily digest — what changed in the wiki, what's open, what needs attention today
argument-hint: [optional: number of days to look back, default 1]
---

You are running the **daily digest** for the wiki at `C:/Users/merce/Projects/wiki/`.

Lookback window: $ARGUMENTS days (default 1 if no argument given).

This is a read-only operation. Do not modify any files.

## Workflow

### 1. Read the log
Read `C:/Users/merce/Projects/wiki/log.md` and pull all entries from the lookback window. This tells you what ingests, lints, and saves happened.

### 2. Read the index
Read `C:/Users/merce/Projects/wiki/index.md` to understand the current shape of the wiki. Read `C:/Users/merce/Projects/wiki/CLAUDE.md` for context on what matters.

### 3. Identify what changed
For each page touched in the lookback window:
- Which page
- One-line summary of what changed (read the page if needed, but be efficient)
- Why it changed (which log entry triggered it)

### 4. Identify what's open
- **Unresolved contradictions** — `> [!warning] Contradiction` callouts still open
- **Open questions** — flagged in recent ingests or lints
- **Orphan pages** — added recently but not yet linked
- **Stale claims** — flagged in the most recent lint pass

### 5. Suggest one thing to do today
Based on what's open and what's been ingested recently, suggest one concrete action. Examples:
- "Resolve the contradiction on `[[Topic X]]` — two sources disagree."
- "Three sources on `[[Y]]` ingested but no synthesis page yet."
- "No lint pass in 14 days — worth a run."

Just one suggestion. Not a list.

### 6. Output

A single scannable digest, under 250 words:

```
## Wiki Digest — [date]

**Activity (last N days)**
- X sources ingested, Y pages updated
- Z lint pass(es), N findings

**What changed**
- [[Page A]] — added section on X (from <source>)
- [[Page B]] — created (entity page for Y)

**What's open**
- Contradiction: [[Topic X]] — needs resolution
- 2 orphans from last week's ingests
- Stale claim on [[Z]] flagged Tuesday

**Today's suggestion**
Resolve the contradiction on [[Topic X]] — two sources disagree on Y. 10 minutes.
```

## Constraints
- Read-only. No edits, no log entries (daily does not log itself — it's a viewer).
- If nothing has changed in the lookback window, say so plainly. Don't manufacture activity.
- If the wiki is brand new (under 10 pages, no log history), say so and suggest ingesting a few sources first.
