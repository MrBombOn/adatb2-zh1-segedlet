# Halmazműveletek

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

UNION / UNION ALL / INTERSECT / MINUS.

## MIRE GONDOLJ

Oszlopszám és típuskompatibilitás. UNION deduplikál; UNION ALL nem.

**Laikus:** unió ≈ amit a feladatszöveg magyarul kér; a SQL csak a pontos eszköz.

## MINIMÁLIS SZINTAXIS (11g)

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
SELECT <o1>, <o2> FROM <t1>
UNION
SELECT <o1>, <o2> FROM <t2>;

SELECT … FROM <t1>
INTERSECT
SELECT … FROM <t2>;

SELECT … FROM <t1>
MINUS
SELECT … FROM <t2>;
```

## MIT ÍRHATOK (helyőrzők)

| Helyőrző | Mit írj | Jelölés | Példa gondolat |
|----------|---------|---------|----------------|
| `UNION vs UNION ALL` | Dedup vs mind | KÖTELEZŐ döntés | szöveg: „összes / duplikátumokkal” |

## ÉRTÉKEK JELENTÉSE

| Érték / minta | Jelentés | Jelölés |
|---------------|----------|---------|
| `UNION` | Egyesítés, egyedi | **VALID** |
| `UNION ALL` | Egyesítés, duplikátumokkal | **VALID** |
| `INTERSECT` | Metszet | **VALID** |
| `MINUS` | Különbség (Oracle) | **VALID** |

Jelölés: **KÖTELEZŐ** = a feladat/szintaxis kéri · **VALID** = 11g-ben elfogadott · **TIPIKUS** = gyakori lab · **KÖRNYEZETFÜGGŐ** = a lab dönti el.

## PÉLDA FELADATSZÖVEG (alternatív entitások)

Világok: `AUTHOR/BOOK, STUDENT/COURSE, CITY/PERSON, CUSTOMER/ORDER, CAR/OWNER` — **NE** TERMEK/KATEGORIA kész megoldást másolj.

- „STUDENT id-k akik COURSE A vagy B.” → UNION
- „Mindkét kurzuson.” → INTERSECT
- „A-n de nem B-n.” → MINUS

## LÉPÉSEK NULLÁRÓL

1. Oszlopok igazítása
2. Operátor választás
3. ORDER BY legvégén

## HA EZT ÍRJA

| Feladatszöveg | Teendő |
|---------------|--------|
| unió / vagy az egyik vagy a másik lista | UNION |
| metszet / mindkettőben | INTERSECT |
| különbség / az egyikben de nem a másikban | MINUS |

## TIPIKUS HIBÁK

- Oszlopszám eltérés
- EXCEPT (nem Oracle kulcsszó) — MINUS

## TIPIKUS ORA (ehhez a témához)

| Kód | Mit nézz |
|-----|----------|
| ORA-01789 | query block has incorrect number of result columns |

## 10s ELLENŐRZÉS

- [ ] Típusok passzolnak?
- [ ] UNION ALL kell-e?

## RÉSZLETES MAGYARÁZAT

→ [`../../04-SELECT/`](../../04-SELECT/)

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
site:docs.oracle.com Oracle 11g UNION UNION ALL INTERSECT MINUS syntax
```

```text
site:stackoverflow.com Oracle 11g UNION UNION ALL INTERSECT MINUS -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference UNION UNION ALL INTERSECT MINUS
```

```text
"Oracle 11g" UNION UNION ALL INTERSECT MINUS ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```
