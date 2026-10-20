# Lépésről lépésre — döntési pontok (§19) + UX

**P0 · START** · Oracle 11g · pótzárthelyi / 20 perc

> **Tanulási út**, nem megoldásbank. Canonical csak ha a quick után elakadsz.

## Célfolyamat (UX)

**Feladatszöveg → max 1 quick (integrált ha kell) → teljes kitölthető SQL** (MIT ÍRJ + HONNAN VESZEM) → futtatás → ellenőrzés → ORA.

1. [`ZH-SZOVEG-FELISMERES-INDEX.md`](ZH-SZOVEG-FELISMERES-INDEX.md) vagy [`NEM-TUDOM-MIT-KERESSEK.md`](NEM-TUDOM-MIT-KERESSEK.md)
2. Egy quick → SQL kitöltés
3. Elakadás → canonical README / [`ISMERETLEN-FELADAT-FALLBACK.md`](ISMERETLEN-FELADAT-FALLBACK.md)

## Döntési pontok (sorrend)

| # | Kérdés | Igen → | Nem → |
|---|--------|--------|-------|
| 1 | User / séma / DROP ha van? | [`../01-SEMA-USER/DROP-USER.md`](../01-SEMA-USER/DROP-USER.md) | tovább |
| 2 | CREATE TABLE / típus? | 02-TABLA | tovább |
| 3 | PK/FK/CHECK LENGTH? | 03 + CHECK-LENGTH | tovább |
| 4 | Több táblába INSERT ALL? | 04 + INSERT-ALL-TOBB | egy tábla → 04 |
| 5 | Szétválogatás WHEN? | 06 | tovább |
| 6 | CTAS / MERGE? | 05 | tovább |
| 7 | Dátum napra (TRUNC)? | 11 + DATUM-IDOPONT | tovább |
| 8 | % módosítás / EXISTS UPDATE? | 12 DML lapok | tovább |
| 9 | LEFT? (*azokat is… semmi* / *függetlenül a kapcsolattól* / *nulla kapcsolódó* / *hiányában is*) | [`../08-JOIN-ES-KAPCSOLAT/00-ZH-GYORS-3-PERC.md`](../08-JOIN-ES-KAPCSOLAT/00-ZH-GYORS-3-PERC.md) | INNER → 08 |
| 10 | GROUP + HAVING COUNT? | 07 + HAVING-COUNT | tovább |
| 11 | LIKE kis/nagybetű? | 10 + LIKE-CASE | tovább |
| 12 | 5 komponens egy SELECT? | [`OT-KOMPONENSES-LEKERDEZES.md`](OT-KOMPONENSES-LEKERDEZES.md) | tovább |
| 13 | Rang / SUM OVER? | [`../18-ANALITIKUS/00-ZH-GYORS-3-PERC.md`](../18-ANALITIKUS/00-ZH-GYORS-3-PERC.md) | tovább |
| 14 | Top-N sima? | 09 ROWNUM | tovább |
| 15 | Idegen szöveg? | 22 + ISMERETLEN fallback | 99-MASTER |

## 20 perces időboxing

1. 0–3 perc: felismerés + komponensek  
2. 3–12 perc: DDL + adat  
3. 12–18 perc: SELECT / analitikus  
4. 18–20 perc: checklist + ORA

→ [`00-ZH-GYORS-3-PERC.md`](00-ZH-GYORS-3-PERC.md) · [`FELADAT-KOMPONENSEKRE-BONTASA.md`](FELADAT-KOMPONENSEKRE-BONTASA.md)
