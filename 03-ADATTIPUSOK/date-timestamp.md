# DATE és TIMESTAMP

## MI EZ?
Időpont tárolása.

## MIKOR KELL?
Születésnap, jelentkezés ideje, határidő.

## HONNAN ISMEREM FEL?
DATE literál / SYSDATE / TO_DATE; formázás TO_CHAR.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT SYSDATE FROM dual;
SELECT TO_DATE('<datum_szoveg>', '<formatum>') FROM dual;
SELECT TO_CHAR(<date_oszlop>, '<formatum>') FROM dual;
```

## MIT JELENT SORONKÉNT?
- SYSDATE: szerver aktuális ideje
- TO_DATE: szöveg → dátum
- TO_CHAR: dátum → megjelenítő szöveg

## TIPIKUS HIBA
Rossz formátummaszk → ORA-01861. Dátumot stringként hasonlítasz formátum nélkül.

## HOGYAN ELLENŐRZÖM?
Mindig tudatos formátum (`YYYY-MM-DD` stb.).

## ZH GYORS EMLÉKEZTETŐ
Szűrés dátumra: TO_DATE vagy DATE literál; tartomány: >= nap eleje és < másnap.
