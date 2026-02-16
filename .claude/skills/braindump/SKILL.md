---
name: braindump
description: Quick capture — dump raw text and Claude classifies it into your vault
disable-model-invocation: true
allowed-tools: Read, Write, Edit, Glob, Grep, AskUserQuestion, ToolSearch
---

The user dumps raw text. Your job is to classify each piece and route it to the right place in the vault.

**Input:** $ARGUMENTS

## Step 1: Receive input

If `$ARGUMENTS` is empty, ask:
> What's on your mind? Dump everything — ideas, people, sources, tasks, whatever. I'll sort it out.

## Step 2: Classify each piece

Analyze the text and classify each piece:

| Category | Destination | Criteria |
|----------|-------------|----------|
| **Thing** | `Atoms/Things/` | Idea, concept, reflection, recommendation |
| **Source** | `Atoms/Sources/` | Consumable source (book, article, video, podcast) |
| **Person** | `Atoms/People/` | Person (contact, reference, collaborator) |
| **Task** | Checkbox in relevant note | Something to do (concrete action) |

## Step 3: Present classification

Show the classification BEFORE creating anything:

```
I've classified your braindump:

Things:
- "idea name" → Atoms/Things/Name.md

Sources:
- "book title" → Atoms/Sources/Title - Author.md

People:
- "name" → Atoms/People/Name.md

Tasks:
- "do X" → checkbox in [relevant note]
```

Ask: **Does this look right, or do you want to change anything?**

## Step 4: Check for duplicates

BEFORE creating each note, search the vault for similar content:
- Use `Grep` to search by name/title
- Use `Glob` to find files with similar names
- If you find something similar, ask: "I found `[[Existing Note]]`. Is this the same thing or should I create a new one?"

## Step 5: Create notes

For each confirmed piece:

**Things** — Use the exact template from `x/Templates/Atom.md`:
```yaml
---
date: YYYY-MM-DD
in:
---
```
Add a brief paragraph with the idea. If you can link to existing vault notes with wikilinks `[[note]]`, do so integrated in the text (Wikipedia-style).

**Sources** — Use the exact template from `x/Templates/Source.md`:
```yaml
---
date: YYYY-MM-DD
type: [book/article/video/podcast/paper/tweet/film]
author:
year:
status: to-consume
in:
url:
---
## Overview

[brief description]

## Key ideas
-

## Highlights
>
```

**People** — Use the exact template from `x/Templates/Person.md`:
```yaml
---
date: YYYY-MM-DD
in:
---
```
Add context about the person below.

**Tasks** — Add checkbox in the most relevant note (active project, today's daily, or topic note):
```
- [ ] Do something 📅 YYYY-MM-DD
```

## Step 6: Suggest connections

After creating notes:
1. **Maps**: Check what Maps exist in `Maps/` (use Glob). Suggest the `in` field for each note.
2. **Wikilinks**: Suggest links between new notes and existing vault notes.
3. Present suggestions and wait for confirmation before applying.
