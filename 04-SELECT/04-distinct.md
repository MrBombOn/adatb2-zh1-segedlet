# DISTINCT

## MI EZ?
Ismétlődő eredmény-sorok kiszűrése.

## MIKOR KELL?
„Milyen különböző városok…”, „egyedi értékek”.

## HONNAN ISMEREM FEL?
Duplikátum, különböző, unique értékek listája.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT DISTINCT <oszlopok>
FROM   <tabla>;
```

## MIT JELENT SORONKÉNT?
A teljes kiválasztott sor-kombinációra érvényes.

## TIPIKUS HIBA
DISTINCT nem helyettesíti a GROUP BY aggregálást.

## HOGYAN ELLENŐRZÖM?
Duplikátum-e még mindig? Számold a sorokat DISTINCT nélkül/vel.

## ZH GYORS EMLÉKEZTETŐ
Csak egyediség kell listában → DISTINCT; összeg kell → GROUP BY.
