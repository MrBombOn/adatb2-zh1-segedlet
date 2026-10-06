# Gyorssegély – cheatsheet

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

## Top-N (Oracle)

```sql
SELECT … FETCH FIRST <n> ROWS ONLY;
-- vagy ROWNUM szűrés alkérdéssel (tananyag szerint)
```
