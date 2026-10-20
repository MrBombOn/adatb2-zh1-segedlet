# Pót-ZH — mit szokott tesztelni? (mintafelismerés)

**P0** · NEM szó szerinti feladatsor · NEM megoldásbank  
Világok: AUTHOR/BOOK, CUSTOMER/ORDER, STUDENT/COURSE, EMPLOYEE/DEPARTMENT  
**Nincs** KONYV/KOLCSONZES / TERMEK/KATEGORIA megoldás.

| # | Minta | Szövegjel | Merre |
|---|-------|-----------|-------|
| 1 | DROP USER + CREATE | ha már létezik / töröld | `01-SEMA-USER/DROP-USER` |
| 2 | CHECK LENGTH | legalább N karakter | `03/CHECK-LENGTH` |
| 3 | INSERT ALL több tábla | több táblába egyszerre | `04/INSERT-ALL-TOBB-TABLABA` |
| 4 | TRUNC nap | mai nap / idő nélkül | `11/DATUM-IDOPONT-NELKUL` |
| 5 | % UPDATE | N%-kal emeld/csökkentsd | `12/SZAZALEKOS-MODOSITAS` |
| 6 | UPDATE EXISTS | akiknek van … | `12/UPDATE-HA-VAN…` |
| 7 | Analitikus | rang / partíciónként összeg | `18-ANALITIKUS` |
| 8 | LEFT COUNT=0 | nincs pár / 0 darab | `08/NINCS-PAR` |
| 9 | LIKE UPPER | kis-nagy betű | `10/LIKE-CASE-INSENSITIVE` |
| 10 | HAVING COUNT | legalább N a csoportban | `07/HAVING-COUNT` |
| 11 | 5 komponens | LEFT+COUNT+GROUP+LIKE+HAVING | `00-START/OT-KOMPONENSES…` |

Gyakorlat: saját mini-feladat a fenti típusokra → placeholder → próba-ZH.
