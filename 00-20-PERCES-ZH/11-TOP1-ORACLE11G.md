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

## KERESÉS, HA ELAKADTAM

> **Figyelem:** Kerüld a MySQL / Postgres / SQL Server találatokat és a **12c+** megoldásokat (`FETCH FIRST`, `OFFSET … ROWS`, `IDENTITY`). Elsőbbség: hivatalos **Oracle 11g** dokumentáció.

Bemásolható keresők (5–10 mp):

```text
site:docs.oracle.com Oracle 11g ROWNUM top N ORDER BY subquery syntax
```

```text
site:stackoverflow.com Oracle 11g ROWNUM top N ORDER BY subquery -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference ROWNUM top N ORDER BY subquery
```

```text
"Oracle 11g" ROWNUM top N ORDER BY subquery ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```

```text
site:docs.oracle.com Oracle 11g ROWNUM
```

