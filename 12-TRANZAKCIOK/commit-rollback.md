# COMMIT és ROLLBACK

## MI EZ?
Véglegesítés / visszavonás.

## MIKOR KELL?
„Mentsd el” / „vonjad vissza”.

## HONNAN ISMEREM FEL?
Tranzakció vége.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
UPDATE …;
COMMIT;
-- vagy
ROLLBACK;
```

## MIT JELENT SORONKÉNT?
COMMIT tartósít; ROLLBACK visszavon az utolsó véglegesítésig (egyszerű modell).

## TIPIKUS HIBA
DDL gyakran implicit COMMIT — óvatosan.

## HOGYAN ELLENŐRZÖM?
Módosíts, SELECT, ROLLBACK, SELECT újra.

## ZH GYORS EMLÉKEZTETŐ
DML után tudatos véglegesítés.
