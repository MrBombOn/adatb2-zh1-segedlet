# Sor és oszlop

## Egyszerű definíció
Oszlop = mezőtípus; sor = egy konkrét előfordulás.

## Óvodás magyarázat
Oszlop: „keresztnév” felirat. Sor: „Anna” egy emberről.

## Technikai magyarázat
Relációs modell: tuple (sor), attribute (oszlop).

## Mini példa
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT <oszlop> FROM <tabla>; -- oszlopot választunk, sorokat szűrünk
```

## Tipikus félreértés
WHERE az oszlopokra ír feltételt, de sorokat szűr ki.

## ZH-felismerés
„Listázd az oszlopokat” vs „listázd a hallgatókat” — más SELECT lista / más szemcsézettség.
