# HAVING

## MI EZ?
Feltétel a már aggregált csoportokra.

## MIKOR KELL?
„Csak azok a kurzusok, ahol legalább 5 jelentkező”.

## HONNAN ISMEREM FEL?
Aggregátumra szűrés.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT <csoport_oszlop>, COUNT(*)
FROM   <tabla>
GROUP BY <csoport_oszlop>
HAVING COUNT(*) >= <n>;
```

## MIT JELENT SORONKÉNT?
WHERE sorokra; HAVING csoportokra.

## TIPIKUS HIBA
Aggregátum WHERE-ben.

## HOGYAN ELLENŐRZÖM?
Ugyanaz COUNT a SELECT-ben és HAVING-ben segít olvasni.

## ZH GYORS EMLÉKEZTETŐ
Számosság/összeg küszöb → HAVING.
