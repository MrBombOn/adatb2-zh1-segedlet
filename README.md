# Adatbázisok 2 – Oracle / SQL ZH1 segédlet

Saját tanulási és **szintaktikai** segédlet. **Oracle Database 11g / 11g R2 ONLY.**
Nem megoldásbank: placeholder minták és tanulási mini-példák.

**Repo:** https://github.com/MrBombOn/adatb2-zh1-segedlet

---

# 20 PERCES ZH – START ITT

Ha kevés az időd / pótzárthelyi / gyors ismétlés:

**→ [`00-20-PERCES-ZH/00-START-ITT.md`](00-20-PERCES-ZH/00-START-ITT.md)**

## Gyors navigáció (20 perc)

| # | Lap | Mikor nyisd ki |
|---|-----|----------------|
| 00 | [START ITT](00-20-PERCES-ZH/00-START-ITT.md) | Mindig először |
| 01 | [Feladatszöveg felismerés](00-20-PERCES-ZH/01-FELADATSZOVEG-FELISMERES.md) | Mit kér a szöveg? |
| 02 | [Függőségi sorrend](00-20-PERCES-ZH/02-FUGGOSEGI-SORREND.md) | Melyik SQL előbb? |
| 03 | [Séma / user](00-20-PERCES-ZH/03-SEMA-USER.md) | CREATE USER / GRANT / QUOTA |
| 04 | [Tábla létrehozás](00-20-PERCES-ZH/04-TABLA-LETREHOZAS.md) | CREATE TABLE |
| 05 | [Constraint gyorsválasztó](00-20-PERCES-ZH/05-CONSTRAINT-GYORSVALASZTO.md) | PK/FK/UK/CK/NN |
| 06 | [INSERT 5 rekord](00-20-PERCES-ZH/06-INSERT-5-REKORD-EGYSZERRE.md) | INSERT ALL |
| 07 | [CTAS üres másolat](00-20-PERCES-ZH/07-CTAS-URES-MASOLAT.md) | WHERE 1=0 |
| 08 | [MERGE ha még nincs](00-20-PERCES-ZH/08-MERGE-HA-MEG-NINCS.md) | Upsert |
| 09 | [Dátum szétválogatás](00-20-PERCES-ZH/09-DATUM-ALAPJAN-SZETVALOGATAS.md) | INSERT FIRST/ALL |
| 10 | [VIEW + GROUP + LISTAGG](00-20-PERCES-ZH/10-VIEW-GROUP-LISTAGG.md) | Nézet + aggregálás |
| 11 | [Top-1 Oracle 11g](00-20-PERCES-ZH/11-TOP1-ORACLE11G.md) | ROWNUM (nem FETCH FIRST) |
| 12 | [JOIN pár nélkül is](00-20-PERCES-ZH/12-JOIN-PAR-NELKUL-IS.md) | LEFT JOIN |
| 13 | [Subquery](00-20-PERCES-ZH/13-SUBQUERY-GYORSSEGELY.md) | Alkérdés |
| 14 | [DATE](00-20-PERCES-ZH/14-DATE-GYORSSEGELY.md) | TO_DATE / TO_CHAR |
| 15 | [ORA hibák](00-20-PERCES-ZH/15-ORA-HIBAK-20-PERC.md) | 20 perces hibalista |
| 16 | [Végső ellenőrzés](00-20-PERCES-ZH/16-VEGSO-ELLENORZES.md) | Beadás előtt |
| 17 | [ZH technikai menet](00-20-PERCES-ZH/17-ZH-TECHNIKAI-MENET.md) | Szabályzat-kompatibilis |
| 18 | [Ha teljesen más feladat](00-20-PERCES-ZH/18-HA-TELJESEN-MAS-FELADAT-JON.md) | Döntési fa |
| 99 | [Master cheatsheet](00-20-PERCES-ZH/99-MASTER-CHEATSHEET.md) | Minden minta egyben |

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

Kliens a gyakorláshoz: **PL/SQL Developer** (nem SQL Developer-központú útmutató).

---

## Két réteg

| Réteg | Hol | Mire |
|-------|-----|------|
| **GYORS** | `00-20-PERCES-ZH/` | 20 perces ismétlés / pótzárthelyi |
| **TANULÓ** | `00-START-HERE/` … `22-ZH/` | Részletes magyarázat (P0/P1/P2) |

## Hol kezdjem? (tanuló út)

1. [`00-20-PERCES-ZH/`](00-20-PERCES-ZH/) ha ZH közel van  
2. [`00-START-HERE/`](00-START-HERE/) + [`01-KORNYEZET/`](01-KORNYEZET/)  
3. SELECT → JOIN → GROUP BY → DML/DDL  
4. [`20-GYAKORLAS/`](20-GYAKORLAS/) (≥80 feladat, LEVEL 0–4) + próba-ZH  

## Mappaáttekintés

| Mappa | Tartalom | Prio |
|-------|----------|------|
| `00-20-PERCES-ZH/` | 20 perces gyorsréteg | P0 |
| `00-START-HERE/` | Bevezető | P0 |
| `01-KORNYEZET/` | 11g + PL/SQL Developer | P0 |
| `02`–`15` | Részletes tananyag | P0–P2 |
| `16-SZINTAKTIKAI-SABLONOK/` | Kitöltendő szintaktikai minták | P0 |
| `17`–`19` | Felismerés, hibák, gyorssegély | P0 |
| `20-GYAKORLAS/` | ≥80 feladat + PROBA-ZH | P0 |
| `21-FOGALOMTAR/` | Fogalomtár | P2 |
| `22-ZH/` | Stratégia | P0 |
| `23-KORABBI-ZH-MINTAK/` | Mintafelismerés (nem kész megoldás) | P0 |

## Kitöltendő minta (placeholder)

```sql
SELECT <oszlopok>
FROM   <tabla>
WHERE  <feltetel>;
```

## Licenc

MIT – saját tartalomra. Lásd `LICENSE` és `REFERENCES.md`.
