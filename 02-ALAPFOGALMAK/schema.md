# Séma (schema)

## Egyszerű definíció
Egy felhasználó objektumainak névtere (táblák, nézetek, stb.).

## Óvodás magyarázat
A te fiókod a közös könyvtárban: ami a neved alatt van, az a sémád.

## Technikai magyarázat
Oracle: user ≈ schema. Objektumok: tables, views, indexes, sequences…

## Mini példa
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT table_name FROM user_tables;
```

## Tipikus félreértés
Séma ≠ tablespace. A tablespace tárolási hely; a séma logikai tulajdon.

## ZH-felismerés
„Más sémából olvasás” → owner.prefix vagy jog / synonym.
