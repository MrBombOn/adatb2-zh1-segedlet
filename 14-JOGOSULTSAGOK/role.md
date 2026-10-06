# ROLE

## MI EZ?
Jogok csomagja.

## MIKOR KELL?
Csoportos jogosultságkezelés.

## HONNAN ISMEREM FEL?
CREATE ROLE; GRANT jog TO role; GRANT role TO user.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
CREATE ROLE <szerep>;
GRANT SELECT ON <tabla> TO <szerep>;
GRANT <szerep> TO <user>;
```

## MIT JELENT SORONKÉNT?
Role egyszerűsíti az adminisztrációt.

## TIPIKUS HIBA
Közvetlen jog vs role keverése fejciben.

## HOGYAN ELLENŐRZÖM?
session_roles / szóbeli ellenőrzés tárgy szerint.

## ZH GYORS EMLÉKEZTETŐ
„Szerepkör” → ROLE.
