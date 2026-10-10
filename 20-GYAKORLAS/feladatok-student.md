# Feladatok — STUDENT/COURSE/ENROLLMENT

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

Összesen ebben a fájlban: **20** feladat.

## F001 · LEVEL 0
Listázd a `student` tábla `full_name` és `email` oszlopát név szerint.

## F002 · LEVEL 0
Add meg azokat a kurzusokat, ahol `credits >= <kuszob>`.

## F003 · LEVEL 0
Szűrd a hallgatókat, akiknek az emailje `<minta>%` LIKE mintára illeszkedik.

## F004 · LEVEL 1
JOIN: hallgató név + kurzus cím az `enrollment` táblán keresztül egy `<course_id>`-re.

## F005 · LEVEL 1
INSERT: új hallgató `<id>`, `<nev>`, `<email>`, `<birth_date>`.

## F006 · LEVEL 1
UPDATE: egy hallgató emailje `<uj_email>`-re (előtte SELECT).

## F007 · LEVEL 2
LEFT JOIN: hallgatók, akiknek **nincs** enrollment sora.

## F008 · LEVEL 2
GROUP BY: kurzusonkénti jelentkezésszám.

## F009 · LEVEL 2
HAVING: csak kurzusok, ahol a jelentkezésszám >= 2.

## F010 · LEVEL 2
COUNT vs COUNT(grade): hány jelentkezésnek van jegye?

## F011 · LEVEL 3
Subquery: hallgatók, akik több kurzusra járnak, mint az átlagos jelentkezésszám.

## F012 · LEVEL 3
INSERT ALL: 5 enrollment sor egyszerre (érvényes FK-kkal).

## F013 · LEVEL 3
MERGE: ha a (student_id, course_id) létezik, frissítsd a `grade`-et; különben insert.

## F014 · LEVEL 3
CTAS: üres másolat `enrollment_arch` WHERE 1=0 + figyelmeztetés constraintekről.

## F015 · LEVEL 4
VIEW: kurzus cím + létszám + LISTAGG(hallgatónevek).

## F016 · LEVEL 4
Top-1 ROWNUM: a legtöbb kreditű kurzus címe.

## F017 · LEVEL 4
NOT EXISTS: kurzusok, amelyekre senki sem jelentkezett.

## F018 · LEVEL 1
DELETE: törölj egy enrollment sort adott kulccsal (előtte COUNT).

## F019 · LEVEL 2
CASE: grade NULL → 'NINCS', különben 'VAN'.

## F020 · LEVEL 0
DISTINCT: milyen különböző `grade` értékek vannak?
