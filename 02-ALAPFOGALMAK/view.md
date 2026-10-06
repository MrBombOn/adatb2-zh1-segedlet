# Nézet (VIEW)

## Egyszerű definíció
Elmentett SELECT: logikai tábla, általában nem tárol külön adatot.

## Óvodás magyarázat
Mentett keresés, amit táblaként kérdezhetsz.

## Technikai magyarázat
CREATE VIEW … AS SELECT …; jogok és komplexitás elrejtése.

## Mini példa
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
CREATE VIEW <nezet> AS SELECT <oszlopok> FROM <tabla> WHERE <feltetel>;
```

## Tipikus félreértés
View frissíthetősége korlátozott (JOIN-os view gyakran nem updatable).

## ZH-felismerés
„Mutasd mindig így” / „egyszerűsítsd a lekérdezést” → VIEW.
