# Jogosultság (GRANT / REVOKE)

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

System privilege (CREATE TABLE) vs object privilege (SELECT ON t).

## MIRE GONDOLJ

WITH ADMIN OPTION (rendszer) ≠ WITH GRANT OPTION (objektum). ORA-01031 → hiányzó jog.

**Laikus:** adj jogot ≈ amit a feladatszöveg magyarul kér; a SQL csak a pontos eszköz.

## MINIMÁLIS SZINTAXIS (11g)

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
GRANT CREATE SESSION TO <user_nev>;
GRANT CREATE TABLE TO <user_nev>;
GRANT SELECT, INSERT ON <schema>.<tabla> TO <user_nev>;
GRANT <role> TO <user_nev>;
REVOKE SELECT ON <schema>.<tabla> FROM <user_nev>;
-- object: WITH GRANT OPTION
-- system: WITH ADMIN OPTION
-- (csak ha a feladat kéri)
```

## MIT ÍRHATOK (helyőrzők)

| Helyőrző | Mit írj | Jelölés | Példa gondolat |
|----------|---------|---------|----------------|
| `system privilege` | CREATE SESSION/TABLE/VIEW… | TIPIKUS | … |
| `object privilege` | SELECT/INSERT/UPDATE/DELETE ON … | TIPIKUS | … |
| `WITH GRANT OPTION` | Továbbadható object jog | KÖRNYEZETFÜGGŐ | csak ha a feladat kéri |
| `WITH ADMIN OPTION` | Továbbadható system jog | KÖRNYEZETFÜGGŐ | csak ha a feladat kéri |

## ÉRTÉKEK JELENTÉSE

| Érték / minta | Jelentés | Jelölés |
|---------------|----------|---------|
| `GRANT` | Jog adás | **VALID** |
| `REVOKE` | Jog elvétel | **VALID** |
| `ROLE` | Jogcsomag | **VALID** |

Jelölés: **KÖTELEZŐ** = a feladat/szintaxis kéri · **VALID** = 11g-ben elfogadott · **TIPIKUS** = gyakori lab · **KÖRNYEZETFÜGGŐ** = a lab dönti el.

## PÉLDA FELADATSZÖVEG (alternatív entitások)

Világok: `AUTHOR/BOOK, STUDENT/COURSE, CITY/PERSON, CUSTOMER/ORDER, CAR/OWNER` — **NE** TERMEK/KATEGORIA kész megoldást másolj.

- „A REPORT user SELECT-elhessen a BOOK-on.”
- „Vond vissza az INSERT jogot.”
- „Adj CREATE VIEW-t.”

## LÉPÉSEK NULLÁRÓL

1. System vagy object?
2. GRANT lista
3. Teszt másik userrel
4. ORA-01031 → hiány

## HA EZT ÍRJA

| Feladatszöveg | Teendő |
|---------------|--------|
| adj jogot / engedélyezd | GRANT |
| vedd el a jogot | REVOKE |
| szerepkör | ROLE |

## TIPIKUS HIBÁK

- Object vs system összekeverése
- WITH GRANT vs WITH ADMIN

## TIPIKUS ORA (ehhez a témához)

| Kód | Mit nézz |
|-----|----------|
| ORA-01031 | insufficient privileges |
| ORA-00942 | table/view does not exist (vagy jog) |

## 10s ELLENŐRZÉS

- [ ] Más userrel SELECT működik?
- [ ] ORA-00942 lehet joghiány is

## RÉSZLETES MAGYARÁZAT

→ [`../../14-JOGOSULTSAGOK/`](../../14-JOGOSULTSAGOK/)

## KAPCSOLÓDÓ

- [`../01-SEMA-USER/`](../01-SEMA-USER/)

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
site:docs.oracle.com Oracle 11g GRANT REVOKE privilege ROLE WITH GRANT OPTION syntax
```

```text
site:stackoverflow.com Oracle 11g GRANT REVOKE privilege ROLE WITH GRANT OPTION -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference GRANT REVOKE privilege ROLE WITH GRANT OPTION
```

```text
"Oracle 11g" GRANT REVOKE privilege ROLE WITH GRANT OPTION ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```
