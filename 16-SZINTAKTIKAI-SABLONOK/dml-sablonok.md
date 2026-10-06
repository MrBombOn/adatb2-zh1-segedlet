# DML sablonok

> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
INSERT INTO <tabla> (<oszlopok>)
VALUES (<ertekek>);
```

```sql
UPDATE <tabla>
SET    <oszlop> = <ertek>
WHERE  <feltetel>;
```

```sql
DELETE FROM <tabla>
WHERE  <feltetel>;
```

```sql
MERGE INTO <cel> c
USING <forras> f ON (<c.kulcs> = <f.kulcs>)
WHEN MATCHED THEN UPDATE SET c.<oszlop> = f.<oszlop>
WHEN NOT MATCHED THEN INSERT (<oszlopok>) VALUES (<ertekek>);
```
