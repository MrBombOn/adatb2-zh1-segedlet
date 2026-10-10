# Feladatok — AUTHOR/BOOK/LOAN

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

Összesen ebben a fájlban: **20** feladat.

## F021 · LEVEL 0
Listázd az `author.name` értékeket ABC szerint.

## F022 · LEVEL 0
Könyvek, amelyek `published` dátuma >= TO_DATE(`<d>`, 'YYYY-MM-DD').

## F023 · LEVEL 1
JOIN: könyvcím + szerzőnév.

## F024 · LEVEL 1
INSERT: új author + book érvényes FK-val.

## F025 · LEVEL 2
LEFT: szerzők könyv nélkül.

## F026 · LEVEL 2
GROUP BY: szerzőnkénti könyvszám HAVING >= 2.

## F027 · LEVEL 2
Nyitott kölcsönök: `returned_on IS NULL`.

## F028 · LEVEL 3
Subquery: könyvek, amelyeket kölcsönöztek már (EXISTS).

## F029 · LEVEL 3
MERGE: kölcsön lezárása returned_on = SYSDATE ha loan_id egyezik.

## F030 · LEVEL 3
INSERT ALL: 5 book sor.

## F031 · LEVEL 4
VIEW + LISTAGG: szerzőnként a könyvcímek listája.

## F032 · LEVEL 4
Top-1: a legkorábban published könyv.

## F033 · LEVEL 4
Multitable ötlet: published előtt/után két archív táblába (INSERT FIRST minta).

## F034 · LEVEL 1
UPDATE: javíts egy book.title értéket.

## F035 · LEVEL 2
CASE loan státusz NYITOTT/LEZART.

## F036 · LEVEL 0
COUNT(*) a loan táblán.

## F037 · LEVEL 3
CTAS üres `loan_copy`.

## F038 · LEVEL 1
DELETE lezárt kölcsönök adott dátum előtt (WHERE!).

## F039 · LEVEL 2
JOIN lánc: author–book–loan borrower listázás.

## F040 · LEVEL 4
ROW_NUMBER: szerzőnként az első könyv published szerint.
