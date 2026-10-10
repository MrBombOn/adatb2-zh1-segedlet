# Dátum alapján szétválogatás

**20 perc · GYORS**

## Magyar szinonimák
szétválogatás / más táblába ha dátum … / feltételes beszúrás több táblába

## INSERT FIRST (első igaz ág) vs INSERT ALL (minden igaz ág)
> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
INSERT FIRST
  WHEN <datum_oszlop> <  TO_DATE('<hatar1>', 'YYYY-MM-DD') THEN
    INTO <tabla_regi> (<oszlopok>) VALUES (<ertekek>)
  WHEN <datum_oszlop> >= TO_DATE('<hatar1>', 'YYYY-MM-DD') THEN
    INTO <tabla_uj>   (<oszlopok>) VALUES (<ertekek>)
SELECT <oszlopok>
FROM   <forras>;
```

```sql
INSERT ALL
  WHEN <feltetel_a> THEN INTO <tabla_a> VALUES (<…>)
  WHEN <feltetel_b> THEN INTO <tabla_b> VALUES (<…>)
SELECT …
FROM   <forras>;
```

## Tipikus hiba
Rossz TO_DATE maszk; FIRST/ALL keverése; forrás SELECT hiánya a végén.

## KERESÉS, HA ELAKADTAM

> **Figyelem:** Kerüld a MySQL / Postgres / SQL Server találatokat és a **12c+** megoldásokat (`FETCH FIRST`, `OFFSET … ROWS`, `IDENTITY`). Elsőbbség: hivatalos **Oracle 11g** dokumentáció.

Bemásolható keresők (5–10 mp):

```text
site:docs.oracle.com Oracle 11g INSERT FIRST INSERT ALL conditional multitable syntax
```

```text
site:stackoverflow.com Oracle 11g INSERT FIRST INSERT ALL conditional multitable -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference INSERT FIRST INSERT ALL conditional multitable
```

```text
"Oracle 11g" INSERT FIRST INSERT ALL conditional multitable ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```

```text
site:docs.oracle.com Oracle 11g multitable insert INSERT FIRST
```

