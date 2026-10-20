# ROW_NUMBER

**P1 · GYORS** · 11g

> **Tanulási példa – ne másold be ZH-megoldásként.**

```sql
SELECT * FROM (
  SELECT <oszlopok>,
         ROW_NUMBER() OVER (PARTITION BY <p> ORDER BY <r> DESC) AS rn
  FROM   <tabla>
) WHERE rn = 1;
```

Egyedi sorszám — döntetlennél is különböző. **Nincs FETCH FIRST** (12c+).

→ [`RANK.md`](RANK.md) · [`../09-TOP1-ES-SUBQUERY/`](../09-TOP1-ES-SUBQUERY/)
