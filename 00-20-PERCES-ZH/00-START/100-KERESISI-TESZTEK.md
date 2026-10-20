# 100 keresési / navigációs teszt (UX)

**P1** · Nem vizsgapontszám. Cél: feladatszöveg-rész → 1–2 lépés a quickig.

| # | Kereső / mondatrész | Várt quick / irány | Megjegyzés |
|---|---------------------|--------------------|------------|
| 1 | `azokat is, amelyekhez még nem tartozik semmi` | `08-JOIN` | LEFT JOIN |
| 2 | `minden rekord, függetlenül a kapcsolattól` | `08-JOIN` | LEFT JOIN |
| 3 | `akkor is mutasd, ha nulla kapcsolódó rekordja van` | `08-JOIN/LEFT-JOIN-COUNT` | LEFT+COUNT |
| 4 | `kapcsolódó rekord hiányában is` | `08-JOIN` | LEFT JOIN |
| 5 | `fuggetlenul a kapcsolattol` | `08-JOIN` | ékezet nélkül → LEFT |
| 6 | `hianyaban is` | `08-JOIN` | ékezet nélkül → LEFT |
| 7 | `nulla kapcsolodo` | `08-JOIN/LEFT-JOIN-COUNT` | ékezet nélkül |
| 8 | `DROP USER` | `01/DROP-USER` | DROP CASCADE |
| 9 | `ha mar letezik user` | `01/DROP-USER` | ékezet nélkül |
| 10 | `LENGTH karakter` | `03/CHECK-LENGTH` | CHECK LENGTH |
| 11 | `legalabb N karakter` | `03/CHECK-LENGTH` | ékezet nélkül |
| 12 | `INSERT ALL tobb tabla` | `04/INSERT-ALL-TOBB` | multi INSERT |
| 13 | `TRUNC SYSDATE` | `11/DATUM-IDOPONT` | TRUNC |
| 14 | `mai nap ido nelkul` | `11/DATUM-IDOPONT` | ékezet nélkül |
| 15 | `szazalek emeles` | `12/SZAZALEKOS` | % UPDATE |
| 16 | `UPDATE EXISTS` | `12/UPDATE-EXISTS` | EXISTS |
| 17 | `ROW_NUMBER PARTITION` | `18/INTEGRATED` | analytics |
| 18 | `SUM OVER` | `18/SUM-COUNT-AVG` | window sum |
| 19 | `HAVING COUNT` | `07/HAVING-COUNT` | HAVING |
| 20 | `UPPER LIKE` | `10/LIKE-CASE` | case-insensitive |
| 21 | `5 komponens` | `00-START/OT-KOMPONENSES` | integrated |
| 22 | `FETCH FIRST` | `09-TOP1 TILOS` | tilos |
| 23 | `nem tudom mit keressek` | `NEM-TUDOM` | fallback entry |
| 24 | `ismeretlen feladat` | `ISMERETLEN-FELADAT` | 12 kérdés |
| 25 | `AUTHOR BOOK left` | `08-JOIN` | entity glue |
| 26 | `CUSTOMER ORDER nelkul` | `08/NINCS-PAR` | ékezet nélkül |
| 27 | `STUDENT COURSE COUNT 0` | `08/LEFT-JOIN-COUNT` | COUNT=0 |
| 28 | `EMPLOYEE DEPARTMENT rang` | `18/INTEGRATED` | analytics |
| 29 | `COUNT(*)=0 left` | `CSAPDA COUNT(pk)` | trap |
| 30 | `IF EXISTS drop user` | `TILOS` | 11g |
| 31 | `azokat is, amelyekhez még nem tartozik semmi (variáns 31)` | `08-JOIN` | LEFT JOIN |
| 32 | `minden rekord, függetlenül a kapcsolattól (variáns 32)` | `08-JOIN` | LEFT JOIN |
| 33 | `akkor is mutasd, ha nulla kapcsolódó rekordja van (variáns 33)` | `08-JOIN/LEFT-JOIN-COUNT` | LEFT+COUNT |
| 34 | `kapcsolódó rekord hiányában is (variáns 34)` | `08-JOIN` | LEFT JOIN |
| 35 | `fuggetlenul a kapcsolattol (variáns 35)` | `08-JOIN` | ékezet nélkül → LEFT |
| 36 | `hianyaban is (variáns 36)` | `08-JOIN` | ékezet nélkül → LEFT |
| 37 | `nulla kapcsolodo (variáns 37)` | `08-JOIN/LEFT-JOIN-COUNT` | ékezet nélkül |
| 38 | `DROP USER (variáns 38)` | `01/DROP-USER` | DROP CASCADE |
| 39 | `ha mar letezik user (variáns 39)` | `01/DROP-USER` | ékezet nélkül |
| 40 | `LENGTH karakter (variáns 40)` | `03/CHECK-LENGTH` | CHECK LENGTH |
| 41 | `legalabb N karakter (variáns 41)` | `03/CHECK-LENGTH` | ékezet nélkül |
| 42 | `INSERT ALL tobb tabla (variáns 42)` | `04/INSERT-ALL-TOBB` | multi INSERT |
| 43 | `TRUNC SYSDATE (variáns 43)` | `11/DATUM-IDOPONT` | TRUNC |
| 44 | `mai nap ido nelkul (variáns 44)` | `11/DATUM-IDOPONT` | ékezet nélkül |
| 45 | `szazalek emeles (variáns 45)` | `12/SZAZALEKOS` | % UPDATE |
| 46 | `UPDATE EXISTS (variáns 46)` | `12/UPDATE-EXISTS` | EXISTS |
| 47 | `ROW_NUMBER PARTITION (variáns 47)` | `18/INTEGRATED` | analytics |
| 48 | `SUM OVER (variáns 48)` | `18/SUM-COUNT-AVG` | window sum |
| 49 | `HAVING COUNT (variáns 49)` | `07/HAVING-COUNT` | HAVING |
| 50 | `UPPER LIKE (variáns 50)` | `10/LIKE-CASE` | case-insensitive |
| 51 | `5 komponens (variáns 51)` | `00-START/OT-KOMPONENSES` | integrated |
| 52 | `FETCH FIRST (variáns 52)` | `09-TOP1 TILOS` | tilos |
| 53 | `nem tudom mit keressek (variáns 53)` | `NEM-TUDOM` | fallback entry |
| 54 | `ismeretlen feladat (variáns 54)` | `ISMERETLEN-FELADAT` | 12 kérdés |
| 55 | `AUTHOR BOOK left (variáns 55)` | `08-JOIN` | entity glue |
| 56 | `CUSTOMER ORDER nelkul (variáns 56)` | `08/NINCS-PAR` | ékezet nélkül |
| 57 | `STUDENT COURSE COUNT 0 (variáns 57)` | `08/LEFT-JOIN-COUNT` | COUNT=0 |
| 58 | `EMPLOYEE DEPARTMENT rang (variáns 58)` | `18/INTEGRATED` | analytics |
| 59 | `COUNT(*)=0 left (variáns 59)` | `CSAPDA COUNT(pk)` | trap |
| 60 | `IF EXISTS drop user (variáns 60)` | `TILOS` | 11g |
| 61 | `azokat is, amelyekhez még nem tartozik semmi (variáns 61)` | `08-JOIN` | LEFT JOIN |
| 62 | `minden rekord, függetlenül a kapcsolattól (variáns 62)` | `08-JOIN` | LEFT JOIN |
| 63 | `akkor is mutasd, ha nulla kapcsolódó rekordja van (variáns 63)` | `08-JOIN/LEFT-JOIN-COUNT` | LEFT+COUNT |
| 64 | `kapcsolódó rekord hiányában is (variáns 64)` | `08-JOIN` | LEFT JOIN |
| 65 | `fuggetlenul a kapcsolattol (variáns 65)` | `08-JOIN` | ékezet nélkül → LEFT |
| 66 | `hianyaban is (variáns 66)` | `08-JOIN` | ékezet nélkül → LEFT |
| 67 | `nulla kapcsolodo (variáns 67)` | `08-JOIN/LEFT-JOIN-COUNT` | ékezet nélkül |
| 68 | `DROP USER (variáns 68)` | `01/DROP-USER` | DROP CASCADE |
| 69 | `ha mar letezik user (variáns 69)` | `01/DROP-USER` | ékezet nélkül |
| 70 | `LENGTH karakter (variáns 70)` | `03/CHECK-LENGTH` | CHECK LENGTH |
| 71 | `legalabb N karakter (variáns 71)` | `03/CHECK-LENGTH` | ékezet nélkül |
| 72 | `INSERT ALL tobb tabla (variáns 72)` | `04/INSERT-ALL-TOBB` | multi INSERT |
| 73 | `TRUNC SYSDATE (variáns 73)` | `11/DATUM-IDOPONT` | TRUNC |
| 74 | `mai nap ido nelkul (variáns 74)` | `11/DATUM-IDOPONT` | ékezet nélkül |
| 75 | `szazalek emeles (variáns 75)` | `12/SZAZALEKOS` | % UPDATE |
| 76 | `UPDATE EXISTS (variáns 76)` | `12/UPDATE-EXISTS` | EXISTS |
| 77 | `ROW_NUMBER PARTITION (variáns 77)` | `18/INTEGRATED` | analytics |
| 78 | `SUM OVER (variáns 78)` | `18/SUM-COUNT-AVG` | window sum |
| 79 | `HAVING COUNT (variáns 79)` | `07/HAVING-COUNT` | HAVING |
| 80 | `UPPER LIKE (variáns 80)` | `10/LIKE-CASE` | case-insensitive |
| 81 | `5 komponens (variáns 81)` | `00-START/OT-KOMPONENSES` | integrated |
| 82 | `FETCH FIRST (variáns 82)` | `09-TOP1 TILOS` | tilos |
| 83 | `nem tudom mit keressek (variáns 83)` | `NEM-TUDOM` | fallback entry |
| 84 | `ismeretlen feladat (variáns 84)` | `ISMERETLEN-FELADAT` | 12 kérdés |
| 85 | `AUTHOR BOOK left (variáns 85)` | `08-JOIN` | entity glue |
| 86 | `CUSTOMER ORDER nelkul (variáns 86)` | `08/NINCS-PAR` | ékezet nélkül |
| 87 | `STUDENT COURSE COUNT 0 (variáns 87)` | `08/LEFT-JOIN-COUNT` | COUNT=0 |
| 88 | `EMPLOYEE DEPARTMENT rang (variáns 88)` | `18/INTEGRATED` | analytics |
| 89 | `COUNT(*)=0 left (variáns 89)` | `CSAPDA COUNT(pk)` | trap |
| 90 | `IF EXISTS drop user (variáns 90)` | `TILOS` | 11g |
| 91 | `azokat is, amelyekhez még nem tartozik semmi (variáns 91)` | `08-JOIN` | LEFT JOIN |
| 92 | `minden rekord, függetlenül a kapcsolattól (variáns 92)` | `08-JOIN` | LEFT JOIN |
| 93 | `akkor is mutasd, ha nulla kapcsolódó rekordja van (variáns 93)` | `08-JOIN/LEFT-JOIN-COUNT` | LEFT+COUNT |
| 94 | `kapcsolódó rekord hiányában is (variáns 94)` | `08-JOIN` | LEFT JOIN |
| 95 | `fuggetlenul a kapcsolattol (variáns 95)` | `08-JOIN` | ékezet nélkül → LEFT |
| 96 | `hianyaban is (variáns 96)` | `08-JOIN` | ékezet nélkül → LEFT |
| 97 | `nulla kapcsolodo (variáns 97)` | `08-JOIN/LEFT-JOIN-COUNT` | ékezet nélkül |
| 98 | `DROP USER (variáns 98)` | `01/DROP-USER` | DROP CASCADE |
| 99 | `ha mar letezik user (variáns 99)` | `01/DROP-USER` | ékezet nélkül |
| 100 | `LENGTH karakter (variáns 100)` | `03/CHECK-LENGTH` | CHECK LENGTH |

## Értékelés
- ≥90/100 irány helyes → keresési UX PASS
- LEFT JOIN 4 kulcsmondat kötelezően benne (1–4 + ékezet nélküli 5–7)

→ [`ZH-SZOVEG-FELISMERES-INDEX.md`](ZH-SZOVEG-FELISMERES-INDEX.md) · [`ZERO-KNOWLEDGE-TESZTEK.md`](ZERO-KNOWLEDGE-TESZTEK.md)
