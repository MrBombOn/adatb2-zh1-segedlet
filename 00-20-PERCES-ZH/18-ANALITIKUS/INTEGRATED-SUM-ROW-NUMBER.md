# Integrated SUM + ROW_NUMBER — önálló quick

**P1** · 11g · egy sablon, **két mód**

## 5 MÁSODPERCES FELISMERÉS

„Csoportonként a leg… **és** minden sor / győztes mellett a csoport összege.”

**Először döntsd el:** minden sort akarod (összeggel), vagy csak a csoport elsőjét?

| Ha a feladat… | Mód |
|---------------|-----|
| Minden sor megmarad + mellé partíció-összeg (+ opcionális rang) | **MÓD A** — **NINCS** `WHERE rn = 1` |
| Csak a csoport legelső / győztes sora kell | **MÓD B** — külső SELECT + `WHERE rn = 1` |

## MÓD A — minden sor marad (NINCS `WHERE rn = 1`)

Használd, ha: „minden sor mellett a csoport összege / sorszáma” — **ne szűrj** `rn = 1`-re.

```sql
SELECT e.<oszlopok>,
       SUM(e.<n>) OVER (PARTITION BY e.<p>) AS part_sum,
       ROW_NUMBER() OVER (
         PARTITION BY e.<p>
         ORDER BY e.<r> DESC
       ) AS rn
FROM   <tabla> e;
-- NINCS külső WHERE rn = 1  →  minden eredeti sor megmarad
```

## MÓD B — csak csoport első (külső SELECT + `rn = 1`)

Használd, ha: „csoportonként csak a leg… sor” (+ mellette partíció-összeg).

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

## „Minden sor” vs „csoportonként csak első”

| Kérdés | Válasz |
|--------|--------|
| Minden bemeneti sor kell az eredményben? | **MÓD A** — ne írj `WHERE rn = 1` |
| Csak 1 sor / partíció (győztes)? | **MÓD B** — külső szűrés `rn = 1` |
| `rn` oszlop kell, de minden sor? | **MÓD A** — a `rn` megmarad, nincs szűrés |
| Tipikus hiba | MÓD A helyett MÓD B-t írni → **eltűnnek** a nem-első sorok |

## Placeholder — MIT ÍRJ / HONNAN VESZEM

| Helyőrző | MIT ÍRJ | HONNAN VESZEM |
|----------|---------|---------------|
| `<p>` | Partíció (dept/author) | **feladat** |
| `<r>` | Rangsor kulcs | **feladat** |
| `<n>` | Összegezendő szám | **feladat** |
| `rn = 1` | Csak MÓD B-ben | **tipikus** Top-1 / csoport-győztes |

**TILOS:** FETCH FIRST. Canonical: [`README.md`](README.md)
