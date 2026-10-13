# Séma / USER

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

Hozz létre felhasználót / adj jogot / állíts kvótát — Oracle-ben **USER ≈ SCHEMA**.

## MIRE GONDOLJ

Ne írj vak `CREATE SCHEMA`-t. Előbb user, aztán quota/tablespace (ha kell), aztán GRANT, aztán csatlakozás.

**Laikus:** user ≈ amit a feladatszöveg magyarul kér; a SQL csak a pontos eszköz.

## MINIMÁLIS SZINTAXIS (11g)

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
CREATE USER <user_nev> IDENTIFIED BY <jelszo>;

ALTER USER <user_nev> QUOTA <meret> ON <tablespace_nev>;
-- pl. QUOTA UNLIMITED ON <tablespace_nev>   (ha a lab engedi)

GRANT CREATE SESSION TO <user_nev>;
GRANT CREATE TABLE TO <user_nev>;
GRANT CREATE VIEW TO <user_nev>;
-- további jogok a feladat szerint
```

## MIT ÍRHATOK (helyőrzők)

| Helyőrző | Mit írj | Jelölés | Példa gondolat |
|----------|---------|---------|----------------|
| `<user_nev>` | Új user neve a feladatsorból | KÖTELEZŐ | pl. ZHUSER1 — a szövegből |
| `<jelszo>` | Identified by jelszó | KÖTELEZŐ | lab/feladat adja |
| `<tablespace_nev>` | Tablespace ahol kvóta kell | KÖRNYEZETFÜGGŐ | gyakran USERS, de NE vak kötelező |
| `<meret>` | Kvóta méret vagy UNLIMITED | VALID | 10M, 100M, UNLIMITED |

## ÉRTÉKEK JELENTÉSE

| Érték / minta | Jelentés | Jelölés |
|---------------|----------|---------|
| `CREATE SESSION` | Bejelentkezés joga | **KÖTELEZŐ tipikus ZH-n** |
| `CREATE TABLE` | Tábla létrehozás joga | **TIPIKUS** |
| `QUOTA … ON <ts>` | Helyfoglalás tablespace-en | **KÖRNYEZETFÜGGŐ** |
| `USERS` | Gyakori default tablespace név | **TIPIKUS / KÖRNYEZETFÜGGŐ** |

Jelölés: **KÖTELEZŐ** = a feladat/szintaxis kéri · **VALID** = 11g-ben elfogadott · **TIPIKUS** = gyakori lab · **KÖRNYEZETFÜGGŐ** = a lab dönti el.

## PÉLDA FELADATSZÖVEG (alternatív entitások)

Világok: `AUTHOR/BOOK, STUDENT/COURSE, CITY/PERSON, CUSTOMER/ORDER, CAR/OWNER` — **NE** TERMEK/KATEGORIA kész megoldást másolj.

- „Hozz létre egy STUDENT_ADM usert, tudjon csatlakozni és táblát létrehozni.”
- „Adj kvótát a CITY_APP usernek a lab tablespace-én.”
- „AUTHOR_WRITER user kapjon CREATE VIEW jogot.”

## LÉPÉSEK NULLÁRÓL

1. Privileged userrel (lab szerint) futtasd CREATE USER
2. Ha a feladat kéri: ALTER USER … QUOTA … ON <tablespace>
3. GRANT CREATE SESSION (+ CREATE TABLE / VIEW …)
4. PL/SQL Developer: új kapcsolat Username=<user_nev>
5. SELECT user FROM dual; majd próbálj CREATE TABLE-t

## HA EZT ÍRJA

| Feladatszöveg | Teendő |
|---------------|--------|
| hozz létre usert / felhasználót | CREATE USER |
| adj jogot / engedélyezd | GRANT … |
| kvóta / hely / tablespace | ALTER USER … QUOTA |
| séma | USER ≈ SCHEMA — ne CREATE SCHEMA reflex |

## TIPIKUS HIBÁK

- Vak CREATE SCHEMA (Oracle ZH-n generally USER)
- USERS tablespace hardkód kötelezőként (környezetfüggő)
- CREATE TABLE quota nélkül → ORA-01950
- Nincs CREATE SESSION → nem lép be

## TIPIKUS ORA (ehhez a témához)

| Kód | Mit nézz |
|-----|----------|
| ORA-01950 | no privileges on tablespace → QUOTA |
| ORA-01031 | insufficient privileges → GRANT |
| ORA-01017 | bad username/password |

## 10s ELLENŐRZÉS

- [ ] SELECT user FROM dual a céluserrel
- [ ] Van CREATE SESSION?
- [ ] Quota beállítva, ha táblát kell létrehozni?
- [ ] ORA-01950 → QUOTA; ORA-01031 → GRANT

## RÉSZLETES MAGYARÁZAT

→ [`../../01-KORNYEZET/06-schema-user.md`](../../01-KORNYEZET/06-schema-user.md) · [`../../14-JOGOSULTSAGOK/`](../../14-JOGOSULTSAGOK/) · [`../../02-ALAPFOGALMAK/schema.md`](../../02-ALAPFOGALMAK/schema.md)

## KAPCSOLÓDÓ

- [`../14-JOGOSULTSAG/`](../14-JOGOSULTSAG/)
- [`../02-TABLA-LETREHOZAS/`](../02-TABLA-LETREHOZAS/)

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
site:docs.oracle.com Oracle 11g CREATE USER GRANT QUOTA tablespace SCHEMA syntax
```

```text
site:stackoverflow.com Oracle 11g CREATE USER GRANT QUOTA tablespace SCHEMA -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference CREATE USER GRANT QUOTA tablespace SCHEMA
```

```text
"Oracle 11g" CREATE USER GRANT QUOTA tablespace SCHEMA ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```
