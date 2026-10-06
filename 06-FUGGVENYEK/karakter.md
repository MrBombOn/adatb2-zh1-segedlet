# Karakterfüggvények

## MI EZ?
Szövegmanipuláció.

## MIKOR KELL?
Nagybetű, darabolás, hossz.

## HONNAN ISMEREM FEL?
UPPER/LOWER/SUBSTR/LENGTH…

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT UPPER(<oszlop>), SUBSTR(<oszlop>, <kezdet>, <hossz>), LENGTH(<oszlop>)
FROM <tabla>;
```

## MIT JELENT SORONKÉNT?
Balról indexelés 1-től Oracle-ben.

## TIPIKUS HIBA
0-alapú indexelés feltételezése (más nyelvekből).

## HOGYAN ELLENŐRZÖM?
Próbáld DUAL-on.

## ZH GYORS EMLÉKEZTETŐ
„Nagybetűsen”, „első 3 karakter” → karakterfüggvény.
