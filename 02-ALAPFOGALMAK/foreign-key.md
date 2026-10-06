# Idegen kulcs (FOREIGN KEY)

## Egyszerű definíció
Oszlop(ok), amelyek egy másik tábla PK/UNIQUE értékére hivatkoznak.

## Óvodás magyarázat
A kutya táblában ott van a gazdi azonosítója — így tudjuk, kihez tartozik.

## Technikai magyarázat
REFERENCES <szulo_tabla>(<oszlop>); kapcsolati épség (referential integrity).

## Mini példa
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
ALTER TABLE <gyerek> ADD CONSTRAINT <nev> FOREIGN KEY (<oszlop>) REFERENCES <szulo>(<oszlop>);
```

## Tipikus félreértés
FK nem automatikus JOIN — csak szabály. A JOIN-t neked kell írni.

## ZH-felismerés
„Tartozik valamihez” / „kapcsolódik” → FK + JOIN.
