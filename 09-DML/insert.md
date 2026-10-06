# INSERT

## MI EZ?
Új sor hozzáadása.

## MIKOR KELL?
„Vegyél fel”, „illeszd be”.

## HONNAN ISMEREM FEL?
Új rekord.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
INSERT INTO <tabla> (<oszlopok>)
VALUES (<ertekek>);
```

## MIT JELENT SORONKÉNT?
Oszloplista ajánlott; sorrend = értékek sorrendje.

## TIPIKUS HIBA
NOT NULL / típus / FK sértés.

## HOGYAN ELLENŐRZÖM?
SELECT-tel ellenőrizd a beszúrt kulcsot.

## ZH GYORS EMLÉKEZTETŐ
Új sor → INSERT; sok sor SELECT-ből → INSERT … SELECT.
