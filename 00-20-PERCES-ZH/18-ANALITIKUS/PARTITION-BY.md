# PARTITION BY

**P1 · GYORS** · 11g

> **Tanulási példa – ne másold be ZH-megoldásként.**

```sql
SUM(<n>) OVER (PARTITION BY <csoport>) AS part_sum
ROW_NUMBER() OVER (PARTITION BY <csoport> ORDER BY <r> DESC) AS rn
```

„Kurzusonként / osztályonként / szerzőnként” → Partition.

→ [`README.md`](README.md)
