# JOIN sablonok

> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT <oszlopok>
FROM   <bal>  <b>
JOIN   <jobb> <j> ON <j>.<fk> = <b>.<pk>
WHERE  <feltetel>;
```

```sql
SELECT <oszlopok>
FROM   <bal>  <b>
LEFT JOIN <jobb> <j> ON <j>.<fk> = <b>.<pk>
WHERE  <j>.<pk> IS NULL;  -- nincs pár
```

```sql
SELECT <oszlopok>
FROM   <tabla> <a>
JOIN   <tabla> <b> ON <a>.<oszlop> = <b>.<oszlop>;  -- self
```
