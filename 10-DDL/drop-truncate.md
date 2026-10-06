# DROP és TRUNCATE

## MI EZ?
DROP: objektum törlése. TRUNCATE: minden sor gyors ürítése.

## MIKOR KELL?
„Töröld a táblát” vs „ürítsd ki”.

## HONNAN ISMEREM FEL?
DROP TABLE; TRUNCATE TABLE;

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
DROP TABLE <tabla>;
TRUNCATE TABLE <tabla>;
```

## MIT JELENT SORONKÉNT?
TRUNCATE DDL; általában nem row-szintű undo mint DELETE.

## TIPIKUS HIBA
DROP véletlenül — praktika környezet!

## HOGYAN ELLENŐRZÖM?
user_tables listázása után.

## ZH GYORS EMLÉKEZTETŐ
Szerkezet eldobása → DROP; csak adat → DELETE vagy TRUNCATE (követelmény szerint).
