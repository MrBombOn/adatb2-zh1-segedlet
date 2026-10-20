# DENSE_RANK

**P1 · GYORS** · 11g

> **Tanulási példa – ne másold be ZH-megoldásként.**

```sql
DENSE_RANK() OVER (PARTITION BY <p> ORDER BY <r> DESC) AS dr
```

Azonos érték → azonos rang, **lyuk nélkül** (1,2,2,3).

→ [`RANK.md`](RANK.md)
