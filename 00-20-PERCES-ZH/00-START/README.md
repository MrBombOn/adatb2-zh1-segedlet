# 20 PERCES ZH – START ITT

**Zero → megoldás navigáció** · Oracle **11g / 11g R2 ONLY** · PL/SQL Developer

> Statikus saját jegyzet. Nincs AI-utasítás ZH-n. Nincs TERMEK/KATEGORIA megoldásbank.

## 60 másodperces menet

1. Olvasd el az **egész** feladatsort egyszer  
2. Jelöld: DDL / DML / SELECT / JOIN / GROUP / dátum / Top-N  
3. Nyisd: [`FELADATSZOVEG-INDEX.md`](FELADATSZOVEG-INDEX.md) vagy [`MIT-KER-A-FELADAT.md`](MIT-KER-A-FELADAT.md)  
4. Írj **először** user/tábla/constraint, aztán adat, aztán lekérdezés  
5. Beadás előtt: ellenőrzőlista a témákban + [`../20-ORA-HIBAK/`](../20-ORA-HIBAK/)

## Oracle 11g emlékeztető

- Top-N: **ROWNUM** — **TILOS:** `FETCH FIRST`, `LIMIT`  
- ID: **SEQUENCE** — **TILOS:** `IDENTITY`  
- NULL: `IS NULL` — **TILOS:** `= NULL`

## Mappa térkép (feladatelvárás)

| # | Mappa | Mikor |
|---|-------|-------|
| 00 | [00-START](./) | Mindig először |
| 01 | [01-SEMA-USER](../01-SEMA-USER/) | user / séma / kvóta |
| 02 | [02-TABLA-LETREHOZAS](../02-TABLA-LETREHOZAS/) | CREATE TABLE |
| 03 | [03-CONSTRAINT](../03-CONSTRAINT/) | PK/FK/UK/CK/NN |
| 04 | [04-ADATFELTOLTES](../04-ADATFELTOLTES/) | INSERT |
| 05 | [05-MASOLAT-ES-MERGE](../05-MASOLAT-ES-MERGE/) | CTAS / MERGE |
| 06 | [06-SZETVALOGATAS](../06-SZETVALOGATAS/) | multitable INSERT |
| 07 | [07-VIEW-ES-CSOPORTOSITAS](../07-VIEW-ES-CSOPORTOSITAS/) | VIEW / GROUP / LISTAGG |
| 08 | [08-JOIN-ES-KAPCSOLAT](../08-JOIN-ES-KAPCSOLAT/) | JOIN / LEFT |
| 09 | [09-TOP1-ES-SUBQUERY](../09-TOP1-ES-SUBQUERY/) | Top-N / subquery |
| 10 | [10-WHERE-ES-SZURES](../10-WHERE-ES-SZURES/) | WHERE |
| 11 | [11-DATUM](../11-DATUM/) | dátum |
| 12–19 | DML…halmaz | P1/P2 tartalék |
| 20 | [20-ORA-HIBAK](../20-ORA-HIBAK/) | ORA |
| 21 | [21-KERESOSEGED](../21-KERESOSEGED/) | keresés |
| 22 | [22-MEGLEPETES-FELADAT](../22-MEGLEPETES-FELADAT/) | idegen szöveg |
| 99 | [99-MASTER](../99-MASTER/) | minden minta |

## Kötelező START fájlok

- [`MIT-KER-A-FELADAT.md`](MIT-KER-A-FELADAT.md)
- [`20-PERCES-MENET.md`](20-PERCES-MENET.md)
- [`HOL-KERESSEM.md`](HOL-KERESSEM.md)
- [`FELADATSZOVEG-INDEX.md`](FELADATSZOVEG-INDEX.md) (≥150 sor)
- [`MIT-IRHATOK-IDE.md`](MIT-IRHATOK-IDE.md)
- [`ZH-TECHNIKAI-MENET.md`](ZH-TECHNIKAI-MENET.md)
- [`FELADATONKENTI-MUNKAMENET.md`](FELADATONKENTI-MUNKAMENET.md)

## 3 szint

| Szint | Hol |
|-------|-----|
| GYORS | ez a `00-20-PERCES-ZH/` fa |
| KÖZEPES | témák README + master |
| RÉSZLETES | `01-KORNYEZET/` … `22-ZH/` tanulói réteg |

## KERESÉS, HA ELAKADTAM

> **Figyelem:** Kerüld a MySQL / Postgres / SQL Server találatokat és a **12c+** megoldásokat (`FETCH FIRST`, `OFFSET … ROWS`, `IDENTITY`). Elsőbbség: hivatalos **Oracle 11g** dokumentáció.

Bemásolható keresők (5–10 mp):

```text
site:docs.oracle.com Oracle 11g SQL SELECT JOIN CREATE TABLE syntax
```

```text
site:stackoverflow.com Oracle 11g SQL SELECT JOIN CREATE TABLE -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference SQL SELECT JOIN CREATE TABLE
```

```text
"Oracle 11g" SQL SELECT JOIN CREATE TABLE ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```
