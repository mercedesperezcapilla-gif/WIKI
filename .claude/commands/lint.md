---
description: Health-check the wiki for contradictions, orphans, broken links, stale claims, and missing cross-references
argument-hint: [optional: 'recent' | 'topic:<name>' | 'orphans']
---

You are running the **lint operation** on the wiki at `C:/Users/merce/Projects/wiki/`.

Scope: $ARGUMENTS (if empty, run full lint across all wiki pages)

## Workflow

### 1. Read the schema
Read `C:/Users/merce/Projects/wiki/CLAUDE.md` to refresh conventions and the rules lint should enforce.

### 2. Determine scope
- **No argument** → full lint across all markdown files in `C:/Users/merce/Projects/wiki/`
- **`recent`** → only pages modified in the last 30 days
- **`topic:<name>`** → only pages under that subfolder (e.g. `topic:Learning`)
- **`orphans`** → only check for orphan pages and broken links

### 3. Run the checks

Work through each systematically. Report findings — don't fix yet.

**A. Contradictions**
- Look for `> [!warning] Contradiction` callouts left unresolved from previous ingests.
- Look for substantive disagreement between pages on the same concept.
- List each contradiction: the two conflicting claims, their sources, and dates.

**B. Orphan pages**
- Pages with no inbound `[[wikilinks]]` from any other page.
- Pages not referenced in `index.md`.
- Suggest where each orphan should be linked from, or whether it should be archived.

**C. Broken links**
- `[[wikilinks]]` pointing to pages that don't exist.
- For each: suggest create the missing page, fix the link, or remove it.

**D. Stale claims**
- Claims with old dates that may no longer hold ("as of 2024", "current policy is").
- Pages not modified in 6+ months covering fast-moving topics (AI regulation, career targets, live projects).
- Flag for review — refresh or archive.

**E. Missing cross-references**
- Pages that mention an entity by name but don't link to its page.
- Entity pages that don't link back to the sources they were derived from.

**F. Index hygiene**
- Pages in the wiki not listed in `index.md`.
- Entries in `index.md` pointing to pages that don't exist.
- One-line summaries in `index.md` that no longer match the page content.

**G. Schema drift**
- Pages that deviate from CLAUDE.md conventions: naming, structure, missing one-line summary at top.

### 4. Surface open questions

End with a "Questions the wiki is asking" section:
- What concepts are clearly underdeveloped?
- What contradictions need resolution before the wiki can answer related questions confidently?
- What sources should be ingested next, based on gaps?

### 5. Append to log
Append a single line to `C:/Users/merce/Projects/wiki/log.md`:

```
[LINT] YYYY-MM-DD | <scope> | <N findings>
```

### 6. Ask before fixing
Do NOT auto-fix anything during the lint pass. The user reviews findings and chooses what to act on. Offer to run targeted fixes if asked (safe ones only: linking orphans, updating index entries, removing broken links).

## Output format
Use clear section headers (A through G). Within each section, a compact table or bulleted list. Scannable, not exhaustive.
