# SELECT sablonok

> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT <oszlopok>
FROM   <tabla>
WHERE  <feltetel>
ORDER BY <kifejezes> [ASC|DESC];
```

```sql
SELECT DISTINCT <oszlopok>
FROM   <tabla>;
```

```sql
SELECT <csoport>, COUNT(*)
FROM   <tabla>
WHERE  <sor_feltetel>
GROUP BY <csoport>
HAVING COUNT(*) >= <n>
ORDER BY COUNT(*) DESC;
```

```sql
SELECT <kifejezes>
FROM   dual;
```
