# DELETE

## MI EZ?
Sorok törlése.

## MIKOR KELL?
„Töröld a sorokat, ahol…”.

## HONNAN ISMEREM FEL?
Törlés feltétellel.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
DELETE FROM <tabla>
WHERE  <feltetel>;
```

## MIT JELENT SORONKÉNT?
DELETE vs TRUNCATE: TRUNCATE DDL, más szabályokkal.

## TIPIKUS HIBA
WHERE nélküli DELETE.

## HOGYAN ELLENŐRZÖM?
Előtte SELECT COUNT(*) ugyanazzal a WHERE-rel.

## ZH GYORS EMLÉKEZTETŐ
FK gyerekek blokkolhatják a törlést.
