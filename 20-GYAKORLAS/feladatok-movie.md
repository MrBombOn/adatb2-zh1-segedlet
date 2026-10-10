# Feladatok — MOVIE/ACTOR/MOVIE_CAST

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

Összesen ebben a fájlban: **20** feladat.

## F081 · LEVEL 0
Listázd a movie címeket.

## F082 · LEVEL 0
Actor nevek UPPER-rel megjelenítve.

## F083 · LEVEL 1
JOIN movie–movie_cast–actor.

## F084 · LEVEL 1
INSERT actor + cast sor.

## F085 · LEVEL 2
GROUP BY: filmenkénti színészszám.

## F086 · LEVEL 2
LEFT: filmek szereplő nélkül.

## F087 · LEVEL 2
HAVING: filmek >= 3 színésszel.

## F088 · LEVEL 3
Subquery: színészek akik >= 2 filmben játszanak.

## F089 · LEVEL 3
INSERT ALL: 5 cast.

## F090 · LEVEL 3
MERGE: cast role_name frissítés.

## F091 · LEVEL 4
VIEW + LISTAGG színészek filmenként.

## F092 · LEVEL 4
Top-1 legtöbb szereplős film ROWNUM.

## F093 · LEVEL 0
DISTINCT role_name.

## F094 · LEVEL 1
UPDATE movie title.

## F095 · LEVEL 2
CASE: ha release_year < <év> → 'REGI'.

## F096 · LEVEL 3
CTAS üres movie_cast_arch.

## F097 · LEVEL 4
NOT EXISTS actor without cast.

## F098 · LEVEL 1
DELETE cast row.

## F099 · LEVEL 2
ORDER BY release_year.

## F100 · LEVEL 3
EXISTS movies with actor `<nev>`.
