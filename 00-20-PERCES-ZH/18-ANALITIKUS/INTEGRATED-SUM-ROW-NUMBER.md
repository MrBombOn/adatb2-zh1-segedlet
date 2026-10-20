# Integrated SUM + ROW_NUMBER — önálló quick

**P1** · 11g · egy sablon

## 5 MÁSODPERCES FELISMERÉS

„Csoportonként a leg… **és** minden sor / győztes mellett a csoport összege.”

## Teljes SQL

```sql
SELECT *
FROM (
  SELECT e.<oszlopok>,
         SUM(e.<n>) OVER (PARTITION BY e.<p>) AS part_sum,
         ROW_NUMBER() OVER (
           PARTITION BY e.<p>
           ORDER BY e.<r> DESC
         ) AS rn
  FROM   <tabla> e
)
WHERE rn = 1;
```

## Placeholder — MIT ÍRJ / HONNAN VESZEM

| Helyőrző | MIT ÍRJ | HONNAN VESZEM |
|----------|---------|---------------|
| `<p>` | Partíció (dept/author) | **feladat** |
| `<r>` | Rangsor kulcs | **feladat** |
| `<n>` | Összegezendő szám | **feladat** |
| `rn = 1` | Legelső a partícióban | **tipikus** Top-1 |

**TILOS:** FETCH FIRST. Canonical: [`README.md`](README.md)
