# Case-insensitive LIKE — önálló quick

**P0** · 11g

## 5 MÁSODPERCES FELISMERÉS

„Kis-nagy betű mindegy / tartalmazza ignore case” → `UPPER`/`LOWER` mindkét oldalon.

## Teljes SQL

```sql
WHERE UPPER(<oszlop>) LIKE UPPER('%<minta>%')
```

## Placeholder — MIT ÍRJ / HONNAN VESZEM

| Helyőrző | MIT ÍRJ | HONNAN VESZEM |
|----------|---------|---------------|
| `<oszlop>` | Szöveges oszlop | **feladat** |
| `<minta>` | Keresett rész | **feladat** |
| `UPPER` mindkét oldal | Azonos függvény | **szabály** |

Canonical: [`README.md`](README.md)
