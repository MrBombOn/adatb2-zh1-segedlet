# Tábla (table)

## Egyszerű definíció
Sorokból és oszlopokból álló alapvető adattároló objektum.

## Óvodás magyarázat
Excel-szerű rács, de szabályokkal (típus, kulcs, constraint).

## Technikai magyarázat
CREATE TABLE … ; minden sor egy rekord, minden oszlop egy attribútum.

## Mini példa
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
CREATE TABLE <tabla> (<oszlop> <tipus>);
```

## Tipikus félreértés
Tábla ≠ eredményhalmaz. A SELECT eredménye nem mentett tábla (hacsak nem CREATE TABLE AS).

## ZH-felismerés
Feladat „táblában tárold” → DDL + esetleg constraint.
