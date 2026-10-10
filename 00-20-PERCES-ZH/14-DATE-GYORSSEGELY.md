# DATE gyorssegély

**20 perc · GYORS**

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
SELECT SYSDATE FROM dual;

SELECT TO_DATE('<szoveg>', 'YYYY-MM-DD') FROM dual;
SELECT TO_CHAR(<date_oszlop>, 'YYYY-MM-DD') FROM dual;

SELECT *
FROM   <tabla>
WHERE  <date_oszlop> >= TO_DATE('<tol>', 'YYYY-MM-DD')
  AND  <date_oszlop> <  TO_DATE('<ig>',  'YYYY-MM-DD');

SELECT ADD_MONTHS(<date_oszlop>, <n>) FROM <tabla>;
SELECT EXTRACT(YEAR FROM <date_oszlop>) FROM <tabla>;
```

## Tipikus hiba
Maszk nélkül hasonlítás; `=` NULL dátumra; ORA-01861.

## KERESÉS, HA ELAKADTAM

> **Figyelem:** Kerüld a MySQL / Postgres / SQL Server találatokat és a **12c+** megoldásokat (`FETCH FIRST`, `OFFSET … ROWS`, `IDENTITY`). Elsőbbség: hivatalos **Oracle 11g** dokumentáció.

Bemásolható keresők (5–10 mp):

```text
site:docs.oracle.com Oracle 11g TO_DATE TO_CHAR ADD_MONTHS SYSDATE syntax
```

```text
site:stackoverflow.com Oracle 11g TO_DATE TO_CHAR ADD_MONTHS SYSDATE -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference TO_DATE TO_CHAR ADD_MONTHS SYSDATE
```

```text
"Oracle 11g" TO_DATE TO_CHAR ADD_MONTHS SYSDATE ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```

```text
site:docs.oracle.com Oracle 11g datetime functions TO_DATE format model
```

