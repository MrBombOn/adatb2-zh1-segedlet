# Elsődleges kulcs (PRIMARY KEY)

## Egyszerű definíció
Oszlop(ok), amelyek egyértelműen azonosítják a sort; UNIQUE + NOT NULL.

## Óvodás magyarázat
Minden embernek van egyedi igazolványszáma a táblában.

## Technikai magyarázat
PRIMARY KEY constraint; összetett PK több oszlopból állhat.

## Mini példa
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
ALTER TABLE <tabla> ADD CONSTRAINT <nev> PRIMARY KEY (<oszlop>);
```

## Tipikus félreértés
PK nem „az egyetlen index”, és nem mindig egyetlen oszlop.

## ZH-felismerés
„Azonosítsd egyértelműen” → PK vagy UNIQUE.
