---
date: 2026-01-15
---

```dataview
TABLE author, year, status
FROM "Atoms/Sources"
WHERE in = [[Films]] OR contains(in, [[Films]])
SORT year ASC
```
