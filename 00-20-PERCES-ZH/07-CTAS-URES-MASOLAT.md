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
