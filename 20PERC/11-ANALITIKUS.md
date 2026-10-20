# Analitikus — OVER / PARTITION

**P1** · MÓD A: minden sor (nincs rn=1) · MÓD B: rn=1

```sql
-- A
SELECT e.*, SUM(e.<n>) OVER (PARTITION BY e.<p>) AS part_sum,
       ROW_NUMBER() OVER (PARTITION BY e.<p> ORDER BY e.<r> DESC) AS rn
FROM <tabla> e;

-- B
SELECT * FROM ( /* ugyanaz */ ) WHERE rn = 1;
```

GROUP BY összevon; PARTITION megtartja a sorokat.

**RÉSZLETESEN:** [`../00-20-PERCES-ZH/18-ANALITIKUS/INTEGRATED-SUM-ROW-NUMBER.md`](../00-20-PERCES-ZH/18-ANALITIKUS/INTEGRATED-SUM-ROW-NUMBER.md)
