# Adatbázisok 2 – Oracle / SQL ZH1 segédlet

Saját tanulási és **szintaktikai** segédlet. **Oracle Database 11g / 11g R2 ONLY.**  
Nem megoldásbank: placeholder minták és tanulási mini-példák. Nincs TERMEK/KATEGORIA kész megoldás.

**Repo:** https://github.com/MrBombOn/adatb2-zh1-segedlet

---

# 20 PERCES ZH – START ITT

**→ [`00-20-PERCES-ZH/00-START/README.md`](00-20-PERCES-ZH/00-START/README.md)**

Zero → megoldás: feladatszöveg → mappa → szintaxis → helyőrző → ellenőrzés.

## Gyors navigáció (feladatelvárás-mappák)

| # | Mappa | Mikor |
|---|-------|-------|
| 00 | [START](00-20-PERCES-ZH/00-START/) | Mindig először |
| 01 | [Séma / USER](00-20-PERCES-ZH/01-SEMA-USER/) | CREATE USER / GRANT / QUOTA |
| 02 | [Tábla](00-20-PERCES-ZH/02-TABLA-LETREHOZAS/) | CREATE TABLE |
| 03 | [Constraint](00-20-PERCES-ZH/03-CONSTRAINT/) | PK/FK/UK/CK/NN |
| 04 | [Adatfeltöltés](00-20-PERCES-ZH/04-ADATFELTOLTES/) | INSERT ALL |
| 05 | [Másolat / MERGE](00-20-PERCES-ZH/05-MASOLAT-ES-MERGE/) | CTAS / MERGE |
| 06 | [Szétválogatás](00-20-PERCES-ZH/06-SZETVALOGATAS/) | INSERT FIRST/ALL |
| 07 | [VIEW / GROUP](00-20-PERCES-ZH/07-VIEW-ES-CSOPORTOSITAS/) | Nézet + aggregálás |
| 08 | [JOIN](00-20-PERCES-ZH/08-JOIN-ES-KAPCSOLAT/) | INNER / LEFT |
| 09 | [Top-N / subquery](00-20-PERCES-ZH/09-TOP1-ES-SUBQUERY/) | ROWNUM (nem FETCH FIRST) |
| 10 | [WHERE](00-20-PERCES-ZH/10-WHERE-ES-SZURES/) | Szűrés |
| 11 | [Dátum](00-20-PERCES-ZH/11-DATUM/) | TO_DATE / TO_CHAR |
| 12–19 | DML…halmaz | P1/P2 |
| 20 | [ORA hibák](00-20-PERCES-ZH/20-ORA-HIBAK/) | Hibalista |
| 21 | [Kereső](00-20-PERCES-ZH/21-KERESOSEGED/) | Docs keresők |
| 22 | [Meglepetés](00-20-PERCES-ZH/22-MEGLEPETES-FELADAT/) | Döntési fa |
| 99 | [Master](00-20-PERCES-ZH/99-MASTER/) | Cheatsheet + szintaxis index |

### Indexek

- [`FELADATSZOVEG-INDEX.md`](00-20-PERCES-ZH/00-START/FELADATSZOVEG-INDEX.md)
- [`MIT-IRHATOK-IDE.md`](00-20-PERCES-ZH/00-START/MIT-IRHATOK-IDE.md)
- [`SZINTAXIS-INDEX.md`](00-20-PERCES-ZH/99-MASTER/SZINTAXIS-INDEX.md)
- [`COURSE-COVERAGE.md`](COURSE-COVERAGE.md)

Régi flat fájlnevek (`00-START-ITT.md` stb.) **redirect stubok** az új mappákra.

### Ha elakadtam – keresés

Minden GYORS README végén: **KERESÉS, HA ELAKADTAM**. Kezdd: [`00-START`](00-20-PERCES-ZH/00-START/).

Korábbi mintafelismerés: [`23-KORABBI-ZH-MINTAK/`](23-KORABBI-ZH-MINTAK/)  
Próba-ZH: [`20-GYAKORLAS/PROBA-ZH/`](20-GYAKORLAS/PROBA-ZH/)

---

## ZH szabályok

1. **Saját munka.** A ZH alatt csak azt írd, amit magad értessz.
2. **Ne másold be** a repo mintáit kész válaszként. `<helyőrző>` szándékos.
3. **Tanulási példa** blokkokat ne vidd be ZH-válaszként.
4. **Oracle 11g.** Nincs `LIMIT`, nincs `FETCH FIRST` / `OFFSET … ROWS`. Top-N: `ROWNUM` / `ROW_NUMBER()`.
5. **NULL:** `IS NULL` / `IS NOT NULL`, ne `= NULL`.
6. **DML után** tranzakció, ha kell: `COMMIT` / `ROLLBACK`.
7. **JOIN előtt** FK → PK.
8. **GROUP BY:** minden nem aggregált SELECT-oszlop a GROUP BY-ban.
9. **Constraint** hiba → olvasd az ORA kódot.
10. **Idő:** biztos pontok először.
11. **Névadás:** a feladatsor neveit használd.
12. **Teszt fejben:** hány sor? NULL? 1:N szorzás?

Kliens a gyakorláshoz: **PL/SQL Developer**.

---

## Három szint

| Szint | Hol | Mire |
|-------|-----|------|
| **GYORS** | `00-20-PERCES-ZH/` | 20 perces / pótzárthelyi |
| **KÖZEPES** | témák + `99-MASTER` | szintaxis + helyőrző |
| **RÉSZLETES** | `00-START-HERE/` … `22-ZH/` | tanulói magyarázat (P0/P1/P2) |

## Hol kezdjem? (tanuló út)

1. [`00-20-PERCES-ZH/00-START/`](00-20-PERCES-ZH/00-START/) ha ZH közel van  
2. [`00-START-HERE/`](00-START-HERE/) + [`01-KORNYEZET/`](01-KORNYEZET/)  
3. Témák sorrendben a feladatsor szerint  
4. [`20-GYAKORLAS/`](20-GYAKORLAS/) + próba-ZH  

## Licenc

Lásd [`LICENSE`](LICENSE). Referenciák: [`REFERENCES.md`](REFERENCES.md). Freeze megjegyzés: [`FREEZE.md`](FREEZE.md).
