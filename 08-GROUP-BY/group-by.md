# GROUP BY

## MI EZ?
Sorok csoportokba rendezése közös érték szerint.

## MIKOR KELL?
„Kurzusonként”, „városonként az átlag”.

## HONNAN ISMEREM FEL?
Csoportonként / szerint / bontásban.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT <csoport_oszlop>, COUNT(*)
FROM   <tabla>
GROUP BY <csoport_oszlop>;
```

## MIT JELENT SORONKÉNT?
SELECT listán nem aggregált oszlop → GROUP BY-ban kell.

## TIPIKUS HIBA
Oszlop kimarad a GROUP BY-ból → ORA-00979.

## HOGYAN ELLENŐRZÖM?
Nézd: egy sor csoportkulcsonként.

## ZH GYORS EMLÉKEZTETŐ
„X-enként” → GROUP BY X.
