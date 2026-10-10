# CTAS – üres szerkezeti másolat

**20 perc · GYORS**

## Magyar szinonimák
másolat adat nélkül / üres tábla ugyanazzal a szerkezettel / klónozás struktúra

## Minta
> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
CREATE TABLE <uj_tabla> AS
SELECT *
FROM   <forras_tabla>
WHERE  1 = 0;
```

## FIGYELEM (constraint)
A `CREATE TABLE … AS SELECT` **nem másolja megbízhatóan** a PK/FK/CHECK constraint-eket ugyanúgy, mint a forrás.
Ha a feladat constraint-eket is vár az új táblán → `ALTER TABLE … ADD CONSTRAINT …` utána.

## Ellenőrzés
```sql
SELECT COUNT(*) FROM <uj_tabla>;  -- 0-t vársz
```

## KERESÉS, HA ELAKADTAM

> **Figyelem:** Kerüld a MySQL / Postgres / SQL Server találatokat és a **12c+** megoldásokat (`FETCH FIRST`, `OFFSET … ROWS`, `IDENTITY`). Elsőbbség: hivatalos **Oracle 11g** dokumentáció.

Bemásolható keresők (5–10 mp):

```text
site:docs.oracle.com Oracle 11g CREATE TABLE AS SELECT WHERE 1=0 syntax
```

```text
site:stackoverflow.com Oracle 11g CREATE TABLE AS SELECT WHERE 1=0 -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference CREATE TABLE AS SELECT WHERE 1=0
```

```text
"Oracle 11g" CREATE TABLE AS SELECT WHERE 1=0 ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```

```text
site:docs.oracle.com Oracle 11g CREATE TABLE AS subquery
```

