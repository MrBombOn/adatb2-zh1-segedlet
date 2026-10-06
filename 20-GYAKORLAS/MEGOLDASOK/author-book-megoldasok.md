# AUTHOR / BOOK / LOAN — tanulási megoldások

> **TANULÁSI MEGOLDÁS – ZH alatt ne másold be.** Ezek a megoldások gyakorláshoz vannak; a ZH-n saját fejjel dolgozz.

## 1. Könyvek szerzővel

```sql
SELECT b.title, a.name
FROM   book b
JOIN   author a ON a.author_id = b.author_id;
```

## 3. Szerzőnkénti darab

```sql
SELECT a.name, COUNT(*) AS konyvek
FROM   author a
JOIN   book b ON b.author_id = a.author_id
GROUP BY a.name;
```

## 4. Nyitott kölcsönök

```sql
SELECT loan_id, book_id, borrower, loaned_on
FROM   loan
WHERE  returned_on IS NULL;
```

## 5. CASE státusz

```sql
SELECT loan_id,
       CASE
         WHEN returned_on IS NULL THEN 'NYITOTT'
         ELSE 'LEZART'
       END AS status
FROM   loan;
```

## 2. (ötlet)

Definiáld előbb, mit jelent a „nincs kölcsönözve”: pl. nincs olyan `loan` sor, ahol `returned_on IS NULL`.
LEFT JOIN + `WHERE loan.loan_id IS NULL`, vagy `NOT EXISTS` alkérdés.
