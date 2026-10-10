# ZH szabályok – bővített

A rövid lista a `README.md` tetején van. Itt a magyarázat.

## 1. Saját munka
A segédlet **tanuláshoz** van. A vizsgán / ZH-n a saját megértésedet mérik.

## 2. Placeholder, nem kész válasz
```sql
SELECT <oszlopok> FROM <tabla> WHERE <feltetel>;
```
A `<…>` részeket **te** cseréled a feladathoz.

## 3. Oracle, nem más dialektus
- String összefűzés: `||` (nem `CONCAT` másképp / nem `+`)
- Top-N (**Oracle 11g**): `ROWNUM` vagy `ROW_NUMBER()` — **ne** `FETCH FIRST` / `LIMIT`
- Egyedi ID: `SEQUENCE` (+ szükség szerint trigger) — **ne** `IDENTITY` / `AUTO_INCREMENT`

## 4. NULL fegyelem
`WHERE col = NULL` **soha** nem az, amit akarsz. → `IS NULL`.

## 5. JOIN kulcs
Ha „együtt” kell két tábla adata: keresd a FK–PK kapcsolatot.

## 6. Aggregálás
`COUNT` / `SUM` / `AVG` mellett: GROUP BY + (szűrés csoportokra) HAVING.

## 7. Írás (DML)
INSERT/UPDATE/DELETE: gondold végig, **hány sor** változik; ha kell, tranzakció.

## 8. Időgazdálkodás
1) Mit kér? 2) Mely táblák? 3) Szűrés? 4) Összekapcsolás? 5) Csoportosítás?
