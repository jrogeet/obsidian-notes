---
sticker: lucide//list
---
```dataview
TABLE Topic, week, term
FROM #netc
WHERE term="prelim"
SORT file.mtime asc
```

```dataview
TABLE week, term
FROM #netc
WHERE term="midterm"
```

```dataview
TABLE week, term
FROM #netc
WHERE term="finals"
```
