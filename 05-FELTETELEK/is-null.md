# IS NULL / IS NOT NULL

## MI EZ?
NULL szűrés.

## MIKOR KELL?
„Nincs kitöltve”, „ismeretlen”.

## HONNAN ISMEREM FEL?
Hiányzó érték.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
WHERE <oszlop> IS NULL
WHERE <oszlop> IS NOT NULL
```

## MIT JELENT SORONKÉNT?
NULL-ra csak IS / IS NOT.

## TIPIKUS HIBA
`= NULL` → üres eredmény tipikusan.

## HOGYAN ELLENŐRZÖM?
INSERT után hagyj szándékos NULL sort tesztnek.

## ZH GYORS EMLÉKEZTETŐ
NULL szó a feladatban → IS NULL.
