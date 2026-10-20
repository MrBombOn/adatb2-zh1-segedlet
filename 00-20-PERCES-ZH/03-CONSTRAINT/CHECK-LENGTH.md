# CHECK LENGTH — önálló quick

**P0** · 11g

## 5 MÁSODPERCES FELISMERÉS

„Legalább N karakter / ne legyen rövidebb” → `CHECK (LENGTH(...) >= n)`.

## Teljes SQL

```sql
CONSTRAINT ck_<tabla>_<oszlop>_len CHECK (LENGTH(<oszlop>) >= <n>)
```

## Placeholder — MIT ÍRJ / HONNAN VESZEM

| Helyőrző | MIT ÍRJ | HONNAN VESZEM |
|----------|---------|---------------|
| `<n>` | Minimum hossz | **feladat** |
| `<oszlop>` | Név/cím/jelszó mező | **feladat** |
| `ck_…` | Constraint név | **tipikus** konvenció |

Canonical: [`README.md`](README.md)
