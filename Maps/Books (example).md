---
date: 2026-01-01
---
# Books

Map of books — read, in progress, or to read.

## All Books

```dataview
TABLE author as "Author", status as "Status"
FROM "Atoms/Sources"
WHERE contains(in, [[Books]])
SORT date desc
```

> This is an example Map. Create your own when you have 5+ notes about a topic. The Dataview queries automatically list all notes with `in: "[[Books]]"` in their frontmatter.
