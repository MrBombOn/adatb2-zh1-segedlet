# LEFT JOIN + COUNT(right.id) = 0 (nincs pár)

**P0 · GYORS** · 11g

> **Tanulási példa – ne másold be ZH-megoldásként.**

## Két helyes „nincs pár” minta

**A) LEFT + IS NULL** (egyszerű lista):

```sql
SELECT <bal>.*
FROM   <bal>
LEFT JOIN <jobb> ON <jobb>.<fk> = <bal>.<pk>
WHERE  <jobb>.<pk> IS NULL;
```

**B) GROUP + COUNT(right) = 0** (ha GROUP is kell):

```sql
SELECT <bal>.<pk>, <bal>.<nev>, COUNT(<jobb>.<pk>) AS db
FROM   <bal>
LEFT JOIN <jobb> ON <jobb>.<fk> = <bal>.<pk>
GROUP BY <bal>.<pk>, <bal>.<nev>
HAVING COUNT(<jobb>.<pk>) = 0;
```

## CSAPDA: COUNT(*) vs COUNT(right.id)

| Kifejezés | LEFT JOIN-nél „nincs pár” soron |
|-----------|----------------------------------|
| `COUNT(*)` | **1** (a bal sor létezik) — **NEM** jó „nincs pár” tesztre |
| `COUNT(<jobb>.<pk>)` | **0** (NULL-ok nem számítanak) — **ez** kell |

→ [`README.md`](README.md) · [`NINCS-PAR.md`](NINCS-PAR.md)
## Felismerő mondatok

| Mondat | Teendő |
|--------|--------|
| azokat is, amelyekhez még nem tartozik semmi | LEFT + IS NULL **vagy** HAVING COUNT(jobb.pk)=0 |
| minden rekord, függetlenül a kapcsolattól | LEFT JOIN (lista) |
| akkor is mutasd, ha nulla kapcsolódó rekordja van | LEFT; nulla → IS NULL / COUNT=0 |
| kapcsolódó rekord hiányában is | LEFT JOIN |
