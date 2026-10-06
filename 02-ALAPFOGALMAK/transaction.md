# Tranzakció

## Egyszerű definíció
Összetartozó műveletek egysége: vagy mind érvényes, vagy semmi.

## Óvodás magyarázat
Vagy mindkét átutalás megtörténik, vagy egyik sem.

## Technikai magyarázat
BEGIN (implicit) … COMMIT / ROLLBACK. ACID: Atomicity, Consistency, Isolation, Durability.

## Mini példa
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
UPDATE <tabla> SET <oszlop> = <ertek> WHERE <feltetel>;
COMMIT;
```

## Tipikus félreértés
SELECT is futhat tranzakcióban, de a DML az, amit visszavonhatsz ROLLBACK-kel.

## ZH-felismerés
„Visszavonható legyen” / „véglegesítsd” → tranzakció.
