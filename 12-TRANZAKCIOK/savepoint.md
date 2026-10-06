# SAVEPOINT

## MI EZ?
Részleges visszagörgetési pont.

## MIKOR KELL?
„Eddig tartsd meg, a többit vond vissza”.

## HONNAN ISMEREM FEL?
Köztes pont.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SAVEPOINT <nev>;
-- műveletek
ROLLBACK TO <nev>;
```

## MIT JELENT SORONKÉNT?
ROLLBACK TO nem zárja feltétlenül a tranzakciót teljesen ugyanúgy minden esetben — tanuld a tárgy anyagát.

## TIPIKUS HIBA
Név elírása.

## HOGYAN ELLENŐRZÖM?
Két SAVEPOINT gyakorlás.

## ZH GYORS EMLÉKEZTETŐ
Összetett DML közben biztonsági pont.
