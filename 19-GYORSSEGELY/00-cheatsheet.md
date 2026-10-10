# Gyorssegély – cheatsheet

**Prioritás: P0** — P0=20 perces ZH kritikus · P1=fontos · P2=háttér

> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

## SELECT váz

```sql
SELECT … FROM … WHERE … GROUP BY … HAVING … ORDER BY …;
```

## JOIN

```sql
FROM a JOIN b ON b.fk = a.pk
FROM a LEFT JOIN b ON …
```

## NULL

```sql
IS NULL / IS NOT NULL / NVL(col, x)
```

## Dátum

```sql
TO_DATE('<szoveg>', '<maszk>')
TO_CHAR(<date>, '<maszk>')
SYSDATE
```

## Tranzakció

```sql
COMMIT;  ROLLBACK;  SAVEPOINT <nev>;
```

## Top-N (Oracle 11g)

```sql
SELECT *
FROM (
  SELECT <oszlopok>
  FROM   <tabla>
  ORDER BY <kifejezes> DESC
)
WHERE ROWNUM <= <n>;
```