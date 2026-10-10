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
