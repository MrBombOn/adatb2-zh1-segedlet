# DDL (ALTER / DROP)

**P1 · GYORS** · Oracle **11g / 11g R2 ONLY** · Kliens: **PL/SQL Developer**

## HOL TALÁLOM?

| Kell | Hol |
|------|-----|
| Szintaxis | ebben a README-ben → **MINIMÁLIS SZINTAXIS** |
| Nem értem a fogalmat | **RÉSZLETES MAGYARÁZAT** link + laikus definíció lent |
| Helyőrző mit írjak | **MIT ÍRHATOK** + **ÉRTÉKEK JELENTÉSE** |
| ORA hiba | lent + [`../20-ORA-HIBAK/`](../20-ORA-HIBAK/) |
| Feladatszöveg → mappa | [`../00-START/FELADATSZOVEG-INDEX.md`](../00-START/FELADATSZOVEG-INDEX.md) |

## MIT KÉR

ALTER TABLE / DROP / TRUNCATE — struktúra, nem sor-DML.

## MIRE GONDOLJ

DDL gyakran implicit COMMIT. DROP ≠ DELETE.

**Laikus:** módosítsd a szerkezetet ≈ amit a feladatszöveg magyarul kér; a SQL csak a pontos eszköz.

## MINIMÁLIS SZINTAXIS (11g)

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
ALTER TABLE <tabla> ADD (<oszlop> <tipus>);
ALTER TABLE <tabla> MODIFY (<oszlop> <tipus>);
ALTER TABLE <tabla> DROP COLUMN <oszlop>;
ALTER TABLE <tabla> ADD CONSTRAINT <nev> …;
DROP TABLE <tabla>;
TRUNCATE TABLE <tabla>;
```

## MIT ÍRHATOK (helyőrzők)

| Helyőrző | Mit írj | Jelölés | Példa gondolat |
|----------|---------|---------|----------------|
| `ADD/MODIFY/DROP COLUMN` | Szerkezetváltozás | KÖTELEZŐ a szöveg szerint | … |
| `DROP TABLE` | Objektum törlés | FIGYELEM | visszavonhatatlanabb modell |

## ÉRTÉKEK JELENTÉSE

| Érték / minta | Jelentés | Jelölés |
|---------------|----------|---------|
| `ALTER TABLE` | Szerkezet módosítás | **VALID** |
| `TRUNCATE` | Összes sor gyors törlés (DDL jelleg) | **VALID / FIGYELEM** |
| `DROP` | Objektum eltávolítás | **VALID / FIGYELEM** |

Jelölés: **KÖTELEZŐ** = a feladat/szintaxis kéri · **VALID** = 11g-ben elfogadott · **TIPIKUS** = gyakori lab · **KÖRNYEZETFÜGGŐ** = a lab dönti el.

## PÉLDA FELADATSZÖVEG (alternatív entitások)

Világok: `AUTHOR/BOOK, STUDENT/COURSE, CITY/PERSON, CUSTOMER/ORDER, CAR/OWNER` — **NE** TERMEK/KATEGORIA kész megoldást másolj.

- „Adj email oszlopot a STUDENT-hez.”
- „Töröld a temp táblát.”
- „Növeld a VARCHAR2 hosszt.”

## LÉPÉSEK NULLÁRÓL

1. Döntsd el: ADD / MODIFY / DROP / constraint
2. Futtasd ALTER-t
3. Dictionary ellenőrzés

## HA EZT ÍRJA

| Feladatszöveg | Teendő |
|---------------|--------|
| adj oszlopot / módosítsd a típust | ALTER TABLE |
| töröld a táblát | DROP TABLE |
| ürítsd ki teljesen (struktúra marad) | TRUNCATE vagy DELETE — olvasd a szöveget |

## TIPIKUS HIBÁK

- Implicit COMMIT meglepetés
- DROP helyett DELETE reflex fordítva

## TIPIKUS ORA (ehhez a témához)

| Kód | Mit nézz |
|-----|----------|
| ORA-01430 | column being added already exists |
| ORA-00942 | table does not exist |

## 10s ELLENŐRZÉS

- [ ] user_tab_columns friss?
- [ ] Constraint megvan?

## RÉSZLETES MAGYARÁZAT

→ [`../../10-DDL/`](../../10-DDL/)

## KAPCSOLÓDÓ

- [`../02-TABLA-LETREHOZAS/`](../02-TABLA-LETREHOZAS/)
- [`../03-CONSTRAINT/`](../03-CONSTRAINT/)

## KERESÉS

Lásd lent, vagy [`../21-KERESOSEGED/`](../21-KERESOSEGED/).



## ORACLE 11g VALIDÁCIÓ

| Kérdés | Válasz |
|--------|--------|
| Van FETCH FIRST / OFFSET ROWS / LIMIT a megoldásban? | **NO** (csak TILOS figyelmeztetésben OK) |
| Van IDENTITY / AUTO_INCREMENT? | **NO** → SEQUENCE |
| Top-N ROWNUM / ROW_NUMBER? | **YES** ha kell Top-N |
| Placeholder kitöltve a feladatsor neveivel? | **YES** kell |
| USER ≈ SCHEMA tudatos? | **YES** (nincs vak CREATE SCHEMA) |


## KERESÉS, HA ELAKADTAM

> **Figyelem:** Kerüld a MySQL / Postgres / SQL Server találatokat és a **12c+** megoldásokat (`FETCH FIRST`, `OFFSET … ROWS`, `IDENTITY`). Elsőbbség: hivatalos **Oracle 11g** dokumentáció.

Bemásolható keresők (5–10 mp):

```text
site:docs.oracle.com Oracle 11g ALTER TABLE DROP TRUNCATE syntax
```

```text
site:stackoverflow.com Oracle 11g ALTER TABLE DROP TRUNCATE -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference ALTER TABLE DROP TRUNCATE
```

```text
"Oracle 11g" ALTER TABLE DROP TRUNCATE ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```
