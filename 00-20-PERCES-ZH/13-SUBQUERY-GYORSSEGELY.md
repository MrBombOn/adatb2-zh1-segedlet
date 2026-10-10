# Subquery gyorssegély

**20 perc · GYORS réteg** · Részletes: [`04-SELECT/`](../04-SELECT/) + gyakorlás

## Magyar szinonimák (feladatszöveg)
azok akik / nagyobb mint az átlag / létezik olyan / nincs olyan

## MI KELL? (1 mondat)
SELECT a WHERE/FROM/SELECT listában másik SELECT-tel.

## Kitöltendő szintaktikai minta
> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
SELECT <oszlopok>
FROM   <tabla> t
WHERE  t.<szam> > (SELECT AVG(<szam>) FROM <tabla>)
   OR  t.<id> IN (SELECT <id> FROM <masik> WHERE <feltetel>)
   OR  EXISTS (SELECT 1 FROM <masik> m WHERE m.<fk> = t.<pk>);
```

## TIPIKUS HIBA
Több sort adó subquery `=` mellett; korreláció elrontása.

## ELLENŐRZÉS (10 mp)
Futtasd külön a belső SELECT-et.

## KERESÉS, HA ELAKADTAM

> **Figyelem:** Kerüld a MySQL / Postgres / SQL Server találatokat és a **12c+** megoldásokat (`FETCH FIRST`, `OFFSET … ROWS`, `IDENTITY`). Elsőbbség: hivatalos **Oracle 11g** dokumentáció.

Bemásolható keresők (5–10 mp):

```text
site:docs.oracle.com Oracle 11g subquery EXISTS IN correlated syntax
```

```text
site:stackoverflow.com Oracle 11g subquery EXISTS IN correlated -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference subquery EXISTS IN correlated
```

```text
"Oracle 11g" subquery EXISTS IN correlated ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```

```text
site:docs.oracle.com Oracle 11g subquery EXISTS
```

