# CASE kifejezés

## MI EZ?
Feltételes érték a SELECT listában (vagy máshol).

## MIKOR KELL?
„Ha … akkor … különben …”, kategorizálás.

## HONNAN ISMEREM FEL?
Elágazás SQL-ben.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT
  CASE
    WHEN <feltetel> THEN <ertek1>
    ELSE <ertek2>
  END AS <alias>
FROM <tabla>;
```

## MIT JELENT SORONKÉNT?
Searched CASE (WHEN feltétel) a leggyakoribb tanuláskor.

## TIPIKUS HIBA
END kihagyása szintaxis hiba.

## HOGYAN ELLENŐRZÖM?
Néhány sorra ellenőrizd a kategóriákat.

## ZH GYORS EMLÉKEZTETŐ
„Sorold kategóriába” → CASE.
