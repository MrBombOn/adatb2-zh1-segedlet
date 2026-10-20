# OVER — analitikus ablakkifejezés

**P1 · GYORS** · Oracle **11g ONLY**

> **Tanulási példa – ne másold be ZH-megoldásként.**

```sql
<agg_vagy_rank>() OVER (
  [PARTITION BY <p>]
  ORDER BY <r> [ASC|DESC]
)
```

- GROUP BY → sorok összeolvadnak
- OVER → **sorok megmaradnak**, mellé számít eredményt

→ [`README.md`](README.md) · [`GROUP-BY-VS-PARTITION-BY.md`](GROUP-BY-VS-PARTITION-BY.md)
