# CROSS JOIN

## MI EZ?
Descartes-szorzat: minden mindennel.

## MIKOR KELL?
Kombinációk; ritkán szándékos.

## HONNAN ISMEREM FEL?
„minden párosítás”.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT <oszlopok>
FROM   <a> CROSS JOIN <b>;
```

## MIT JELENT SORONKÉNT?
Sorok: |A| * |B|.

## TIPIKUS HIBA
ON nélküli régi vesszős FROM véletlen CROSS.

## HOGYAN ELLENŐRZÖM?
Sorok száma = szorzat?

## ZH GYORS EMLÉKEZTETŐ
Ha robban a sorok száma, nézz JOIN feltételt.
