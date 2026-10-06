# Frissíthető nézet

## MI EZ?
Bizonyos nézeteken DML is futhat.

## MIKOR KELL?
Egyszerű, egytáblás nézetek.

## HONNAN ISMEREM FEL?
INSERT/UPDATE nézeten.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
UPDATE <nezet> SET <oszlop> = <ertek> WHERE <feltetel>;
```

## MIT JELENT SORONKÉNT?
JOIN / aggregátum / DISTINCT gyakran nem updatable.

## TIPIKUS HIBA
Azt hinni, hogy minden view írható.

## HOGYAN ELLENŐRZÖM?
Próbálj UPDATE-et — ha ORA hiba, nem updatable.

## ZH GYORS EMLÉKEZTETŐ
ZH-n inkább CREATE VIEW + SELECT, hacsak nem kérik az írást.
