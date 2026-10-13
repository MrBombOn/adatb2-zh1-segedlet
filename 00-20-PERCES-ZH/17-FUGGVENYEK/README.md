# Függvények

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

Karakter/szám/NULL/CASE függvények a SELECT listában vagy WHERE-ben.

## MIRE GONDOLJ

NVL / NVL2 / COALESCE; CASE kifejezés; ne keverd dialektusokat.

**Laikus:** nagybetű ≈ amit a feladatszöveg magyarul kér; a SQL csak a pontos eszköz.

## MINIMÁLIS SZINTAXIS (11g)

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
SELECT UPPER(<o>), LOWER(<o>), SUBSTR(<o>,<k>,<h>), LENGTH(<o>) FROM <t>;
SELECT ROUND(<n>,<d>), TRUNC(<n>,<d>), MOD(<a>,<b>) FROM <t>;
SELECT NVL(<o>, <helyettes>) FROM <t>;
SELECT CASE WHEN <f> THEN <a> ELSE <b> END AS <alias> FROM <t>;
```

## MIT ÍRHATOK (helyőrzők)

| Helyőrző | Mit írj | Jelölés | Példa gondolat |
|----------|---------|---------|----------------|
| `NVL(<o>,<x>)` | NULL helyettes | TIPIKUS | NVL(phone,'N/A') |
| `SUBSTR` | Részstring | VALID | SUBSTR(name,1,3) |

## ÉRTÉKEK JELENTÉSE

| Érték / minta | Jelentés | Jelölés |
|---------------|----------|---------|
| `NVL` | 2 arg NULL kezelés | **VALID** |
| `CASE` | Feltételes kifejezés | **VALID** |
| `SELECT INTO` | PL/SQL — nem tiszta SQL SELECT ZH tipikusan | **FIGYELEM / ne keverd** |

Jelölés: **KÖTELEZŐ** = a feladat/szintaxis kéri · **VALID** = 11g-ben elfogadott · **TIPIKUS** = gyakori lab · **KÖRNYEZETFÜGGŐ** = a lab dönti el.

## PÉLDA FELADATSZÖVEG (alternatív entitások)

Világok: `AUTHOR/BOOK, STUDENT/COURSE, CITY/PERSON, CUSTOMER/ORDER, CAR/OWNER` — **NE** TERMEK/KATEGORIA kész megoldást másolj.

- „Ha nincs telefon, legyen N/A.”
- „Nevek nagybetűvel.”
- „Ár kerekítve.”

## LÉPÉSEK NULLÁRÓL

1. Melyik függvénycsalád?
2. Placeholder kitöltés
3. Teszt dual-on ha kell

## HA EZT ÍRJA

| Feladatszöveg | Teendő |
|---------------|--------|
| ha nincs legyen… | NVL / CASE |
| nagybetű / rész | UPPER / SUBSTR |

## TIPIKUS HIBÁK

- Dialektus keverés
- NVL rossz típus

## TIPIKUS ORA (ehhez a témához)

| Kód | Mit nézz |
|-----|----------|
| ORA-01722 | invalid number |

## 10s ELLENŐRZÉS

- [ ] NULL ág lefedve?
- [ ] Típus egyezik?

## RÉSZLETES MAGYARÁZAT

→ [`../../06-FUGGVENYEK/`](../../06-FUGGVENYEK/)

## KAPCSOLÓDÓ

- [`../11-DATUM/`](../11-DATUM/)
- [`../10-WHERE-ES-SZURES/`](../10-WHERE-ES-SZURES/)

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
site:docs.oracle.com Oracle 11g NVL UPPER SUBSTR ROUND CASE syntax
```

```text
site:stackoverflow.com Oracle 11g NVL UPPER SUBSTR ROUND CASE -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference NVL UPPER SUBSTR ROUND CASE
```

```text
"Oracle 11g" NVL UPPER SUBSTR ROUND CASE ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```
