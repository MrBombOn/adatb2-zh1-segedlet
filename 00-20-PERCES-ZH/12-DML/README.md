# DML (UPDATE / DELETE)

**P1 · GYORS** · Oracle **11g / 11g R2 ONLY** · Kliens: **PL/SQL Developer**

## HOL TALÁLOM?

| Kell | Hol |
|------|-----|
| Szintaxis | ebben a README-ben → **MINIMÁLIS SZINTAXIS** |
| Nem értem a fogalmat | **RÉSZLETES MAGYARÁZAT** link + laikus definíció lent |
| Helyőrző mit írjak | **MIT ÍRHATOK** + **ÉRTÉKEK JELENTÉSE** |
| ORA hiba | lent + [`../20-ORA-HIBAK/`](../20-ORA-HIBAK/) |
| Feladatszöveg → mappa | [`../00-START/FELADATSZOVEG-INDEX.md`](../00-START/FELADATSZOVEG-INDEX.md) |

## MIT KÉR

UPDATE / DELETE — mindig WHERE-tudatosan; előtte SELECT COUNT.

## MIRE GONDOLJ

DELETE ≠ DROP. Tranzakció: COMMIT/ROLLBACK ha kell.

**Laikus:** módosíts ≈ amit a feladatszöveg magyarul kér; a SQL csak a pontos eszköz.

## MINIMÁLIS SZINTAXIS (11g)

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
UPDATE <tabla> SET <oszlop> = <ertek> WHERE <feltetel>;
DELETE FROM <tabla> WHERE <feltetel>;
-- előtte:
SELECT COUNT(*) FROM <tabla> WHERE <feltetel>;
```

## MIT ÍRHATOK (helyőrzők)

| Helyőrző | Mit írj | Jelölés | Példa gondolat |
|----------|---------|---------|----------------|
| `SET <oszlop>` | Új érték | KÖTELEZŐ | status = 'CLOSED' |
| `WHERE` | Melyik sorok | KÖTELEZŐ gyakorlatban | id = … |

## ÉRTÉKEK JELENTÉSE

| Érték / minta | Jelentés | Jelölés |
|---------------|----------|---------|
| `UPDATE` | Sorok módosítása | **VALID** |
| `DELETE` | Sorok törlése | **VALID** |
| `WHERE nélküli DML` | Egész tábla — veszélyes | **FIGYELEM** |

Jelölés: **KÖTELEZŐ** = a feladat/szintaxis kéri · **VALID** = 11g-ben elfogadott · **TIPIKUS** = gyakori lab · **KÖRNYEZETFÜGGŐ** = a lab dönti el.

## PÉLDA FELADATSZÖVEG (alternatív entitások)

Világok: `AUTHOR/BOOK, STUDENT/COURSE, CITY/PERSON, CUSTOMER/ORDER, CAR/OWNER` — **NE** TERMEK/KATEGORIA kész megoldást másolj.

- „Állítsd CLOSED-ra a lezárt ORDER-eket.”
- „Töröld a COURSE-okat ahol nincs jelentkező (óvatosan).”
- „Frissítsd a CAR színét.”

## LÉPÉSEK NULLÁRÓL

1. SELECT előtte
2. UPDATE/DELETE WHERE-rel
3. SELECT utána
4. COMMIT ha kell

## HA EZT ÍRJA

| Feladatszöveg | Teendő |
|---------------|--------|
| módosíts / állíts | UPDATE |
| töröld a sorokat | DELETE |

## TIPIKUS HIBÁK

- WHERE nélkül
- FK miatt ORA-02292
- DDL-lel összekevert DELETE/DROP

## TIPIKUS ORA (ehhez a témához)

| Kód | Mit nézz |
|-----|----------|
| ORA-02292 | child record found |
| ORA-00001 | unique after update |

## 10s ELLENŐRZÉS

- [ ] Hány sort érint?
- [ ] COMMIT kell-e?

## RÉSZLETES MAGYARÁZAT

→ [`../../09-DML/`](../../09-DML/)

## KAPCSOLÓDÓ

- [`../15-TRANZAKCIO/`](../15-TRANZAKCIO/)
- [`../04-ADATFELTOLTES/`](../04-ADATFELTOLTES/)

## KERESÉS

Lásd lent, vagy [`../21-KERESOSEGED/`](../21-KERESOSEGED/).



## ORACLE 11g VALIDÁCIÓ

| Kérdés | Válasz |
|--------|--------|
| Van FETCH FIRST / OFFSET ROWS / LIMIT a megoldásban? | **NO** (csak TILOS figyelmeztetésben OK) |
| Van IDENTITY / AUTO_INCREMENT? | **NO** → SEQUENCE |
| Top-N ROWNUM / ROW_NUMBER? | **YES** ha kell Top-N |
| Placeholder kitöltve a feladatsor neveivel? | **YES** kell |
| USER ≈ SCHEMA tudatos? | **YES** (nincs vak CREATE SCHEMA) |


## KERESÉS, HA ELAKADTAM

> **Figyelem:** Kerüld a MySQL / Postgres / SQL Server találatokat és a **12c+** megoldásokat (`FETCH FIRST`, `OFFSET … ROWS`, `IDENTITY`). Elsőbbség: hivatalos **Oracle 11g** dokumentáció.

Bemásolható keresők (5–10 mp):

```text
site:docs.oracle.com Oracle 11g UPDATE DELETE WHERE syntax
```

```text
site:stackoverflow.com Oracle 11g UPDATE DELETE WHERE -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference UPDATE DELETE WHERE
```

```text
"Oracle 11g" UPDATE DELETE WHERE ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```
