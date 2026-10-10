# 20 PERCES ZH – START ITT

Egy képernyő. Ha csak ezt nyitod ki, tudj navigálni.

## 60 másodperces menet

1. Olvasd el az **egész** feladatsort egyszer  
2. Jelöld: DDL / DML / SELECT / JOIN / GROUP / dátum / Top-N  
3. Rajzold a **függőségi sorrendet** (`02-FUGGOSEGI-SORREND.md`)  
4. Írj **először** CREATE/GRANT/tábla/constraint, aztán adat, aztán lekérdezés  
5. Beadás előtt: `16-VEGSO-ELLENORZES.md`

## Oracle 11g emlékeztető

- Top-N: **ROWNUM** (alkérdésben) — **TILOS:** `FETCH FIRST`, `LIMIT`  
- ID: **SEQUENCE** — **TILOS:** `IDENTITY`, `AUTO_INCREMENT`  
- Kliens gyakorláshoz: **PL/SQL Developer**

## Hol melyik lap?

| Ha ezt látod a feladatban… | Nyisd |
|----------------------------|-------|
| user / séma / jog / kvóta | `03-SEMA-USER.md` |
| hozz létre táblát | `04-TABLA-LETREHOZAS.md` |
| PK / FK / UNIQUE / CHECK | `05-CONSTRAINT-GYORSVALASZTO.md` |
| több sor beszúrása egyszerre | `06-INSERT-5-REKORD-EGYSZERRE.md` |
| üres másolat struktúrával | `07-CTAS-URES-MASOLAT.md` |
| ha nincs, vedd fel / ha van, frissíts | `08-MERGE-HA-MEG-NINCS.md` |
| dátum szerint más táblába | `09-DATUM-ALAPJAN-SZETVALOGATAS.md` |
| nézet + csoport + listázás | `10-VIEW-GROUP-LISTAGG.md` |
| legjobb / első / top 1 | `11-TOP1-ORACLE11G.md` |
| akkor is, ha nincs pár | `12-JOIN-PAR-NELKUL-IS.md` |
| alkérdés / „azok akik” | `13-SUBQUERY-GYORSSEGELY.md` |
| dátum / hónap / formátum | `14-DATE-GYORSSEGELY.md` |
| ORA-xxxxx | `15-ORA-HIBAK-20-PERC.md` |
| teljesen idegen szöveg | `18-HA-TELJESEN-MAS-FELADAT-JON.md` |
| minden minta egyben | `99-MASTER-CHEATSHEET.md` |

---

## HA EZT LÁTOD → EZT CSINÁLD (≥50 sor)

| # | Feladatszöveg-minta / szinonima | Teendő | Lap |
|---|--------------------------------|--------|-----|
| 1 | listázd / mutasd / add vissza | SELECT | 01, 99 |
| 2 | csak azok / ahol / feltéve | WHERE | 01 |
| 3 | csökkenő / növekvő / ABC | ORDER BY | 99 |
| 4 | különböző / egyedi értékek | DISTINCT vagy UNIQUE | 05 |
| 5 | tartozik / együtt / neve és… | JOIN | 12 |
| 6 | akkor is ha nincs / hiányzik a pár | LEFT JOIN | 12 |
| 7 | X-enként / csoportonként | GROUP BY | 10 |
| 8 | legalább N a csoportban | HAVING | 10 |
| 9 | hány / összeg / átlag | COUNT/SUM/AVG | 10 |
| 10 | vedd fel / új sor | INSERT | 06 |
| 11 | több sort egyszerre | INSERT ALL | 06 |
| 12 | módosítsd | UPDATE | 99 |
| 13 | töröld a sorokat | DELETE | 99 |
| 14 | ha létezik frissíts, különben… | MERGE | 08 |
| 15 | hozz létre táblát | CREATE TABLE | 04 |
| 16 | elsődleges kulcs | PRIMARY KEY | 05 |
| 17 | hivatkozzon / idegen kulcs | FOREIGN KEY | 05 |
| 18 | egyedi legyen | UNIQUE | 05 |
| 19 | kötelező mező | NOT NULL | 05 |
| 20 | ellenőrző feltétel | CHECK | 05 |
| 21 | hozz létre usert | CREATE USER | 03 |
| 22 | adj jogot | GRANT | 03 |
| 23 | kvóta / tablespace | QUOTA | 03 |
| 24 | üres szerkezeti másolat | CTAS WHERE 1=0 | 07 |
| 25 | dátum előtt/után más táblába | INSERT FIRST/ALL | 09 |
| 26 | nézet | CREATE VIEW | 10 |
| 27 | lista egy cellában / összefűz | LISTAGG | 10 |
| 28 | a leg… / top 1 / első | ROWNUM alkérdés | 11 |
| 29 | akiknek nincs… | LEFT + IS NULL / NOT EXISTS | 12, 13 |
| 30 | nagyobb mint az átlag | subquery | 13 |
| 31 | formázott dátum | TO_CHAR | 14 |
| 32 | szövegből dátum | TO_DATE | 14 |
| 33 | aktuális idő | SYSDATE | 14 |
| 34 | hiányzik / nincs kitöltve | IS NULL | 14, 15 |
| 35 | ha nincs legyen 0 | NVL | 99 |
| 36 | ORA-00942 | tábla/jog | 15 |
| 37 | ORA-02291 | FK szülő hiány | 15 |
| 38 | ORA-00001 | UNIQUE/PK ütközés | 15 |
| 39 | ORA-00979 | GROUP BY hiány | 15 |
| 40 | ORA-01861 | dátum maszk | 14, 15 |
| 41 | ORA-01950 | nincs kvóta | 03, 15 |
| 42 | ORA-01031 | insufficient privileges | 03, 15 |
| 43 | véglegesítsd | COMMIT | 16 |
| 44 | vonjad vissza | ROLLBACK | 16 |
| 45 | sorrend: előbb szülő | függőség | 02 |
| 46 | másolható sablon? | NEM — kitöltendő minta | 99 |
| 47 | LIMIT / FETCH FIRST | TILOS 11g-n → ROWNUM | 11 |
| 48 | IDENTITY / AUTO_INCREMENT | TILOS → SEQUENCE | 04 |
| 49 | MySQL backtick / PG :: | TILOS | 18 |
| 50 | teljesen más feladat | döntési fa | 18 |
| 51 | két tábla neve + „és” | JOIN kulcs keresés | 12 |
| 52 | „minden X Y nélkül” | LEFT + IS NULL | 12 |
| 53 | „azok az X ahol Y darab ≥ n” | GROUP BY + HAVING | 10 |
| 54 | „másold a struktúrát adat nélkül” | CTAS 1=0 | 07 |
| 55 | „szétválogatás dátum szerint” | multitable INSERT | 09 |

## Következő 2 perc

Nyisd: [`01-FELADATSZOVEG-FELISMERES.md`](01-FELADATSZOVEG-FELISMERES.md) → [`02-FUGGOSEGI-SORREND.md`](02-FUGGOSEGI-SORREND.md).
