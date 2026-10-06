# Dátumfüggvények

## MI EZ?
Dátum számítás / részlet.

## MIKOR KELL?
Hozzáadás, különbség, részmező.

## HONNAN ISMEREM FEL?
ADD_MONTHS, MONTHS_BETWEEN, EXTRACT…

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT ADD_MONTHS(<date_oszlop>, <n>), EXTRACT(YEAR FROM <date_oszlop>)
FROM <tabla>;
```

## MIT JELENT SORONKÉNT?
DATE-hoz számot adni napokat jelenthet.

## TIPIKUS HIBA
Hónap vs nap keverése.

## HOGYAN ELLENŐRZÖM?
TO_CHAR-ral ellenőrizd az eredményt.

## ZH GYORS EMLÉKEZTETŐ
„Egy hónappal később” → ADD_MONTHS.
