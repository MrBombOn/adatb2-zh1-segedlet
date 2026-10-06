# ALTER TABLE

## MI EZ?
Meglévő tábla módosítása.

## MIKOR KELL?
„Adj oszlopot / constraintet”.

## HONNAN ISMEREM FEL?
Módosítás struktúrán.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
ALTER TABLE <tabla> ADD (<oszlop> <tipus>);
ALTER TABLE <tabla> ADD CONSTRAINT <nev> …;
ALTER TABLE <tabla> DROP COLUMN <oszlop>;
```

## MIT JELENT SORONKÉNT?
ADD / MODIFY / DROP változatok.

## TIPIKUS HIBA
NOT NULL új oszlopon meglévő soroknál.

## HOGYAN ELLENŐRZÖM?
user_constraints / DESC.

## ZH GYORS EMLÉKEZTETŐ
Már létező tábla → ALTER.
