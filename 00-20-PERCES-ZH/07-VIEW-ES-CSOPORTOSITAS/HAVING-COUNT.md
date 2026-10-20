# HAVING COUNT — önálló quick

**P0** · 11g

## 5 MÁSODPERCES FELISMERÉS

„Legalább / pontosan / több mint / kevesebb mint / legfeljebb N a **csoportban**” → HAVING COUNT + **helyes operátor**.

## Teljes SQL

```sql
SELECT <c>, COUNT(*) AS db
FROM   <t>
GROUP BY <c>
HAVING COUNT(*) <operator> <n>;
```

## Operátor tábla

| Szöveg | Operátor |
|--------|----------|
| kevesebb mint | `<` |
| legfeljebb | `<=` |
| pontosan | `=` |
| legalább | `>=` |
| több mint | `>` |

LEFT „nulla gyerek”: `COUNT(<jobb>.<pk>) = 0` — lásd JOIN 3 perc. **Ne** `COUNT(*)`.

## Placeholder — MIT ÍRJ / HONNAN VESZEM

| Helyőrző | MIT ÍRJ | HONNAN VESZEM |
|----------|---------|---------------|
| `<c>` | Csoportkulcs | **feladat** |
| `<n>` | Küszöb | **feladat** |
| `<operator>` | `<` `<=` `=` `>=` `>` | **feladat** — ne fix `>=` |

Canonical: [`README.md`](README.md)
