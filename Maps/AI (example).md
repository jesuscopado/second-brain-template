---
date: 2026-01-01
---
# AI

Map of everything related to artificial intelligence, agents, and LLMs.

## Things

```dataview
TABLE date as "Date"
FROM "Atoms/Things"
WHERE contains(in, [[AI]])
SORT date desc
```

## Sources

```dataview
TABLE author as "Author", type as "Type"
FROM "Atoms/Sources"
WHERE contains(in, [[AI]])
SORT date desc
```

## People

```dataview
LIST
FROM "Atoms/People"
WHERE contains(in, [[AI]])
SORT file.name asc
```

> This is an example Map. Create your own when you have 5+ notes about a topic. The Dataview queries automatically list all notes with `in: "[[AI]]"` in their frontmatter.
