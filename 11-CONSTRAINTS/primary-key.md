# PRIMARY KEY constraint

## MI EZ?
Egyedi + nem NULL azonosító.

## MIKOR KELL?
„Elsődleges kulcs legyen…”.

## HONNAN ISMEREM FEL?
Azonosító oszlop(ok).

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
CONSTRAINT <nev> PRIMARY KEY (<oszlopok>)
```

## MIT JELENT SORONKÉNT?
Egy táblának egy PK-ja van (lehet összetett).

## TIPIKUS HIBA
NULL PK-ba.

## HOGYAN ELLENŐRZÖM?
user_constraints, user_cons_columns.

## ZH GYORS EMLÉKEZTETŐ
Egyedi azonosító → PK.
