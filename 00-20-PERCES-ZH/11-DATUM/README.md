# Dátum

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

TO_DATE / TO_CHAR / SYSDATE / ADD_MONTHS / EXTRACT.

## MIRE GONDOLJ

Maszk nélkül veszélyes. Összehasonlítás DATE-ként.

**Laikus:** dátum ≈ amit a feladatszöveg magyarul kér; a SQL csak a pontos eszköz.

## MINIMÁLIS SZINTAXIS (11g)

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
SELECT SYSDATE FROM dual;
SELECT TO_DATE('<szoveg>', 'YYYY-MM-DD') FROM dual;
SELECT TO_CHAR(<date_oszlop>, 'YYYY-MM-DD') FROM dual;
SELECT * FROM <tabla>
WHERE <date_oszlop> >= TO_DATE('<tol>', 'YYYY-MM-DD')
  AND <date_oszlop> <  TO_DATE('<ig>',  'YYYY-MM-DD');
SELECT ADD_MONTHS(<date_oszlop>, <n>) FROM <tabla>;
SELECT EXTRACT(YEAR FROM <date_oszlop>) FROM <tabla>;
```

## MIT ÍRHATOK (helyőrzők)

| Helyőrző | Mit írj | Jelölés | Példa gondolat |
|----------|---------|---------|----------------|
| `'YYYY-MM-DD'` | Maszk | TIPIKUS | vagy 'YYYY.MM.DD' feladat szerint |
| `<n>` | Hónap eltolás | VALID | 1, -3 |

## ÉRTÉKEK JELENTÉSE

| Érték / minta | Jelentés | Jelölés |
|---------------|----------|---------|
| `SYSDATE` | Aktuális dátum/idő DB szerint | **VALID** |
| `TO_DATE` | Szöveg → DATE | **KÖTELEZŐ literálnál gyakran** |
| `TO_CHAR` | DATE → szöveg | **VALID** |

Jelölés: **KÖTELEZŐ** = a feladat/szintaxis kéri · **VALID** = 11g-ben elfogadott · **TIPIKUS** = gyakori lab · **KÖRNYEZETFÜGGŐ** = a lab dönti el.

## PÉLDA FELADATSZÖVEG (alternatív entitások)

Világok: `AUTHOR/BOOK, STUDENT/COURSE, CITY/PERSON, CUSTOMER/ORDER, CAR/OWNER` — **NE** TERMEK/KATEGORIA kész megoldást másolj.

- „BOOK 2015 után.”
- „Formázd YYYY-MM-DD-re az ORDER dátumot.”
- „PERSON életkor év EXTRACT-tel.”

## LÉPÉSEK NULLÁRÓL

1. Literál? → TO_DATE maszkkal
2. Szűrés DATE tartomány
3. Formázás? → TO_CHAR
4. Ellenőrizz ORA-01861 ellen

## HA EZT ÍRJA

| Feladatszöveg | Teendő |
|---------------|--------|
| szövegből dátum | TO_DATE |
| formázott dátum | TO_CHAR |
| aktuális idő | SYSDATE |

## TIPIKUS HIBÁK

- Maszk nélkül
- = NULL dátumra
- ORA-01861

## TIPIKUS ORA (ehhez a témához)

| Kód | Mit nézz |
|-----|----------|
| ORA-01861 | literal does not match format |
| ORA-01858 | non-numeric character |

## 10s ELLENŐRZÉS

- [ ] Maszk egyezik a literállal?
- [ ] Tartomány felső határa < vagy <=?

## RÉSZLETES MAGYARÁZAT

→ [`../../03-ADATTIPUSOK/date-timestamp.md`](../../03-ADATTIPUSOK/date-timestamp.md) · [`../../06-FUGGVENYEK/datum.md`](../../06-FUGGVENYEK/datum.md)

## KAPCSOLÓDÓ

- [`../06-SZETVALOGATAS/`](../06-SZETVALOGATAS/)
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
site:docs.oracle.com Oracle 11g TO_DATE TO_CHAR SYSDATE ADD_MONTHS EXTRACT syntax
```

```text
site:stackoverflow.com Oracle 11g TO_DATE TO_CHAR SYSDATE ADD_MONTHS EXTRACT -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference TO_DATE TO_CHAR SYSDATE ADD_MONTHS EXTRACT
```

```text
"Oracle 11g" TO_DATE TO_CHAR SYSDATE ADD_MONTHS EXTRACT ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```
