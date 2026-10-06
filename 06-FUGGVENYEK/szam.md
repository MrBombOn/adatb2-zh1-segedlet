# Számfüggvények

## MI EZ?
Numerikus számítás.

## MIKOR KELL?
Kerekítés, abszolút érték.

## HONNAN ISMEREM FEL?
ROUND, TRUNC, ABS, MOD…

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT ROUND(<szam>, <tizedes>), TRUNC(<szam>, <tizedes>), MOD(<a>, <b>)
FROM dual;
```

## MIT JELENT SORONKÉNT?
ROUND kerekít; TRUNC vág.

## TIPIKUS HIBA
Pénz kerekítésének üzleti szabályát ne keverd össze.

## HOGYAN ELLENŐRZÖM?
DUAL-on ismert értékkel.

## ZH GYORS EMLÉKEZTETŐ
„Kerekítsd” → ROUND/TRUNC.
