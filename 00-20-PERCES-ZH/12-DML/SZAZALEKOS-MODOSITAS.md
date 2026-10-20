# Százalékos UPDATE — önálló quick

**P0** · 11g

## 5 MÁSODPERCES FELISMERÉS

„Emeld/csökkentsd **N%-kal**” → szorzó `(1 ± n/100)`.

## Teljes SQL

```sql
UPDATE <tabla>
SET    <szam_oszlop> = <szam_oszlop> * (1 + <n> / 100)   -- emelés
-- SET <szam_oszlop> = <szam_oszlop> * (1 - <n> / 100)  -- csökkentés
WHERE  <feltetel>;
```

## Placeholder — MIT ÍRJ / HONNAN VESZEM

| Helyőrző | MIT ÍRJ | HONNAN VESZEM |
|----------|---------|---------------|
| `<n>` | Százalék szám (10, 15…) | **feladat** |
| `<szam_oszlop>` | Fizetés/ár/összeg | **feladat** |
| `<feltetel>` | Mely sorok | **feladat** (gyakorlatban kell) |

Canonical: [`README.md`](README.md)
