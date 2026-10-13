# Tranzakció

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

COMMIT / ROLLBACK / SAVEPOINT.

## MIRE GONDOLJ

DML után tudatos véglegesítés. DDL gyakran implicit COMMIT.

**Laikus:** véglegesíts ≈ amit a feladatszöveg magyarul kér; a SQL csak a pontos eszköz.

## MINIMÁLIS SZINTAXIS (11g)

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
COMMIT;
ROLLBACK;
SAVEPOINT <nev>;
ROLLBACK TO <nev>;
```

## MIT ÍRHATOK (helyőrzők)

| Helyőrző | Mit írj | Jelölés | Példa gondolat |
|----------|---------|---------|----------------|
| `<nev>` | SAVEPOINT név | TIPIKUS | sp1 |

## ÉRTÉKEK JELENTÉSE

| Érték / minta | Jelentés | Jelölés |
|---------------|----------|---------|
| `COMMIT` | Véglegesít | **VALID** |
| `ROLLBACK` | Visszavon | **VALID** |
| `SAVEPOINT` | Köztes pont | **VALID** |

Jelölés: **KÖTELEZŐ** = a feladat/szintaxis kéri · **VALID** = 11g-ben elfogadott · **TIPIKUS** = gyakori lab · **KÖRNYEZETFÜGGŐ** = a lab dönti el.

## PÉLDA FELADATSZÖVEG (alternatív entitások)

Világok: `AUTHOR/BOOK, STUDENT/COURSE, CITY/PERSON, CUSTOMER/ORDER, CAR/OWNER` — **NE** TERMEK/KATEGORIA kész megoldást másolj.

- „Véglegesítsd a változtatásokat.”
- „Ha hiba, vonjad vissza.”
- „Jelölj savepointot az UPDATE előtt.”

## LÉPÉSEK NULLÁRÓL

1. DML
2. Ellenőrző SELECT
3. COMMIT vagy ROLLBACK

## HA EZT ÍRJA

| Feladatszöveg | Teendő |
|---------------|--------|
| véglegesíts / mentsd | COMMIT |
| vonjad vissza | ROLLBACK |

## TIPIKUS HIBÁK

- DDL után meglepetés COMMIT
- Elfelejtett COMMIT labban

## 10s ELLENŐRZÉS

- [ ] Mi az elvárt végállapot?
- [ ] Volt DDL közben?

## RÉSZLETES MAGYARÁZAT

→ [`../../12-TRANZAKCIOK/`](../../12-TRANZAKCIOK/)

## KAPCSOLÓDÓ

- [`../12-DML/`](../12-DML/)

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
site:docs.oracle.com Oracle 11g COMMIT ROLLBACK SAVEPOINT transaction syntax
```

```text
site:stackoverflow.com Oracle 11g COMMIT ROLLBACK SAVEPOINT transaction -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference COMMIT ROLLBACK SAVEPOINT transaction
```

```text
"Oracle 11g" COMMIT ROLLBACK SAVEPOINT transaction ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```
