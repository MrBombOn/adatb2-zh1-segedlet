# Aggregált függvények részletesen

## MI EZ?
COUNT, SUM, AVG, MIN, MAX.

## MIKOR KELL?
Statisztika csoportokban vagy egész táblán.

## HONNAN ISMEREM FEL?
Hány / összes / átlag / min / max.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT
  COUNT(*)           AS darab,
  COUNT(<oszlop>)    AS nem_null_darab,
  SUM(<szam_oszlop>) AS osszeg,
  AVG(<szam_oszlop>) AS atlag,
  MIN(<oszlop>)      AS minimum,
  MAX(<oszlop>)      AS maximum
FROM <tabla>;
```

## MIT JELENT SORONKÉNT?
COUNT(*) sorokat számol; COUNT(col) nem-NULL értékeket.

## TIPIKUS HIBA
AVG-be szöveg; SUM NULL-okkal óvatosan (NVL).

## HOGYAN ELLENŐRZÖM?
Ismert kis adaton számold kézzel.

## ZH GYORS EMLÉKEZTETŐ
Ha bontás is kell → GROUP BY.
