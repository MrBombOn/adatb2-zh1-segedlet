# Constraint

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

Szabály az adatokra: PK / FK / UK / CK / NN.

## MIRE GONDOLJ

Named constraint konvenció; FK csak létező szülő PK/UK-re.

**Laikus:** elsődleges kulcs ≈ amit a feladatszöveg magyarul kér; a SQL csak a pontos eszköz.

## MINIMÁLIS SZINTAXIS (11g)

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
CONSTRAINT pk_<tabla> PRIMARY KEY (<oszlop>)
CONSTRAINT fk_<gyerek>_<szulo> FOREIGN KEY (<oszlop>) REFERENCES <szulo>(<oszlop>)
CONSTRAINT uk_<tabla>_<oszlop> UNIQUE (<oszlop>)
CONSTRAINT ck_<tabla>_<oszlop> CHECK (<feltetel>)

ALTER TABLE <gyerek> ADD CONSTRAINT fk_<gyerek>_<szulo>
  FOREIGN KEY (<fk_oszlop>) REFERENCES <szulo>(<pk_oszlop>);
```

## MIT ÍRHATOK (helyőrzők)

| Helyőrző | Mit írj | Jelölés | Példa gondolat |
|----------|---------|---------|----------------|
| `pk_<tabla>` | PK név | TIPIKUS | pk_book |
| `fk_<gyerek>_<szulo>` | FK név | TIPIKUS | fk_book_author |
| `<feltetel>` | CHECK kifejezés | KÖTELEZŐ ha CHECK | price > 0 |

## ÉRTÉKEK JELENTÉSE

| Érték / minta | Jelentés | Jelölés |
|---------------|----------|---------|
| `PRIMARY KEY` | Egyedi azonosító + NOT NULL | **VALID** |
| `FOREIGN KEY` | Hivatkozás szülőre | **VALID** |
| `UNIQUE` | Egyedi, nem feltétlen PK | **VALID** |
| `CHECK` | Soron belüli feltétel | **VALID** |
| `NOT NULL` | Nem lehet üres | **VALID** |

Jelölés: **KÖTELEZŐ** = a feladat/szintaxis kéri · **VALID** = 11g-ben elfogadott · **TIPIKUS** = gyakori lab · **KÖRNYEZETFÜGGŐ** = a lab dönti el.

## PÉLDA FELADATSZÖVEG (alternatív entitások)

Világok: `AUTHOR/BOOK, STUDENT/COURSE, CITY/PERSON, CUSTOMER/ORDER, CAR/OWNER` — **NE** TERMEK/KATEGORIA kész megoldást másolj.

- „Az author_id hivatkozzon az AUTHOR.author_id-re.”
- „A plate_no legyen egyedi.”
- „A grade csak A–F között.”

## LÉPÉSEK NULLÁRÓL

1. Döntsd el: PK / FK / UK / CK / NN
2. Nevezd el (pk_/fk_/uk_/ck_)
3. CREATE TABLE-ben vagy ALTER TABLE ADD
4. FK előtt létezzen a szülő tábla

## HA EZT ÍRJA

| Feladatszöveg | Teendő |
|---------------|--------|
| elsődleges kulcs / azonosító | PRIMARY KEY |
| hivatkozzon / idegen kulcs | FOREIGN KEY |
| egyedi legyen | UNIQUE |
| ellenőrző feltétel / csak ezek az értékek | CHECK |
| kötelező / ne legyen üres | NOT NULL |

## TIPIKUS HIBÁK

- FK szülő nélkül
- CHECK idézőjelhiba
- Névütközés constraint-eknél

## TIPIKUS ORA (ehhez a témához)

| Kód | Mit nézz |
|-----|----------|
| ORA-00001 | unique/PK |
| ORA-02291 | parent key not found |
| ORA-02292 | child record found |
| ORA-01400 | cannot insert NULL |

## 10s ELLENŐRZÉS

- [ ] user_constraints
- [ ] Próbáld a sértő INSERT-et (tanulás)

## RÉSZLETES MAGYARÁZAT

→ [`../../11-CONSTRAINTS/`](../../11-CONSTRAINTS/)

## KAPCSOLÓDÓ

- [`../02-TABLA-LETREHOZAS/`](../02-TABLA-LETREHOZAS/)
- [`../08-JOIN-ES-KAPCSOLAT/`](../08-JOIN-ES-KAPCSOLAT/)

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
site:docs.oracle.com Oracle 11g PRIMARY KEY FOREIGN KEY UNIQUE CHECK NOT NULL constraint syntax
```

```text
site:stackoverflow.com Oracle 11g PRIMARY KEY FOREIGN KEY UNIQUE CHECK NOT NULL constraint -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference PRIMARY KEY FOREIGN KEY UNIQUE CHECK NOT NULL constraint
```

```text
"Oracle 11g" PRIMARY KEY FOREIGN KEY UNIQUE CHECK NOT NULL constraint ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```
