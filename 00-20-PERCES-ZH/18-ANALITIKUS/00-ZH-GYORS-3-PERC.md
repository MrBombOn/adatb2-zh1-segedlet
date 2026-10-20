# Analitikus — 3 perces gyorsút

**P1 · 3 PERC** · 11g · integrated fast path

> **Tanulási példa – ne másold be ZH-megoldásként.**

## 30 mp döntés

1. Rang / Top csoportonként? → ROW_NUMBER + külső `rn=1`
2. Mellé összeg/átlag/darab? → SUM/COUNT/AVG OVER
3. Egy sablonban mindkettő? → [`INTEGRATED-SUM-ROW-NUMBER.md`](INTEGRATED-SUM-ROW-NUMBER.md)

## Minimál sablon

```sql
SELECT * FROM (
  SELECT <oszlopok>,
         SUM(<n>) OVER (PARTITION BY <p>) AS part_sum,
         ROW_NUMBER() OVER (PARTITION BY <p> ORDER BY <r> DESC) AS rn
  FROM <tabla>
) WHERE rn <= <k>;   -- vagy = 1
```

**TILOS:** FETCH FIRST / LIMIT.

→ [`README.md`](README.md)
