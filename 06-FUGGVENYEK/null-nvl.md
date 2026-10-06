# NVL / NVL2 / COALESCE

## MI EZ?
NULL helyettesítés.

## MIKOR KELL?
Összegzésnél / megjelenítésnél hiányzó érték.

## HONNAN ISMEREM FEL?
„Ha nincs, legyen 0”.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT NVL(<oszlop>, <helyettesito>), COALESCE(<o1>, <o2>, <o3>)
FROM <tabla>;
```

## MIT JELENT SORONKÉNT?
NVL2(expr, ha_nem_null, ha_null).

## TIPIKUS HIBA
NULL aritmetika továbbra is NULL, ha nem kezeled.

## HOGYAN ELLENŐRZÖM?
Ismert NULL sor + helyettesítő.

## ZH GYORS EMLÉKEZTETŐ
„Hiányzó helyett írj X-et” → NVL/COALESCE.
