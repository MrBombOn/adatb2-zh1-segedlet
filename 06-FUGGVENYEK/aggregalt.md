# Aggregált függvények (bevezető)

## MI EZ?
Sok sorból egy érték.

## MIKOR KELL?
Összeg, átlag, darab.

## HONNAN ISMEREM FEL?
COUNT/SUM/AVG/MIN/MAX — részletek GROUP BY fejezetben.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT COUNT(*), SUM(<szam_oszlop>), AVG(<szam_oszlop>)
FROM <tabla>
WHERE <feltetel>;
```

## MIT JELENT SORONKÉNT?
WHERE előbb szűr, aztán aggregál.

## TIPIKUS HIBA
SELECT-ben nem aggregált oszlop GROUP BY nélkül.

## HOGYAN ELLENŐRZÖM?
Sorok száma vs COUNT(col).

## ZH GYORS EMLÉKEZTETŐ
„Hány / összes / átlag” → aggregátum (+ GROUP BY ha bontás kell).
