# GRANT és REVOKE

## MI EZ?
Jog adása / visszavonása.

## MIKOR KELL?
„Add meg a SELECT jogot…”.

## HONNAN ISMEREM FEL?
GRANT / REVOKE kulcsszavak.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
GRANT SELECT ON <tabla> TO <user_vagy_role>;
REVOKE SELECT ON <tabla> FROM <user_vagy_role>;
```

## MIT JELENT SORONKÉNT?
Objektumjog vs rendszerjog.

## TIPIKUS HIBA
Nincs jog → ORA-00942 vagy ORA-01031 jellegű helyzetek.

## HOGYAN ELLENŐRZÖM?
Más userrel próbáld a SELECT-et.

## ZH GYORS EMLÉKEZTETŐ
„Engedélyezd / vedd el” → GRANT/REVOKE.
