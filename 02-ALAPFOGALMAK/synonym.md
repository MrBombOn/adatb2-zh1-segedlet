# Synonym

## Egyszerű definíció
Másik objektumra mutató álnév.

## Óvodás magyarázat
Becenév, hogy ne kelljen hosszú sémanév.

## Technikai magyarázat
CREATE SYNONYM <alias> FOR <schema>.<objektum>;

## Mini példa
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
CREATE SYNONYM <alias> FOR <schema>.<tabla>;
```

## Tipikus félreértés
Synonym nem másolja az adatot.

## ZH-felismerés
„Rövidebb néven hívd” / más séma elérése egyszerűen → SYNONYM.
