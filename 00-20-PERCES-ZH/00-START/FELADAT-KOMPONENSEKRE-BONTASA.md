# Feladat komponensekre bontása + egyben sablon

**P0 · START** · 11g · Zero-knowledge / UX

> Nem megoldás. Darabokra bontod → mappa → **utána egyben** a sablon.

## Lépések

1. Olvasd végig egyszer.
2. Karikázd: DDL / DML / SELECT / JOIN / GROUP / dátum / analitikus / jog.
3. Minden karikához 1 quick a [`ZH-SZOVEG-FELISMERES-INDEX.md`](ZH-SZOVEG-FELISMERES-INDEX.md)-ből (max 1 katt P0).
4. Függőségek: USER → TABLE → CONSTRAINT → INSERT → SELECT.
5. Összetett SELECT? → [`OT-KOMPONENSES-LEKERDEZES.md`](OT-KOMPONENSES-LEKERDEZES.md) **egyben**.
6. Idegen? → [`ISMERETLEN-FELADAT-FALLBACK.md`](ISMERETLEN-FELADAT-FALLBACK.md).

## Gyors térkép

| Darab | Quick (önálló SQL) |
|-------|--------------------|
| DROP/CREATE USER | 01/DROP-USER |
| CHECK LENGTH | 03/CHECK-LENGTH |
| INSERT ALL több tábla | 04/INSERT-ALL-TOBB |
| TRUNC nap | 11/DATUM-IDOPONT |
| % UPDATE | 12/SZAZALEKOS |
| UPDATE EXISTS | 12/UPDATE-EXISTS |
| analitikus SUM+RN | 18/INTEGRATED |
| LEFT (*azokat is…* / *függetlenül…* / *nulla…* / *hiányában…*) | 08/00-ZH-GYORS-3-PERC + COUNT=0 |
| LIKE kis/nagy | 10/LIKE-CASE |
| HAVING COUNT | 07/HAVING-COUNT |
| 5 komponens egyben | OT-KOMPONENSES |

## Egyben sablon után

Ha a darabok LEFT+COUNT+GROUP+LIKE+HAVING → ne darabold tovább: nyisd az OT-KOMPONENSES quicket.

→ [`00-LEPESROL-LEPESRE.md`](00-LEPESROL-LEPESRE.md)

## LEFT JOIN felismerő mondatok

- azokat is, amelyekhez még nem tartozik semmi
- minden rekord, függetlenül a kapcsolattól
- akkor is mutasd, ha nulla kapcsolódó rekordja van
- kapcsolódó rekord hiányában is
