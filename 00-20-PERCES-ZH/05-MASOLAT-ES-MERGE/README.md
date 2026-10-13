# Másolat (CTAS) és MERGE

**P0 · GYORS** · Oracle **11g / 11g R2 ONLY** · Kliens: **PL/SQL Developer**

## HOL TALÁLOM?

| Kell | Hol |
|------|-----|
| Szintaxis | ebben a README-ben → **MINIMÁLIS SZINTAXIS** |
| Nem értem a fogalmat | **RÉSZLETES MAGYARÁZAT** link + laikus definíció lent |
| Helyőrző mit írjak | **MIT ÍRHATOK** + **ÉRTÉKEK JELENTÉSE** |
| ORA hiba | lent + [`../20-ORA-HIBAK/`](../20-ORA-HIBAK/) |
| Feladatszöveg → mappa | [`../00-START/FELADATSZOVEG-INDEX.md`](../00-START/FELADATSZOVEG-INDEX.md) |

## MIT KÉR

CTAS WHERE 1=0 üres struktúra; MERGE = feltételes beszúrás/frissítés.

## MIRE GONDOLJ

CTAS NEM másolja megbízhatóan a constraint-eket → ALTER kellhet. MERGE ON feltétel kulcs.

**Laikus:** üres másolat ≈ amit a feladatszöveg magyarul kér; a SQL csak a pontos eszköz.

## MINIMÁLIS SZINTAXIS (11g)

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
CREATE TABLE <uj_tabla> AS
SELECT * FROM <forras_tabla>
WHERE 1 = 0;
-- + ALTER TABLE … ADD CONSTRAINT … ha kell

MERGE INTO <cel> c
USING <forras> f ON (c.<kulcs> = f.<kulcs>)
WHEN MATCHED THEN UPDATE SET c.<o> = f.<o>
WHEN NOT MATCHED THEN INSERT (<oszlopok>) VALUES (<ertekek>);
```

## MIT ÍRHATOK (helyőrzők)

| Helyőrző | Mit írj | Jelölés | Példa gondolat |
|----------|---------|---------|----------------|
| `<uj_tabla>` | Új üres tábla neve | KÖTELEZŐ | BOOK_ARCH / STUDENT_BAK |
| `<forras_tabla>` | Forrás | KÖTELEZŐ | BOOK |
| `<kulcs>` | Egyezés feltétele | KÖTELEZŐ | id / email |

## ÉRTÉKEK JELENTÉSE

| Érték / minta | Jelentés | Jelölés |
|---------------|----------|---------|
| `WHERE 1=0` | 0 sor, struktúra megmarad | **VALID** |
| `WHEN MATCHED / NOT MATCHED` | MERGE ágak | **VALID** |
| `CTAS constraint másolás` | Nem megbízható 1:1 | **FIGYELEM** |

Jelölés: **KÖTELEZŐ** = a feladat/szintaxis kéri · **VALID** = 11g-ben elfogadott · **TIPIKUS** = gyakori lab · **KÖRNYEZETFÜGGŐ** = a lab dönti el.

## PÉLDA FELADATSZÖVEG (alternatív entitások)

Világok: `AUTHOR/BOOK, STUDENT/COURSE, CITY/PERSON, CUSTOMER/ORDER, CAR/OWNER` — **NE** TERMEK/KATEGORIA kész megoldást másolj.

- „Készíts üres másolatot a COURSE-ról COURSE_EMPTY néven.”
- „Ha az ISBN már van, frissítsd az árat, különben vedd fel.”
- „Másold a PERSON struktúráját adat nélkül.”

## LÉPÉSEK NULLÁRÓL

1. CTAS 1=0
2. Ellenőrizd COUNT=0
3. Constraint ALTER ha kell
4. MERGE: írd meg az ON kulcsot
5. Teszt mindkét ágra fejben

## HA EZT ÍRJA

| Feladatszöveg | Teendő |
|---------------|--------|
| üres szerkezeti másolat / klón adat nélkül | CTAS WHERE 1=0 |
| ha létezik frissíts, különben… | MERGE |

## TIPIKUS HIBÁK

- CTAS után elfelejtett PK
- MERGE ON rossz kulcs
- USING forrás üres

## TIPIKUS ORA (ehhez a témához)

| Kód | Mit nézz |
|-----|----------|
| ORA-00942 | forrás/cél név |
| ORA-00904 | oszlop MERGE-ben |

## 10s ELLENŐRZÉS

- [ ] CTAS: COUNT(*)=0
- [ ] MERGE: matched és not matched ág is kell-e?

## RÉSZLETES MAGYARÁZAT

→ [`../../09-DML/merge.md`](../../09-DML/merge.md) · [`../../10-DDL/create-table.md`](../../10-DDL/create-table.md)

## KAPCSOLÓDÓ

- [`../04-ADATFELTOLTES/`](../04-ADATFELTOLTES/)
- [`../06-SZETVALOGATAS/`](../06-SZETVALOGATAS/)

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
site:docs.oracle.com Oracle 11g CREATE TABLE AS SELECT MERGE WHEN MATCHED syntax
```

```text
site:stackoverflow.com Oracle 11g CREATE TABLE AS SELECT MERGE WHEN MATCHED -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference CREATE TABLE AS SELECT MERGE WHEN MATCHED
```

```text
"Oracle 11g" CREATE TABLE AS SELECT MERGE WHEN MATCHED ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```
