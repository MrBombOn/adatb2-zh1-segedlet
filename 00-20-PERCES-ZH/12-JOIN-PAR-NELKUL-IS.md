# JOIN – pár nélkül is + gondolkodási lánc

**20 perc · GYORS** · Részletes: [`07-JOIN/`](../07-JOIN/)

## Szinonimák
akkor is ha nincs / minden X / hiányzó kapcsolat / nincs neki Y

## LEFT JOIN
> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
SELECT <b>.<oszlopok>, <j>.<oszlopok>
FROM   <bal>  <b>
LEFT JOIN <jobb> <j> ON <j>.<fk> = <b>.<pk>
WHERE  <j>.<pk> IS NULL;   -- csak akiknek NINCS párjuk
```

## Kombinált gondolkodási lánc (AUTHOR / BOOK / LOAN)

```text
Mit kérnek?
  könyvek szerzővel?     → book JOIN author
  szerző könyv nélkül?   → author LEFT JOIN book WHERE book_id IS NULL
  nyitott kölcsön?       → loan WHERE returned_on IS NULL
  ki nem kölcsönzött?    → book LEFT JOIN nyitott_loan WHERE loan_id IS NULL
```

Ugyanez STUDENT/COURSE/ENROLLMENT-re:

```text
hallgató kurzusai → student JOIN enrollment JOIN course
nincs jelentkezés → student LEFT JOIN enrollment WHERE enrollment.student_id IS NULL
kurzusonként létszám → GROUP BY + COUNT
```
