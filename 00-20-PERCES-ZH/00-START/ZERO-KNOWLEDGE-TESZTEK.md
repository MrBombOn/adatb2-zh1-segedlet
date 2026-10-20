# Zero-knowledge tesztek (≥30) — retake minták

**Cél:** laikus döntés feladatszöveg → mappa/eszköz. **Nincs** kész megoldás.  
Válaszolj fejben, majd nézd a „Kulcs” sort.

| # | Feladatszöveg (általános) | Várt irány | Kulcs |
|---|---------------------------|------------|-------|
| 1 | Ha a user már létezik, töröld, majd hozd létre | DROP USER CASCADE → CREATE | nincs IF EXISTS |
| 2 | A név legalább 3 karakter legyen | CHECK LENGTH >= 3 | 03/CHECK-LENGTH |
| 3 | Vegyél fel sort az AUTHOR és a BOOK táblába egyszerre | INSERT ALL több tábla | 04/INSERT-ALL-TOBB |
| 4 | Mai nap dátuma óra nélkül | TRUNC(SYSDATE) | 11/DATUM-IDOPONT |
| 5 | Emeld a fizetést 10%-kal | * (1+10/100) | 12/SZAZALEKOS |
| 6 | Frissítsd azokat, akiknek van rendelésük | UPDATE … EXISTS | 12/UPDATE-EXISTS |
| 7 | Osztályonként rangsorold a dolgozókat fizetés szerint | ROW_NUMBER PARTITION | 18 |
| 8 | Minden sor mellett az osztály összfizetése | SUM OVER PARTITION | 18 |
| 9 | Csoportonként a legjobb 1 | rn=1 külső WHERE | 18 integrated |
| 10 | Szerzők könyv nélkül | LEFT + IS NULL | 08/NINCS-PAR |
| 11 | Akiknek 0 kurzusuk van (COUNT) | HAVING COUNT(jobb)=0 | COUNT(*) csapda |
| 12 | Névben legyen „al”, kis-nagy mindegy | UPPER LIKE UPPER | 10/LIKE |
| 13 | Legalább 5 rendelésű ügyfelek | HAVING COUNT(*) >= 5 | 07 |
| 14 | Pontosan 2 könyve van | HAVING COUNT = 2 | 07 |
| 15 | LEFT+COUNT+GROUP+LIKE+HAVING egyben | 5 komponens | 00-START/OT-… |
| 16 | FETCH FIRST 5 ROWS | **TILOS** 11g | ROWNUM/ROW_NUMBER |
| 17 | DROP USER IF EXISTS | **TILOS** 11g | DROP USER |
| 18 | MySQL multi VALUES (1,2),(3,4) | **TILOS** | INSERT ALL |
| 19 | COUNT(*) = 0 LEFT után „nincs pár” | **HIBÁS** | COUNT(pk) |
| 20 | GROUP BY vs minden sor + összeg | OVER nem GROUP | 18/GROUP-BY-VS |
| 21 | RANK lyukkal | RANK | 18/RANK |
| 22 | DENSE_RANK lyuk nélkül | DENSE_RANK | 18 |
| 23 | IN alt EXISTS helyett UPDATE-nél | IN subquery | 12 |
| 24 | Csökkentsd 15%-kal az árat | * (1-15/100) | 12 |
| 25 | TRUNC hónap elejére | TRUNC(d,'MM') | 11 |
| 26 | User ≈ séma? | IGEN Oracle-ben | 01 |
| 27 | CREATE SCHEMA vakon | **NE** | CREATE USER |
| 28 | WHERE vs HAVING | sor vs csoport | 07/10 |
| 29 | Top-N IDENTITY | **TILOS** | SEQUENCE |
| 30 | Idegen megfogalmazás | döntési mátrix | 22 |
| 31 | Pót és eredeti közös: INSERT ALL | közös mag | 23/02 |
| 32 | Analitikus + Top egy sablonban | SUM+ROW_NUMBER | 18/INTEGRATED |
| 33 | FK sorrend multitable INSERT-nél | szülő előbb | 04 docs |
| 34 | LIKE csak az oszlopon UPPER, mintán nem | kockázatos | mindkét oldal |
| 35 | „nincs pár” INNER JOIN-nel | általában nem | LEFT |

**Értékelés:** 30+/35 irány helyes → ZK réteg OK. Nem 100% vak állítás — a lab feladatsor változhat.
## LEFT JOIN kulcsmondatok (kötelező ZK)

| # | Mondat | Várt |
|---|--------|------|
| L1 | azokat is, amelyekhez még nem tartozik semmi | LEFT JOIN |
| L2 | minden rekord, függetlenül a kapcsolattól | LEFT JOIN |
| L3 | akkor is mutasd, ha nulla kapcsolódó rekordja van | LEFT (+ IS NULL / COUNT=0) |
| L4 | kapcsolódó rekord hiányában is | LEFT JOIN |
| L5 | fuggetlenul a kapcsolattol (ék. nélkül) | LEFT JOIN |

→ [100-KERESISI-TESZTEK.md](100-KERESISI-TESZTEK.md) (100 navigációs teszt)