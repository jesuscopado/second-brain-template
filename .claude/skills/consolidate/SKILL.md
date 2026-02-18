---
name: consolidate
description: Knowledge consolidation — connect orphans, suggest Maps, add wikilinks
allowed-tools: Read, Write, Edit, Glob, Grep, AskUserQuestion, ToolSearch
---

Time to consolidate the vault. Review scattered notes, find connection opportunities, and improve the knowledge graph.

## Step 1: Scan orphans

Find notes that need attention by analyzing links:

1. **Read all Things**: Use Glob to list all files in `Atoms/Things/`. Read each one.
2. **Check inlinks**: For each Thing, search the rest of the vault (using Grep) to see if any other note links to it via `[[Note Name]]`. Notes with zero inlinks are orphans.
3. **Check outlinks**: For each Thing, count how many `[[wikilinks]]` it contains. Notes with fewer than 2 outlinks need more connections.

## Step 2: Build connection map

Read all notes in `Atoms/` and build a mental map of:
- What note links to what (outlinks via `[[wikilinks]]`)
- What note is linked by whom (inlinks)
- What topics they cover (via the `in` frontmatter field)

Present a summary:
```
Vault health:
- Total Things: X
- Orphans (no inlinks): X
- Underconnected (fewer than 2 outlinks): X
- Well connected (≥1 inlink + ≥2 outlinks): X
- Sources: X
- People: X
- Maps: X
```

## Step 3: Find wikilink opportunities

For each Thing that is an orphan or underconnected:
1. Read its content
2. Search in OTHER vault notes if they mention the same concept without linking
3. Search if this note mentions concepts that exist as notes but aren't linked

Example suggestion:
```
Connection suggested:
In "Atoms/Things/Prompt Engineering.md" (line 5):
  Before: "...language models need context..."
  After: "...[[LLMs]] need context..."
```

## Step 4: Identify new Map candidates

Review the `in` fields of all notes and find patterns:
- Are there topics in 5+ notes that don't have a Map?
- Are there notes without `in` that could belong to an existing Map?

Suggest new Maps only if there's critical mass (5+ notes).

## Step 5: Detect possible merges

Look for notes that might be the same thing:
- Very similar names
- Significantly overlapping content
- Same topic from slightly different angles

Only suggest a merge if it's clear. When in doubt, don't.

## Step 6: Present everything as suggestions

Show ALL suggestions organized by type BEFORE making any changes:

```
Consolidation suggestions:

Wikilinks to add (X):
1. In "Note A.md" (line N): "text" → "text with [[link]]"

New Maps to create (X):
1. "Maps/Topic.md" — groups: Note A, Note B, Note C...

Possible merges (X):
1. "Note A.md" and "Note B.md" — cover the same thing

`in` fields to add (X):
1. "Note A.md" → in: "[[Existing Map]]"
```

**WAIT FOR APPROVAL** — Don't execute anything until the user confirms which suggestions to apply.

## Step 7: Execute approved changes

Only after confirmation:

1. **Wikilinks**: Use Edit to add `[[links]]` in note text. Links go integrated in text (Wikipedia-style), NEVER in "Related:" sections.
2. **New Maps**: Create following the existing Map pattern — with Dataview sections for Things, Sources, and People.
3. **`in` field**: Use Edit to update frontmatter with suggested Maps.

## Step 8: Final summary

Show what was done:
```
Consolidation complete:
- X wikilinks added
- X Maps created
- X `in` fields updated
```

## Important

- **NEVER make changes without approval**
- Links ALWAYS integrated in text, not in loose sections
