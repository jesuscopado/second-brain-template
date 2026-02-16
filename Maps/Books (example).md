---
date: 2026-01-20
---

```dataview
TABLE author, year, status
FROM "Atoms/Sources"
WHERE in = [[Books]] OR contains(in, [[Books]])
SORT year ASC
```
