# Tárolt eljárás (stored procedure)

## Egyszerű definíció
Az adatbázisban tárolt PL/SQL programegység.

## Óvodás magyarázat
Előre megírt recept a szerveren.

## Technikai magyarázat
PROCEDURE / FUNCTION; paraméterek; BEGIN…END.

## Mini példa
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
CREATE OR REPLACE PROCEDURE <nev> (<param> <tipus>) AS
BEGIN
  NULL; -- helyőrző törzs
END;
```

## Tipikus félreértés
SQL ≠ PL/SQL. A ZH1 gyakran SQL-re fókuszál; járj utána a tárgykövetelménynek.

## ZH-felismerés
„Írj eljárást” → PL/SQL; „írd ki lekérdezéssel” → SQL SELECT.
