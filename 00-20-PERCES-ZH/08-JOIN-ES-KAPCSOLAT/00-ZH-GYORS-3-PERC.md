# 3 perc — JOIN (önálló quick)

**P0** · 11g · teljes váz ebben a fájlban

## 5 MÁSODPERCES FELISMERÉS

LEFT JOIN ha: *azokat is, amelyekhez még nem tartozik semmi* · *függetlenül a kapcsolattól* · *nulla kapcsolódó* · *hiányában is* · *akkor is ha nincs*.

## Teljes kitölthető SQL — nincs pár (IS NULL)

```sql
SELECT <bal>.<oszlopok>
FROM   <bal>
LEFT JOIN <jobb> ON <jobb>.<fk> = <bal>.<pk>
WHERE  <jobb>.<pk> IS NULL;
```

## Teljes kitölthető SQL — COUNT(right)=0

```sql
SELECT <bal>.<pk>, <bal>.<nev>, COUNT(<jobb>.<pk>) AS db
FROM   <bal>
LEFT JOIN <jobb> ON <jobb>.<fk> = <bal>.<pk>
GROUP BY <bal>.<pk>, <bal>.<nev>
HAVING COUNT(<jobb>.<pk>) = 0;
```

## Placeholder

| Helyőrző | MIT ÍRJ | HONNAN VESZEM |
|----------|---------|---------------|
| `<bal>` | Bal tábla | **feladat** táblanév |
| `<jobb>` | Kapcsolódó tábla | **feladat** |
| `<fk>` / `<pk>` | Kapcsoló oszlopok | **feladat** / séma |
| `COUNT(<jobb>.<pk>)` | Jobb kulcs — NEM `*` | **szabály** (NULL nem számít) |

**CSAPDA:** `COUNT(*)=0` LEFT után → hamis. Canonical: [`README.md`](README.md) ha elakadsz.
