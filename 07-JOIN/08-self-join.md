# SELF JOIN

## MI EZ?
Ugyanaz a tábla kétszer alias-szal.

## MIKOR KELL?
Hierarchia: főnök–beosztott; párkeresés.

## HONNAN ISMEREM FEL?
Ugyanarra a táblára hivatkozás.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT <oszlopok>
FROM   <tabla> <a>
JOIN   <tabla> <b> ON <a>.<oszlop> = <b>.<oszlop>;
```

## MIT JELENT SORONKÉNT?
Alias kötelező, különben névütközés.

## TIPIKUS HIBA
Alias nélküli self join.

## HOGYAN ELLENŐRZÖM?
Kis mintán ellenőrizd a párokat.

## ZH GYORS EMLÉKEZTETŐ
„Ugyanabból a táblából kapcsold” → SELF JOIN.
