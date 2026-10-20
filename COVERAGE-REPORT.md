# Coverage report V2 — két ZH / retake minták

> **Nem vak 100%.** Repo-audit + mintalefedettség. Külső syllabus nincs feltöltve.

## Tengelyek

| Tengely | Mit jelent | Becsült lefedettség | Megjegyzés |
|---------|------------|---------------------|------------|
| **Original ZH jelleg** | User, tábla, FK, INSERT ALL, JOIN, GROUP, Top-N, dátum | **Magas** (~85–95% a GYORS+tanulói rétegben) | Régi `23/00` + 00–11 mappák |
| **Pót ZH jelleg** | DROP USER, LENGTH CHECK, multi-table INSERT, TRUNC, % UPDATE, EXISTS UPDATE, analitikus hangsúly, COUNT=0, UPPER LIKE, 5 komponens | **Magas** (~80–90% az új lapokkal) | `23/01-pot-zh…` |
| **Common (közös)** | CREATE USER, PK/FK, INSERT, JOIN, HAVING, TO_DATE | **Magas** | `23/02-KOZOS…` |
| **Zero-knowledge** | ≥30 döntési teszt | **35 tétel** a START-ban | nem vizsgapontszám |
| **20-min fast path** | 00-START 3 perc + topic 00-ZH-GYORS-3-PERC + integrated analytics | **Lefedve** | új mintákra külön 3 perc |
| **Analytics / window** | OVER, PARTITION, SUM/COUNT/AVG OVER, ROW_NUMBER, RANK, DENSE_RANK, GROUP vs PARTITION, tipikus mondatok, integrated | **Lefedve (P1 gyorsfa)** | korábban vékony P2 README |

## Új fájlok (additív, V2)

- `01-SEMA-USER/DROP-USER.md`
- `03-CONSTRAINT/CHECK-LENGTH.md`
- `04-ADATFELTOLTES/INSERT-ALL-TOBB-TABLABA.md`
- `11-DATUM/DATUM-IDOPONT-NELKUL.md`
- `12-DML/SZAZALEKOS-MODOSITAS.md`, `UPDATE-HA-VAN-KAPCSOLODO-REKORD.md`
- `18-ANALITIKUS/*` (több lap + 3 perc + integrated)
- `08-JOIN…/LEFT-JOIN-COUNT-NULL.md`, `NINCS-PAR.md`
- `10-WHERE…/LIKE-CASE-INSENSITIVE.md`
- `07-VIEW…/HAVING-COUNT.md`
- `00-START/FELADAT-KOMPONENSEKRE-BONTASA.md`, `00-LEPESROL-LEPESRE.md`, `00-ZH-GYORS-3-PERC.md`, `OT-KOMPONENSES-LEKERDEZES.md`, `ZERO-KNOWLEDGE-TESZTEK.md`
- `23-KORABBI…/01-pot-zh-mit-tesztelt.md`, `02-KOZOS-MINTAK-ES-VALTOZATOK.md`

## Szándékos rések (nem 100%)

- Konkrét kurzusobjektum-megoldások (KONYV/KOLCSONZES, TERMEK/…) — **szándékosan nincs**
- Lab-specifikus tablespace/jog nevek — KÖRNYEZETFÜGGŐ
- Minden lehetséges meglepetés-feladat — döntési mátrix, nem katalógus
- Hivatalos „ez volt a ZH szövege” állítás — **nincs**; csak mintafelismerés

## Kapcsolódó

- [`COURSE-COVERAGE.md`](COURSE-COVERAGE.md) — fejezet-audit
- [`23-KORABBI-ZH-MINTAK/`](23-KORABBI-ZH-MINTAK/)
