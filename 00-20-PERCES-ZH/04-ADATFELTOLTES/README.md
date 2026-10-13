# Adatfeltöltés (INSERT)

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

Sor(ok) beszúrása — 11g-n több sor: INSERT ALL … SELECT 1 FROM dual.

## MIRE GONDOLJ

Szülő sor előbb; oszlopszám = értékek száma; FK érték létezzen.

**Laikus:** vegyél fel ≈ amit a feladatszöveg magyarul kér; a SQL csak a pontos eszköz.

## MINIMÁLIS SZINTAXIS (11g)

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
INSERT INTO <tabla> (<o1>, <o2>) VALUES (<e1>, <e2>);

INSERT ALL
  INTO <tabla> (<o1>, <o2>) VALUES (<e1a>, <e2a>)
  INTO <tabla> (<o1>, <o2>) VALUES (<e1b>, <e2b>)
  INTO <tabla> (<o1>, <o2>) VALUES (<e1c>, <e2c>)
  INTO <tabla> (<o1>, <o2>) VALUES (<e1d>, <e2d>)
  INTO <tabla> (<o1>, <o2>) VALUES (<e1e>, <e2e>)
SELECT 1 FROM dual;
```

## MIT ÍRHATOK (helyőrzők)

| Helyőrző | Mit írj | Jelölés | Példa gondolat |
|----------|---------|---------|----------------|
| `<tabla>` | Céltábla | KÖTELEZŐ | COURSE / BOOK |
| `<o1>, <o2>` | Oszloplista | KÖTELEZŐ | feladatsor neveiből |
| `<e…>` | Literál / kifejezés / seq.NEXTVAL | KÖTELEZŐ | TO_DATE ha dátum |

## ÉRTÉKEK JELENTÉSE

| Érték / minta | Jelentés | Jelölés |
|---------------|----------|---------|
| `INSERT ALL … SELECT 1 FROM dual` | Több sor 11g-n | **VALID** |
| `MySQL multi-VALUES` | Nem ez a dialektus | **TILTOTT reflex** |
| `seq.NEXTVAL` | ID beszúrás | **TIPIKUS** |

Jelölés: **KÖTELEZŐ** = a feladat/szintaxis kéri · **VALID** = 11g-ben elfogadott · **TIPIKUS** = gyakori lab · **KÖRNYEZETFÜGGŐ** = a lab dönti el.

## PÉLDA FELADATSZÖVEG (alternatív entitások)

Világok: `AUTHOR/BOOK, STUDENT/COURSE, CITY/PERSON, CUSTOMER/ORDER, CAR/OWNER` — **NE** TERMEK/KATEGORIA kész megoldást másolj.

- „Vegyél fel 5 STUDENT sort egyszerre.”
- „Illeszd a BOOK táblába a megadott címeket.”
- „Töltsd fel az OWNER táblát legalább 3 sorral.”

## LÉPÉSEK NULLÁRÓL

1. Oszloplista felírása
2. Szülő INSERT előbb
3. INSERT vagy INSERT ALL
4. SELECT COUNT(*) ellenőrzés

## HA EZT ÍRJA

| Feladatszöveg | Teendő |
|---------------|--------|
| vegyél fel / új sor | INSERT |
| több sort egyszerre / 5 rekord | INSERT ALL |

## TIPIKUS HIBÁK

- MySQL VALUES (...),(...)
- FK sértés
- Elírt oszlopszám
- Dátum maszk nélkül

## TIPIKUS ORA (ehhez a témához)

| Kód | Mit nézz |
|-----|----------|
| ORA-02291 | FK szülő |
| ORA-00001 | unique |
| ORA-01400 | NULL |
| ORA-01861 | dátum |

## 10s ELLENŐRZÉS

- [ ] COUNT(*) elvárt?
- [ ] FK szülő létezik?
- [ ] Van SELECT 1 FROM dual az INSERT ALL végén?

## RÉSZLETES MAGYARÁZAT

→ [`../../09-DML/insert.md`](../../09-DML/insert.md)

## KAPCSOLÓDÓ

- [`../05-MASOLAT-ES-MERGE/`](../05-MASOLAT-ES-MERGE/)
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
site:docs.oracle.com Oracle 11g INSERT ALL SELECT FROM dual syntax
```

```text
site:stackoverflow.com Oracle 11g INSERT ALL SELECT FROM dual -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference INSERT ALL SELECT FROM dual
```

```text
"Oracle 11g" INSERT ALL SELECT FROM dual ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```
