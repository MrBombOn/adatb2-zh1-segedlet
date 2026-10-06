# Sequence

## Egyszerű definíció
Számsorozat-generátor (pl. egyedi azonosítókhoz).

## Óvodás magyarázat
Automatikus sorszám-osztó.

## Technikai magyarázat
CREATE SEQUENCE …; NEXTVAL / CURRVAL.

## Mini példa
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT <seq_nev>.NEXTVAL FROM dual;
```

## Tipikus félreértés
Sequence nem rollbackelődik úgy, mint a táblasor — lyukak lehetnek a számokban.

## ZH-felismerés
„Generálj egyedi ID-t” → SEQUENCE (+ INSERT).
