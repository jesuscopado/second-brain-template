---
name: url
description: URL → Source note with summary, key ideas, and highlights
allowed-tools: Read, Write, Edit, Glob, Grep, WebFetch, WebSearch, AskUserQuestion, Skill, ToolSearch
---

The user gives you a URL. Your job is to extract the content and create a well-structured Source note.

**Input:** $ARGUMENTS

## Step 1: Receive URL

If `$ARGUMENTS` is empty, ask:
> What URL do you want to save?

## Step 2: Detect type and extract content

Detect the URL type and use the right strategy:

| Type | Detection | Strategy |
|------|-----------|----------|
| **YouTube** | `youtube.com/watch`, `youtu.be/` | Use skill `youtube-transcript` for transcription + `WebFetch` for metadata |
| **Twitter/X** | `twitter.com`, `x.com` | `WebFetch` (may fail, extract what you can) |
| **Article/Blog** | Everything else | `WebFetch` to extract content |

Extract:
- **Title** of the content
- **Author** (if identifiable)
- **Year** of publication
- **Type**: `article`, `video`, `podcast`, `paper`, `tweet`
- **Key ideas** (3-5 main points)
- **Highlights** (interesting direct quotes)

## Step 3: Present metadata for confirmation

Show what you extracted and ask if it looks right.

## Step 4: Status

Ask:
> Have you already consumed this, or is it for later?
> - `completed` — Already read/watched
> - `to-consume` — For later

## Step 5: Create Source note

Check first if a similar note already exists in `Atoms/Sources/` (by title or URL).

Create the note at `Atoms/Sources/Title - Author.md` using the exact template from `x/Templates/Source.md`:

```yaml
---
date: YYYY-MM-DD
type: [article/video/podcast/paper/tweet]
author: [author]
year: [year]
status: [to-consume/completed]
in:
url: [the original URL]
---
## Overview

[2-3 sentence summary]

## Key ideas
- [idea 1]
- [idea 2]
- [idea 3]

## Highlights
> [quote 1]

> [quote 2]
```

If no author: just `Title.md`. Clean special characters from the title.

## Step 6: Suggest connections

1. **Maps**: Check existing Maps in `Maps/`. Suggest the `in` field.
2. **Things**: Suggest if any key idea deserves its own note in `Atoms/Things/`. Don't create automatically — just suggest.
3. Wait for confirmation before applying.
