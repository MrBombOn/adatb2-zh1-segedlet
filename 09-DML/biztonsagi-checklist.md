# DML biztonsági checklist

ZH / gyakorlás előtt:

1. **Írtál WHERE-t?** UPDATE/DELETE nélkül az egész tábla veszélyben.
2. **Előtte SELECT** ugyanazzal a feltétellel — hány sor?
3. **Tranzakció:** tudod-e ROLLBACK-elni, ha elrontod?
4. **FK / UNIQUE / CHECK** — milyen constraint dobhat hibát?
5. **NULL / default** — mi kerül üres mezőbe?
6. **Ne commitolj vakon** gyakorló környezetben sem, ha még ellenőrzöl.
7. **Backup / gyakorló séma** — ne éles adat!

```sql
-- Tanulási példa – ne másold be ZH-megoldásként.
SELECT COUNT(*) FROM <tabla> WHERE <feltetel>;
-- csak ha a COUNT stimmel:
-- UPDATE / DELETE ...
```
