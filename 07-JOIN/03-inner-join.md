# INNER JOIN

## MI EZ?
Csak az összeillő sorpárok.

## MIKOR KELL?
Kapcsolódó adatok mindkét oldalon kellenek.

## HONNAN ISMEREM FEL?
„mindkettőben van”, „tartozik hozzá”.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT <oszlopok>
FROM   <bal>  <b>
JOIN   <jobb> <j> ON <j>.<fk> = <b>.<pk>;
```

## MIT JELENT SORONKÉNT?
ON feltétel = kapcsolókulcs.

## TIPIKUS HIBA
Rossz kulcs → Descartes / üres / duplikátum.

## HOGYAN ELLENŐRZÖM?
Sorok száma ≤ min? Nem mindig — 1:N szoroz.

## ZH GYORS EMLÉKEZTETŐ
Alapértelmezett „kapcsold össze” → INNER.
