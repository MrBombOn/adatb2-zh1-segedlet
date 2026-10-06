# DUAL

## MI EZ?
Egysoros dummy tábla kifejezésekhez.

## MIKOR KELL?
„Számold ki”, „mi a SYSDATE”, függvénypróba tábla nélkül.

## HONNAN ISMEREM FEL?
SELECT kifejezés FROM dual.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT <kifejezes> FROM dual;
```

## MIT JELENT SORONKÉNT?
DUAL-nak egy sora van — ideális skalár kifejezéshez.

## TIPIKUS HIBA
Valódi tábla helyett DUAL-t használni, ha adatok kellenek — hiba.

## HOGYAN ELLENŐRZÖM?
Egy soros eredményt vársz.

## ZH GYORS EMLÉKEZTETŐ
Nincs FROM tábla a feladatban, csak kifejezés → DUAL.
