# Second Brain — Context for Claude Code

## About this vault

This is a personal Second Brain managed with Obsidian and Claude Code. It stores knowledge, tracks projects, and manages daily workflows — all in local markdown files.

## About the owner

<!-- Customize this section with your own info -->
- **Name**: Your Name
- **Role**: Your role
- **Focus areas**: Your interests and specializations
- **Email**: your@email.com

## Structure

```
vault/
├── +/              # Inbox: quick capture, process later
├── Atoms/          # All knowledge (timeless)
│   ├── People/     # People
│   ├── Things/     # Ideas, concepts, reflections, recommendations
│   └── Sources/    # Sources (books, articles, videos, etc.)
├── Calendar/       # Everything temporal
│   ├── Logs/       # Logs (YYYY-MM-DD - Name.md)
│   └── (dailies)   # YYYY-MM-DD.md
├── Maps/           # Auto-generated indexes (Dataview on `in` field)
├── Projects/       # Projects and life efforts (by intensity)
│   ├── On/         # Full focus right now
│   ├── Ongoing/    # Continuous efforts
│   ├── Simmering/  # On pause, might reactivate
│   ├── Sleeping/   # Hibernated
│   └── Wrapped/    # Done, won't return
└── x/              # Extras
    ├── Attachments/ # Images, PDFs
    └── Templates/   # Note templates
```

**Philosophy:**
- **Atoms**: All knowledge. Three subfolders: `People/` (people), `Things/` (ideas, concepts, reflections, recommendations), `Sources/` (original sources). The folder determines the type — the decision when creating is: person, source, or everything else?
- **Projects**: Projects organized by intensity. The folder determines the status — no `status` field in frontmatter. `rank` (1-5) orders by priority within each folder.
- **Calendar**: Everything temporal. Dailies, tasks, and logs.

## Atoms subfolders

| Folder | Contains | Decision |
|--------|----------|----------|
| `People/` | People (profiles, relevant contacts) | Is it a person? |
| `Things/` | Ideas, concepts, reflections, recommendations | Everything else |
| `Sources/` | Original sources (books, articles, videos) | Is it a consumable source? |

## Maps (auto-generated indexes)

- **Folder**: `Maps/`
- **What they are**: Index notes that use Dataview to automatically list all notes belonging to a topic.
- **How it works**: Notes have an `in` field in frontmatter with a link to the Map. E.g.: `in: "[[AI]]"`. The Map `Maps/AI.md` has a Dataview query that finds all notes with `in: [[AI]]` and displays them.
- **When to create a Map**: When there are 5+ notes about a topic. Not before.
- **Multiple values**: `in: ["[[AI]]", "[[Personal Brand]]"]` — the note appears in both Maps.

## Calendar

- **Folder**: `Calendar/`
- **Content**: Everything tied to a date — daily check-ins, daily notes, yearly goals
- **Daily notes**: `Calendar/YYYY-MM-DD.md`
- **Source of Truth**: `Calendar/YYYY - Source of Truth.md` — yearly document with intention, goals, non-negotiables, and monthly priorities. Created once per year.
- **Logs**: `Calendar/Logs/` — conversation logs, decisions, brainstorms. Named with date prefix: `YYYY-MM-DD - Name.md`
- **Past Years**: `Calendar/Past Years/` — archive for old dailies, logs, and Source of Truth when a new year starts
- **No connection rules** — temporal notes tied to dates

## Connection rules

| Type | Rule |
|------|------|
| **Atoms/Things** | ≥1 inlink + ≥2 outlinks (recommended for ideas, not mandatory) |
| **Atoms/People** | No rules — connect if it makes sense |
| **Atoms/Sources** | Inlinks only (extracted Things link back to them) |
| **Projects** | None |
| **Calendar** | None — temporal notes |

**Important:** Links must be **integrated in the text** (Wikipedia-style), not in "Related:" sections at the end.

Connection rules are a guide, not a law. A restaurant recommendation doesn't need connections. An idea about agentic coding does.

## Templates

| Template | Use |
|----------|-----|
| `x/Templates/Atom.md` | Things (ideas, concepts, reflections) |
| `x/Templates/Source.md` | Sources (books, articles, etc.) |
| `x/Templates/Person.md` | People |
| `x/Templates/Project.md` | Projects |
| `x/Templates/Source of Truth.md` | Yearly goals and priorities |

### Valid frontmatter values

**Source.md:**

| Field | Values |
|-------|--------|
| `type` | `book`, `article`, `video`, `film`, `podcast`, `tweet`, `paper` |
| `status` | `to-consume`, `in-progress`, `completed` |

**Project.md:**

| Field | Values |
|-------|--------|
| `date` | Creation date |
| `rank` | Priority 1-5 within its folder (5 = highest) |

## Task system

Tasks are **checkboxes (`- [ ]`) inside the notes where they belong**, not separate files. The **Tasks** plugin aggregates them from the whole vault.

**How to create tasks:**
- Add `- [ ] Do something 📅 2026-02-20` inside the relevant note
- Tasks plugin emojis: `📅` (due date), `⏳` (scheduled), `✅` (done date)

## Format conventions

- **Frontmatter**: always in English (`date`, `status`, `tags`, etc.)
- **Sections**: titles in English (`## Overview`, `## Key ideas`, `## References`)
- **Content**: any language
- **Links**: integrated in text (Wikipedia-style), not in "Related:" sections

## Commands

Available as `/command` in Claude Code:

| Command | Description |
|---------|-------------|
| `/daily` | Morning check-in + day briefing |
| `/braindump` | Quick capture — dump raw text, Claude classifies it |
| `/url` | URL → Source note with summary, key ideas, highlights |
| `/weekly` | Weekly reflection — review, synthesize, plan |
| `/consolidate` | Knowledge consolidation — connect orphans, suggest Maps, add wikilinks |
| `/sync` | Commit + push all changes |

## Tools: when to use what

| Operation | Tool | Why |
|-----------|------|-----|
| Edit content | `Edit` (native) | More direct |
| Write new note | `Write` (native) | More direct |
| Read note | `Read` (native) | More direct |
| Search vault | `Grep` / `Glob` (native) | Fast search |
| Move/delete note | `move_note`/`delete_note` (MCP) | Maintains integrity |

## Notes for Claude

- **NEVER** send emails or create calendar events without explicit user confirmation
- **Daily routine**: At the start of a conversation, check if `Calendar/YYYY-MM-DD.md` exists for today. If not, ask: "Want to do your /daily?"
- Links go integrated in text, NEVER in separate "Related:" sections
- Always confirm before creating/modifying notes — present plan, wait for OK
- Search before creating — avoid duplicates
- Use the exact templates from `x/Templates/`
