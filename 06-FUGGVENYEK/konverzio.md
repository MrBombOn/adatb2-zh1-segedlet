# Konverziós függvények

## MI EZ?
Típusváltás.

## MIKOR KELL?
Formázott kiírás / beolvasás.

## HONNAN ISMEREM FEL?
TO_CHAR, TO_DATE, TO_NUMBER.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT TO_CHAR(<date_oszlop>, '<formatum>')
FROM <tabla>;
```

## MIT JELENT SORONKÉNT?
A formátummaszk része a szerződésnek.

## TIPIKUS HIBA
Maszk nélkül dátumszöveg.

## HOGYAN ELLENŐRZÖM?
Ugyanazzal a maszkkal oda-vissza.

## ZH GYORS EMLÉKEZTETŐ
Formátum a feladatban → TO_CHAR/TO_DATE.
