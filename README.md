# WIKI

A personal knowledge base maintained by Claude Code, using the [Karpathy LLM wiki pattern](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f).

Knowledge is compiled once and kept current — not re-derived at query time. Claude reads, structures, and cross-links everything. You query it like a second brain.

---

## What's in here

### Source material
Two PDFs used as source material for the wiki:

- `ai-automation-howto-guide.pdf`
- `ai-second-brain-guide.pdf`

### Claude Code slash commands
Four commands that maintain the wiki when you open this folder in Claude Code:

| Command | What it does |
|---|---|
| `/ingest <file or URL>` | Reads a source, extracts key claims, updates wiki pages and the index |
| `/lint` | Health-checks for contradictions, orphan pages, broken links, stale claims |
| `/save-to-vault` | End-of-session capture — extracts decisions, insights, open threads |
| `/daily [N]` | Read-only digest of what changed in the last N days |

---

## How to use

1. Clone this repo
2. Open the folder in Claude Code
3. Run `/ingest <your source>` to start building your wiki
4. Run `/daily` each morning to see where things stand

The commands live in `.claude/commands/` — edit them freely to match your own folder structure and conventions.

---

*Built by [@mercedesperezcapilla-gif](https://github.com/mercedesperezcapilla-gif). Based on the Karpathy LLM wiki pattern.*
