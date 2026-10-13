# Analitikus függvények

**P2 · GYORS** · Oracle **11g / 11g R2 ONLY** · Kliens: **PL/SQL Developer**

## HOL TALÁLOM?

| Kell | Hol |
|------|-----|
| Szintaxis | ebben a README-ben → **MINIMÁLIS SZINTAXIS** |
| Nem értem a fogalmat | **RÉSZLETES MAGYARÁZAT** link + laikus definíció lent |
| Helyőrző mit írjak | **MIT ÍRHATOK** + **ÉRTÉKEK JELENTÉSE** |
| ORA hiba | lent + [`../20-ORA-HIBAK/`](../20-ORA-HIBAK/) |
| Feladatszöveg → mappa | [`../00-START/FELADATSZOVEG-INDEX.md`](../00-START/FELADATSZOVEG-INDEX.md) |

## MIT KÉR

ROW_NUMBER / RANK / DENSE_RANK OVER (ORDER BY …).

## MIRE GONDOLJ

Analitikus ≠ GROUP BY (sorok megmaradnak). Top-N-hez is használható.

**Laikus:** sorszámozás ≈ amit a feladatszöveg magyarul kér; a SQL csak a pontos eszköz.

## MINIMÁLIS SZINTAXIS (11g)

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
SELECT <oszlopok>,
       ROW_NUMBER() OVER (ORDER BY <r> DESC) AS rn,
       RANK() OVER (ORDER BY <r> DESC) AS rk,
       DENSE_RANK() OVER (PARTITION BY <p> ORDER BY <r> DESC) AS dr
FROM <tabla>;
```

## MIT ÍRHATOK (helyőrzők)

| Helyőrző | Mit írj | Jelölés | Példa gondolat |
|----------|---------|---------|----------------|
| `ORDER BY <r>` | Rangsor kulcs | KÖTELEZŐ | score DESC |
| `PARTITION BY <p>` | Csoporton belüli rang | TIPIKUS | course_id |

## ÉRTÉKEK JELENTÉSE

| Érték / minta | Jelentés | Jelölés |
|---------------|----------|---------|
| `ROW_NUMBER()` | Egyedi sorszám | **VALID** |
| `RANK()` | Ugyanaz az érték → ugyanaz a rang, lyuk | **VALID** |
| `DENSE_RANK()` | Lyuk nélkül | **VALID** |

Jelölés: **KÖTELEZŐ** = a feladat/szintaxis kéri · **VALID** = 11g-ben elfogadott · **TIPIKUS** = gyakori lab · **KÖRNYEZETFÜGGŐ** = a lab dönti el.

## PÉLDA FELADATSZÖVEG (alternatív entitások)

Világok: `AUTHOR/BOOK, STUDENT/COURSE, CITY/PERSON, CUSTOMER/ORDER, CAR/OWNER` — **NE** TERMEK/KATEGORIA kész megoldást másolj.

- „Kurzusonként legjobb hallgató.”
- „Városonként 1. PERSON név szerint.”

## LÉPÉSEK NULLÁRÓL

1. ORDER BY / PARTITION
2. Külső szűrés rn=1 ha Top
3. Nincs FETCH FIRST

## HA EZT ÍRJA

| Feladatszöveg | Teendő |
|---------------|--------|
| sorszámozás / rang | ROW_NUMBER / RANK |
| csoportonként a leg… | PARTITION BY + rn=1 |

## TIPIKUS HIBÁK

- GROUP BY-jal összekeverés
- FETCH FIRST reflex

## 10s ELLENŐRZÉS

- [ ] PARTITION jó?
- [ ] Külső szűrés kell-e?

## RÉSZLETES MAGYARÁZAT

→ Top-N: [`../09-TOP1-ES-SUBQUERY/`](../09-TOP1-ES-SUBQUERY/)

## KAPCSOLÓDÓ

- [`../09-TOP1-ES-SUBQUERY/`](../09-TOP1-ES-SUBQUERY/)

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
site:docs.oracle.com Oracle 11g ROW_NUMBER RANK DENSE_RANK OVER PARTITION syntax
```

```text
site:stackoverflow.com Oracle 11g ROW_NUMBER RANK DENSE_RANK OVER PARTITION -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference ROW_NUMBER RANK DENSE_RANK OVER PARTITION
```

```text
"Oracle 11g" ROW_NUMBER RANK DENSE_RANK OVER PARTITION ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```
