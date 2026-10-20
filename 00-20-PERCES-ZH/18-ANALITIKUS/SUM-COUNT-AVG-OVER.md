# SUM / COUNT / AVG OVER

**P1 · GYORS** · 11g

> **Tanulási példa – ne másold be ZH-megoldásként.**

```sql
SELECT <oszlopok>,
       SUM(<n>)   OVER (PARTITION BY <p>) AS szum_part,
       COUNT(*)   OVER (PARTITION BY <p>) AS db_part,
       AVG(<n>)   OVER (PARTITION BY <p>) AS atlag_part,
       SUM(<n>)   OVER ()                 AS szum_ossz
FROM   <tabla>;
```

→ [`INTEGRATED-SUM-ROW-NUMBER.md`](INTEGRATED-SUM-ROW-NUMBER.md)
