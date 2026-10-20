# UPDATE + EXISTS — integrált önálló quick

**P0** · 11g · teljes váz ebben a fájlban

## 5 MÁSODPERCES FELISMERÉS

„Frissítsd **azokat, akiknek van** kapcsolódó rekordjuk / rendelésük / könyvük.”

## Teljes kitölthető SQL (EXISTS)

```sql
UPDATE <szulo> s
SET    <oszlop> = <uj_ertek>
WHERE  EXISTS (
  SELECT 1
  FROM   <gyerek> g
  WHERE  g.<fk> = s.<pk>
    AND  <opcionalis_feltetel>
);
```

## IN alt

```sql
UPDATE <szulo>
SET    <oszlop> = <uj_ertek>
WHERE  <pk> IN (SELECT <fk> FROM <gyerek> WHERE <feltetel>);
```

## Placeholder — MIT ÍRJ / HONNAN VESZEM

| Helyőrző | MIT ÍRJ | HONNAN VESZEM |
|----------|---------|---------------|
| `<szulo>` / `<gyerek>` | Táblák | **feladat** |
| `<oszlop>` / `<uj_ertek>` | Mit állítasz mire | **feladat** |
| `<fk>`=`<pk>` | Kapcsolat | **feladat**/séma |
| `<opcionalis_feltetel>` | Extra szűrés vagy 1=1 | **feladat** / **tipikus** |

Előtte: `SELECT COUNT(*) …`. Canonical: [`README.md`](README.md)
