# HAVING COUNT — önálló quick

**P0** · 11g

## 5 MÁSODPERCES FELISMERÉS

„Legalább / pontosan / több mint N a **csoportban**” → HAVING COUNT.

## Teljes SQL

```sql
SELECT <c>, COUNT(*) AS db
FROM   <t>
GROUP BY <c>
HAVING COUNT(*) >= <n>;
```

LEFT „nulla gyerek”: `COUNT(<jobb>.<pk>) = 0` — lásd JOIN 3 perc.

## Placeholder — MIT ÍRJ / HONNAN VESZEM

| Helyőrző | MIT ÍRJ | HONNAN VESZEM |
|----------|---------|---------------|
| `<c>` | Csoportkulcs | **feladat** |
| `<n>` | Küszöb | **feladat** |
| `>= > = <` | Összehasonlító | **feladat** |

Canonical: [`README.md`](README.md)
