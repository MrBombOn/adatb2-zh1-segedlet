# TRUNC(SYSDATE) — önálló quick

**P0** · 11g

## 5 MÁSODPERCES FELISMERÉS

„Mai nap / dátum **óra nélkül**” → `TRUNC(SYSDATE)`.

## Teljes SQL

```sql
SELECT TRUNC(SYSDATE) FROM dual;

SELECT * FROM <tabla>
WHERE  TRUNC(<date_oszlop>) = TRUNC(SYSDATE);

INSERT INTO <tabla> (<date_oszlop>) VALUES (TRUNC(SYSDATE));
```

## Placeholder — MIT ÍRJ / HONNAN VESZEM

| Helyőrző | MIT ÍRJ | HONNAN VESZEM |
|----------|---------|---------------|
| `<date_oszlop>` | Dátumoszlop neve | **feladat** |
| `TRUNC` | Napra vágás | **szabály** (SYSDATE egyenlőség idő miatt csapda) |

Canonical: [`README.md`](README.md)
