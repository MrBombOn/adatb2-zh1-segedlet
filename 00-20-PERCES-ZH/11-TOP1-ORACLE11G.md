# Top-1 / Top-N — Oracle 11g

**20 perc · GYORS**

## TILOS ezen a tárgyon
`FETCH FIRST`, `OFFSET … ROWS`, `LIMIT`

## ROWNUM minta (rendezés után!)
> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
SELECT *
FROM (
  SELECT <oszlopok>
  FROM   <tabla>
  WHERE  <feltetel>
  ORDER BY <rendezo> DESC
)
WHERE ROWNUM <= 1;
```

## ROW_NUMBER minta (11g)
```sql
SELECT *
FROM (
  SELECT <oszlopok>,
         ROW_NUMBER() OVER (ORDER BY <rendezo> DESC) AS rn
  FROM   <tabla>
)
WHERE rn = 1;
```

## Tipikus hiba
`WHERE ROWNUM = 1` **ORDER BY előtt** ugyanazon a szinten → rossz „legjobb” sor.
