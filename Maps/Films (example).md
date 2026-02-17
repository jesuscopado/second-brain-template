---
date: 2026-01-01
---
# Films

Map of films and documentaries.

## All Films

```dataview
TABLE author as "Director", status as "Status"
FROM "Atoms/Sources"
WHERE contains(in, [[Films]])
SORT date desc
```

> This is an example Map. Create your own when you have 5+ notes about a topic. The Dataview queries automatically list all notes with `in: "[[Films]]"` in their frontmatter.
