# CREATE TABLE

## MI EZ?
Új tábla létrehozása.

## MIKOR KELL?
„Hozz létre táblát oszlopokkal…”.

## HONNAN ISMEREM FEL?
Új entitás / tábla.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
CREATE TABLE <tabla> (
  <oszlop1> <tipus> <megszoritasok>,
  <oszlop2> <tipus>,
  CONSTRAINT <nev> PRIMARY KEY (<oszlop1>)
);
```

## MIT JELENT SORONKÉNT?
Oszlopdefiníciók + táblaszintű constraint-ek.

## TIPIKUS HIBA
Fenntartott szó névként idézőjel nélkül.

## HOGYAN ELLENŐRZÖM?
DESC <tabla>;

## ZH GYORS EMLÉKEZTETŐ
Struktúra kell → DDL CREATE.
