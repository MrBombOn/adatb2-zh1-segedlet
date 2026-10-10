# Feladatok — CITY/PERSON

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

Összesen ebben a fájlban: **20** feladat.

## F041 · LEVEL 0
Listázd a `city` neveket.

## F042 · LEVEL 0
PERSON születési dátum szűrés TO_DATE-tel.

## F043 · LEVEL 1
JOIN: személy + városnév.

## F044 · LEVEL 1
INSERT 1 city + 1 person.

## F045 · LEVEL 2
LEFT: városok lakó nélkül.

## F046 · LEVEL 2
GROUP BY: városonkénti létszám.

## F047 · LEVEL 2
HAVING: városok ahol >= <n> személy.

## F048 · LEVEL 3
Subquery: személyek a legnagyobb létszámú városból.

## F049 · LEVEL 3
INSERT ALL: 5 person.

## F050 · LEVEL 3
MERGE: person email frissítés / insert kulcs alapján.

## F051 · LEVEL 4
VIEW: város + COUNT + LISTAGG(nevek).

## F052 · LEVEL 4
Top-1 város létszám szerint ROWNUM-mal.

## F053 · LEVEL 0
DISTINCT city_id a person táblából.

## F054 · LEVEL 1
UPDATE person city_id (FK figyelés).

## F055 · LEVEL 2
CASE: nagyváros ha létszám > <n> — aggregált nézetben.

## F056 · LEVEL 3
CTAS üres person_archive.

## F057 · LEVEL 4
NOT EXISTS: city without person.

## F058 · LEVEL 1
DELETE person WHERE <feltetel>.

## F059 · LEVEL 0
ORDER BY birth_date DESC.

## F060 · LEVEL 2
NULL email-ek IS NULL.
