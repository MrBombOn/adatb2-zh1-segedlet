# MERGE – ha még nincs

**20 perc · GYORS réteg** · Részletes: [`09-DML/merge.md`](../09-DML/merge.md)

## Magyar szinonimák (feladatszöveg)
ha létezik frissítsd / ha nincs vedd fel / upsert / egyesíts

## MI KELL? (1 mondat)
MERGE INTO … USING … ON … WHEN MATCHED / NOT MATCHED.

## Kitöltendő szintaktikai minta
> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
MERGE INTO <cel> c
USING (
  SELECT <kulcs> AS kulcs, <ertek> AS ertek FROM dual
) f
ON (c.<kulcs_oszlop> = f.kulcs)
WHEN MATCHED THEN UPDATE SET c.<oszlop> = f.ertek
WHEN NOT MATCHED THEN INSERT (<kulcs_oszlop>, <oszlop>)
  VALUES (f.kulcs, f.ertek);
```

## TIPIKUS HIBA
ON feltétel több sort talál; rossz kulcs.

## ELLENŐRZÉS (10 mp)
Futtasd kétszer: második futás UPDATE ágat érintse.

## KERESÉS, HA ELAKADTAM

> **Figyelem:** Kerüld a MySQL / Postgres / SQL Server találatokat és a **12c+** megoldásokat (`FETCH FIRST`, `OFFSET … ROWS`, `IDENTITY`). Elsőbbség: hivatalos **Oracle 11g** dokumentáció.

Bemásolható keresők (5–10 mp):

```text
site:docs.oracle.com Oracle 11g MERGE INTO WHEN MATCHED WHEN NOT MATCHED syntax
```

```text
site:stackoverflow.com Oracle 11g MERGE INTO WHEN MATCHED WHEN NOT MATCHED -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference MERGE INTO WHEN MATCHED WHEN NOT MATCHED
```

```text
"Oracle 11g" MERGE INTO WHEN MATCHED WHEN NOT MATCHED ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```

```text
site:docs.oracle.com Oracle 11g MERGE statement
```

