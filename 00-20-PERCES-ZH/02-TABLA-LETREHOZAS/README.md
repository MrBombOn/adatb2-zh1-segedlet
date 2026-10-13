# Tábla létrehozás

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

CREATE TABLE + típusok + gyakran constraint-ek.

## MIRE GONDOLJ

Fogalom → típus: azonosító→NUMBER, név→VARCHAR2(n), dátum→DATE, igen/nem→CHAR(1)/VARCHAR2 vagy CHECK. ID: **SEQUENCE**, nem IDENTITY.

**Laikus:** tábla ≈ amit a feladatszöveg magyarul kér; a SQL csak a pontos eszköz.

## MINIMÁLIS SZINTAXIS (11g)

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
CREATE TABLE <tabla> (
  <id_oszlop>    NUMBER        NOT NULL,
  <nev_oszlop>   VARCHAR2(<n>) NOT NULL,
  <datum_oszlop> DATE,
  <szulo_id>     NUMBER,
  CONSTRAINT <pk_nev> PRIMARY KEY (<id_oszlop>)
);

CREATE SEQUENCE <seq_nev> START WITH 1 INCREMENT BY 1;
-- INSERT: <seq_nev>.NEXTVAL
```

## MIT ÍRHATOK (helyőrzők)

| Helyőrző | Mit írj | Jelölés | Példa gondolat |
|----------|---------|---------|----------------|
| `<tabla>` | Táblanév a feladatsorból | KÖTELEZŐ | BOOK, STUDENT, CAR… |
| `<id_oszlop>` | Azonosító oszlop | TIPIKUS | book_id / student_id |
| `<n>` | VARCHAR2 hossz | VALID | 50, 100, 255 — feladat szerint |
| `<seq_nev>` | Sequence név | TIPIKUS | seq_book / book_seq |

## ÉRTÉKEK JELENTÉSE

| Érték / minta | Jelentés | Jelölés |
|---------------|----------|---------|
| `NUMBER` | Szám / ID | **VALID** |
| `VARCHAR2(n)` | Változó hosszúságú szöveg | **VALID** |
| `DATE` | Dátum/idő | **VALID** |
| `SEQUENCE.NEXTVAL` | 11g ID generálás | **KÖTELEZŐ helyett IDENTITY** |
| `IDENTITY` | 12c+ — TILOS itt | **TILTOTT** |

Jelölés: **KÖTELEZŐ** = a feladat/szintaxis kéri · **VALID** = 11g-ben elfogadott · **TIPIKUS** = gyakori lab · **KÖRNYEZETFÜGGŐ** = a lab dönti el.

## PÉLDA FELADATSZÖVEG (alternatív entitások)

Világok: `AUTHOR/BOOK, STUDENT/COURSE, CITY/PERSON, CUSTOMER/ORDER, CAR/OWNER` — **NE** TERMEK/KATEGORIA kész megoldást másolj.

- „Hozd létre a BOOK táblát: book_id, title, author_id, published_on.”
- „STUDENT: student_id, name, birth_date kötelező névvel.”
- „CAR: plate_no egyedi, owner_id hivatkozás OWNER-re (constraint külön vagy itt).”

## LÉPÉSEK NULLÁRÓL

1. Olvasd az oszloplistát → fogalom→típus táblázat fejben
2. CREATE TABLE placeholder nevekkel a feladatsorból
3. PK / NOT NULL a szöveg szerint
4. Ha ID kell automatikusan: CREATE SEQUENCE
5. DESC / user_tab_columns ellenőrzés

## HA EZT ÍRJA

| Feladatszöveg | Teendő |
|---------------|--------|
| hozz létre táblát / oszlopok | CREATE TABLE |
| kötelező mező | NOT NULL |
| automatikus azonosító | SEQUENCE (nem IDENTITY) |

## TIPIKUS HIBÁK

- Fenntartott szó névként
- Hiányzó vessző
- IDENTITY használata
- VARCHAR2 hossz nélkül

## TIPIKUS ORA (ehhez a témához)

| Kód | Mit nézz |
|-----|----------|
| ORA-00942 | tábla/séma/jog |
| ORA-00904 | oszlopnév |
| ORA-12899 | value too large |

## 10s ELLENŐRZÉS

- [ ] user_tables-ben látszik?
- [ ] Próbáld az INSERT-et
- [ ] Nincs IDENTITY/FETCH FIRST

## RÉSZLETES MAGYARÁZAT

→ [`../../10-DDL/create-table.md`](../../10-DDL/create-table.md) · [`../../03-ADATTIPUSOK/`](../../03-ADATTIPUSOK/)

## KAPCSOLÓDÓ

- [`../03-CONSTRAINT/`](../03-CONSTRAINT/)
- [`../04-ADATFELTOLTES/`](../04-ADATFELTOLTES/)

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
site:docs.oracle.com Oracle 11g CREATE TABLE VARCHAR2 NUMBER DATE SEQUENCE syntax
```

```text
site:stackoverflow.com Oracle 11g CREATE TABLE VARCHAR2 NUMBER DATE SEQUENCE -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference CREATE TABLE VARCHAR2 NUMBER DATE SEQUENCE
```

```text
"Oracle 11g" CREATE TABLE VARCHAR2 NUMBER DATE SEQUENCE ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```
