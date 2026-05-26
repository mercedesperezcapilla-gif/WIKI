---
description: Ingest a new source into the wiki — extracts key claims, updates pages, cross-links, and logs the operation
argument-hint: <path to file in sources/ or a URL>
---

You are running the **ingest operation** on the wiki at `C:/Users/merce/Projects/wiki/`.

The source to ingest: $ARGUMENTS

If no argument was provided, list the files in `C:/Users/merce/Projects/wiki/sources/` and ask which one to ingest, or whether the user wants to paste a URL or text directly.

## Workflow

### 1. Read the schema
Read `C:/Users/merce/Projects/wiki/CLAUDE.md` to refresh conventions — entity types, page structure, naming rules, what belongs in sources vs wiki pages.

### 2. Read the source
- If it's a file in `sources/`, read it directly.
- If it's a URL, fetch it.
- If it's pasted text, work with what's provided.
- If the source isn't already in `sources/`, save a copy there with a date-prefixed filename: `YYYY-MM-DD-short-slug.md` (or appropriate extension).

### 3. Surface key takeaways
In 3–6 bullet points, surface the most important claims from the source. Flag anything that:
- Contradicts existing wiki claims
- Opens new questions
- Introduces a new entity, concept, or date worth capturing

### 4. Plan the wiki updates
Before writing, list which wiki pages you intend to:
- **Create** — new entity or concept pages
- **Update** — existing pages this source adds to or changes
- **Cross-link** — pages that should now reference this source or each other

Wait for confirmation before writing — unless the user said "ingest and go" or similar.

### 5. Execute the updates
- Create or update pages in the appropriate subfolder (`Professional/`, `Learning/`, `Personal/`, `Community/`, `Entrepreneur/`, `Holidays and Adventures/`, `Claude Projects/`) using lowercase-hyphenated filenames.
- Add `[[wikilinks]]` between all related pages.
- Update `C:/Users/merce/Projects/wiki/index.md` — add a one-line entry for any new page, update existing entries if their summary changed.

### 6. Flag contradictions
If the source contradicts any existing wiki claim, do NOT silently overwrite. Add a `> [!warning] Contradiction` callout to the affected page noting both the old and new claim, the source of each, and a date. The user will resolve.

### 7. Append to log
Append a single line to `C:/Users/merce/Projects/wiki/log.md`:

```
[INGEST] YYYY-MM-DD | <source-name> | <N pages touched>
```

### 8. Report
End with a short summary: source ingested, pages created, pages updated, contradictions flagged, open questions surfaced.

## Constraints
- Never modify files in `sources/` — that layer is immutable.
- Never delete wiki pages during ingest. If a page is obsolete, flag it for the next `/lint` pass.
- Keep wiki pages under ~500 words. Long source content belongs in `sources/`, not in the wiki.
- Use the wiki's existing tone and conventions, not the source's.
- Page naming: lowercase, hyphenated — e.g. `aigp-risk-categories.md`.
