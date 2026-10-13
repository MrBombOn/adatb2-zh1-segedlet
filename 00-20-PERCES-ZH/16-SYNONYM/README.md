# Synonym

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

CREATE SYNONYM — álnév objektumra; nem másolja az adatot.

## MIRE GONDOLJ

Más séma elérése egyszerű néven; PUBLIC SYNONYM csak ha a feladat/jog engedi.

**Laikus:** álnév ≈ amit a feladatszöveg magyarul kér; a SQL csak a pontos eszköz.

## MINIMÁLIS SZINTAXIS (11g)

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
CREATE SYNONYM <alias> FOR <schema>.<objektum>;
-- CREATE PUBLIC SYNONYM <alias> FOR <schema>.<objektum>;  -- ha jog és feladat engedi
DROP SYNONYM <alias>;
```

## MIT ÍRHATOK (helyőrzők)

| Helyőrző | Mit írj | Jelölés | Példa gondolat |
|----------|---------|---------|----------------|
| `<alias>` | Rövid név | KÖTELEZŐ | books |
| `<schema>.<objektum>` | Cél | KÖTELEZŐ | lib.book |

## ÉRTÉKEK JELENTÉSE

| Érték / minta | Jelentés | Jelölés |
|---------------|----------|---------|
| `private synonym` | Saját sémában | **TIPIKUS** |
| `PUBLIC SYNONYM` | Közös név | **KÖRNYEZETFÜGGŐ / jog kell** |

Jelölés: **KÖTELEZŐ** = a feladat/szintaxis kéri · **VALID** = 11g-ben elfogadott · **TIPIKUS** = gyakori lab · **KÖRNYEZETFÜGGŐ** = a lab dönti el.

## PÉLDA FELADATSZÖVEG (alternatív entitások)

Világok: `AUTHOR/BOOK, STUDENT/COURSE, CITY/PERSON, CUSTOMER/ORDER, CAR/OWNER` — **NE** TERMEK/KATEGORIA kész megoldást másolj.

- „Hívd BOOK-ot BOOKS néven.”
- „Más séma COURSE táblája rövid néven.”

## LÉPÉSEK NULLÁRÓL

1. Célobjektum teljes neve
2. CREATE SYNONYM
3. SELECT az aliasról

## HA EZT ÍRJA

| Feladatszöveg | Teendő |
|---------------|--------|
| rövidebb néven hívd / álnév | CREATE SYNONYM |

## TIPIKUS HIBÁK

- Azt hinnéd, másolat az adat
- Nincs jog a célobjektumra

## TIPIKUS ORA (ehhez a témához)

| Kód | Mit nézz |
|-----|----------|
| ORA-00955 | name already used |
| ORA-01031 | privilege |

## 10s ELLENŐRZÉS

- [ ] SELECT aliasból működik?
- [ ] Nem vár adatmásolást

## RÉSZLETES MAGYARÁZAT

→ [`../../02-ALAPFOGALMAK/synonym.md`](../../02-ALAPFOGALMAK/synonym.md)

## KAPCSOLÓDÓ

- [`../14-JOGOSULTSAG/`](../14-JOGOSULTSAG/)

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
site:docs.oracle.com Oracle 11g CREATE SYNONYM PUBLIC SYNONYM syntax
```

```text
site:stackoverflow.com Oracle 11g CREATE SYNONYM PUBLIC SYNONYM -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference CREATE SYNONYM PUBLIC SYNONYM
```

```text
"Oracle 11g" CREATE SYNONYM PUBLIC SYNONYM ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```
