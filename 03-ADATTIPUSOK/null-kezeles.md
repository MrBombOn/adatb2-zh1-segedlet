# NULL kezelés

## MI EZ?
Hiányzó értékek helyes kezelése.

## MIKOR KELL?
„Nincs jegy”, „nincs email”.

## HONNAN ISMEREM FEL?
IS NULL; NVL / NVL2 / COALESCE.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT * FROM <tabla> WHERE <oszlop> IS NULL;
SELECT NVL(<oszlop>, <helyettesito>) FROM <tabla>;
```

## MIT JELENT SORONKÉNT?
- IS NULL: szűrés
- NVL: megjelenítéskor / számoláskor helyettesít

## TIPIKUS HIBA
`= NULL` → nem jó. Aggregátumok NULL-t ignorálnak (COUNT(*) vs COUNT(col)).

## HOGYAN ELLENŐRZÖM?
Próbálj ki ismert NULL sorokat gyakorló adatban.

## ZH GYORS EMLÉKEZTETŐ
COUNT(*) számolja a sort; COUNT(col) csak a nem-NULL értékeket.
