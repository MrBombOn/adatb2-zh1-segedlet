# NULL

## Egyszerű definíció
Ismeretlen / hiányzó érték; nem üres string és nem nulla szám.

## Óvodás magyarázat
A mezőben nincs beírva semmi — nem tudjuk az értéket.

## Technikai magyarázat
Háromértékű logika: TRUE / FALSE / UNKNOWN. Összehasonlítás NULL-lal UNKNOWN.

## Mini példa
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT * FROM <tabla> WHERE <oszlop> IS NULL;
```

## Tipikus félreértés
`= NULL` nem működik a várt módon; `''` sem NULL Oracle-ben feltétlenül.

## ZH-felismerés
„Nincs kitöltve” / „hiányzik” → IS NULL.
