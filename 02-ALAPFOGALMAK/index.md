# Index

## Egyszerű definíció
Gyorsító struktúra a kereséshez / rendezéshez; nem az „igazi” adat másolata üzleti értelemben.

## Óvodás magyarázat
Mint a könyv tárgymutatója: nem kell végiglapozni.

## Technikai magyarázat
B-tree index gyakori; PK/UNIQUE automatikusan indexel.

## Mini példa
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
CREATE INDEX <nev> ON <tabla>(<oszlop>);
```

## Tipikus félreértés
Index ≠ UNIQUE constraint (bár UNIQUE indexet használ).

## ZH-felismerés
ZH-n ritkán kell CREATE INDEX, de értsd: miért gyorsabb a WHERE.
