# Típuskonverziók

## MI EZ?
Érték egyik típusból másikba.

## MIKOR KELL?
Szöveges dátum beolvasása; szám formázása.

## HONNAN ISMEREM FEL?
TO_CHAR, TO_NUMBER, TO_DATE.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT TO_NUMBER('<szam_szoveg>') FROM dual;
SELECT TO_CHAR(<szam>, '<formatum>') FROM dual;
SELECT TO_DATE('<datum_szoveg>', '<formatum>') FROM dual;
```

## MIT JELENT SORONKÉNT?
Explicit konverzió = te irányítod a formátumot.

## TIPIKUS HIBA
Implicit konverzióra hagyatkozni ZH-n kockázatos.

## HOGYAN ELLENŐRZÖM?
Ugyanarra az inputra írj TO_* függvényt formátummal.

## ZH GYORS EMLÉKEZTETŐ
Ha formátum van a feladatban, TO_CHAR/TO_DATE maszkkal.
