# Gyakorlás: AUTHOR / BOOK / LOAN

> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
CREATE TABLE author (
  author_id NUMBER PRIMARY KEY,
  name      VARCHAR2(100) NOT NULL
);

CREATE TABLE book (
  book_id   NUMBER PRIMARY KEY,
  title     VARCHAR2(200) NOT NULL,
  author_id NUMBER REFERENCES author(author_id),
  published DATE
);

CREATE TABLE loan (
  loan_id   NUMBER PRIMARY KEY,
  book_id   NUMBER REFERENCES book(book_id),
  borrower  VARCHAR2(100) NOT NULL,
  loaned_on DATE NOT NULL,
  returned_on DATE
);
```

## Feladatok

1. Listázd a könyveket szerzőnévvel (JOIN).
2. Mely könyvek nincsenek kölcsönözve jelenleg? (`returned_on` logika / nincs nyitott loan — fogalmazd meg)
3. Szerzőnként hány könyv van?
4. A nem visszahozott kölcsönök listája (`returned_on IS NULL`).
5. CASE: ha `returned_on` NULL → 'NYITOTT', különben 'LEZART'.
