# Top-N és subquery

**P0 · GYORS** · Oracle **11g / 11g R2 ONLY** · Kliens: **PL/SQL Developer**

## HOL TALÁLOM?

| Kell | Hol |
|------|-----|
| Szintaxis | ebben a README-ben → **MINIMÁLIS SZINTAXIS** |
| Nem értem a fogalmat | **RÉSZLETES MAGYARÁZAT** link + laikus definíció lent |
| Helyőrző mit írjak | **MIT ÍRHATOK** + **ÉRTÉKEK JELENTÉSE** |
| ORA hiba | lent + [`../20-ORA-HIBAK/`](../20-ORA-HIBAK/) |
| Feladatszöveg → mappa | [`../00-START/FELADATSZOVEG-INDEX.md`](../00-START/FELADATSZOVEG-INDEX.md) |

## MIT KÉR

Top-N: ROWNUM / ROW_NUMBER (TILOS FETCH FIRST). Subquery: IN / EXISTS / skálár.

## MIRE GONDOLJ

ROWNUM az ORDER BY utáni alkérdésen. FETCH FIRST csak TILOS figyelmeztetésben.

**Laikus:** leg… ≈ amit a feladatszöveg magyarul kér; a SQL csak a pontos eszköz.

## MINIMÁLIS SZINTAXIS (11g)

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
SELECT * FROM (
  SELECT <oszlopok> FROM <tabla> ORDER BY <rendezes> DESC
) WHERE ROWNUM <= <n>;

SELECT * FROM (
  SELECT <oszlopok>, ROW_NUMBER() OVER (ORDER BY <rendezes> DESC) AS rn
  FROM <tabla>
) WHERE rn = 1;

SELECT <oszlopok> FROM <tabla> t
WHERE t.<szam> > (SELECT AVG(<szam>) FROM <tabla>)
   OR t.<id> IN (SELECT <id> FROM <masik> WHERE <feltetel>)
   OR EXISTS (SELECT 1 FROM <masik> m WHERE m.<fk> = t.<pk>);
```

## MIT ÍRHATOK (helyőrzők)

| Helyőrző | Mit írj | Jelölés | Példa gondolat |
|----------|---------|---------|----------------|
| `<n>` | Hány sor (Top-N) | KÖTELEZŐ | 1, 3, 5 |
| `<rendezes>` | ORDER BY kifejezés | KÖTELEZŐ | price, hire_date |
| `belső SELECT` | Subquery | KÖTELEZŐ | AVG / IN lista / EXISTS |

## ÉRTÉKEK JELENTÉSE

| Érték / minta | Jelentés | Jelölés |
|---------------|----------|---------|
| `ROWNUM` | 11g Top-N | **VALID / KÖTELEZŐ Top-N-hez** |
| `ROW_NUMBER() OVER` | Analitikus Top-N | **VALID** |
| `FETCH FIRST` | 12c+ — TILOS megoldásként | **TILTOTT** |
| `EXISTS` | Létezik-e sor | **VALID** |

Jelölés: **KÖTELEZŐ** = a feladat/szintaxis kéri · **VALID** = 11g-ben elfogadott · **TIPIKUS** = gyakori lab · **KÖRNYEZETFÜGGŐ** = a lab dönti el.

## PÉLDA FELADATSZÖVEG (alternatív entitások)

Világok: `AUTHOR/BOOK, STUDENT/COURSE, CITY/PERSON, CUSTOMER/ORDER, CAR/OWNER` — **NE** TERMEK/KATEGORIA kész megoldást másolj.

- „A legdrágább BOOK.” → ORDER BY price DESC + ROWNUM=1
- „Hallgatók az átlag feletti kredittel.” → subquery AVG
- „Városok ahol van PERSON.” → EXISTS
- „Ügyfelek akiknek nincs ORDER.” → NOT EXISTS / LEFT

## LÉPÉSEK NULLÁRÓL

1. Top-N? → belső ORDER BY + ROWNUM
2. Átlag/halmaz? → subquery
3. Futtasd külön a belső SELECT-et
4. Nincs FETCH FIRST

## HA EZT ÍRJA

| Feladatszöveg | Teendő |
|---------------|--------|
| leg… / top / első N | ROWNUM alkérdés |
| nagyobb mint az átlag | skálár subquery |
| azok akik / létezik olyan | IN / EXISTS |
| FETCH FIRST / LIMIT | TILOS → ROWNUM |

## TIPIKUS HIBÁK

- ROWNUM WHERE az ORDER BY előtt (rossz minta)
- Több soros subquery `=` mellett
- FETCH FIRST reflex

## TIPIKUS ORA (ehhez a témához)

| Kód | Mit nézz |
|-----|----------|
| ORA-00936 | missing expression |
| ORA-01427 | single-row subquery returns more |

## 10s ELLENŐRZÉS

- [ ] Belső SELECT önmagában OK?
- [ ] ROWNUM a külső WHERE-ben a rendezett alkérdésen?
- [ ] Nincs FETCH FIRST a megoldásban

## RÉSZLETES MAGYARÁZAT

→ [`../../04-SELECT/`](../../04-SELECT/) · gyakorlás Top-N

## KAPCSOLÓDÓ

- [`../18-ANALITIKUS/`](../18-ANALITIKUS/)
- [`../08-JOIN-ES-KAPCSOLAT/`](../08-JOIN-ES-KAPCSOLAT/)

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
site:docs.oracle.com Oracle 11g ROWNUM ROW_NUMBER subquery EXISTS IN syntax
```

```text
site:stackoverflow.com Oracle 11g ROWNUM ROW_NUMBER subquery EXISTS IN -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference ROWNUM ROW_NUMBER subquery EXISTS IN
```

```text
"Oracle 11g" ROWNUM ROW_NUMBER subquery EXISTS IN ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```
