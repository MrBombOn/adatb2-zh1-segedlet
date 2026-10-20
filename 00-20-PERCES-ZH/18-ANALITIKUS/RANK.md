# RANK

**P1 · GYORS** · 11g

> **Tanulási példa – ne másold be ZH-megoldásként.**

```sql
RANK() OVER (PARTITION BY <p> ORDER BY <r> DESC) AS rk
```

Azonos érték → azonos rang, **lyuk** a következőnél (1,2,2,4).

→ [`DENSE-RANK.md`](DENSE-RANK.md)
