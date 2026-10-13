# VIEW és csoportosítás

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

CREATE VIEW; GROUP BY + aggregátum; gyakran LISTAGG.

## MIRE GONDOLJ

Minden nem aggregált SELECT-oszlop a GROUP BY-ban. LISTAGG 11g OK.

**Laikus:** nézet ≈ amit a feladatszöveg magyarul kér; a SQL csak a pontos eszköz.

## MINIMÁLIS SZINTAXIS (11g)

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
CREATE OR REPLACE VIEW <nezet> AS
SELECT <csoport_oszlop>,
       COUNT(*) AS darab,
       LISTAGG(<elem>, ',') WITHIN GROUP (ORDER BY <elem>) AS lista
FROM   <tabla>
GROUP BY <csoport_oszlop>;

SELECT <c>, COUNT(*), SUM(<n>), AVG(<n>), MIN(<o>), MAX(<o>)
FROM <t>
GROUP BY <c>
HAVING COUNT(*) >= <n>;
```

## MIT ÍRHATOK (helyőrzők)

| Helyőrző | Mit írj | Jelölés | Példa gondolat |
|----------|---------|---------|----------------|
| `<nezet>` | Nézet neve | KÖTELEZŐ | v_course_enroll |
| `<csoport_oszlop>` | GROUP BY kulcs | KÖTELEZŐ | course_id / city |
| `LISTAGG elválasztó` | ',' vagy ';' | TIPIKUS | , |

## ÉRTÉKEK JELENTÉSE

| Érték / minta | Jelentés | Jelölés |
|---------------|----------|---------|
| `GROUP BY` | Csoportkulcs | **KÖTELEZŐ ha aggregálsz + oszlop** |
| `HAVING` | Csoportszűrés | **VALID** |
| `LISTAGG … WITHIN GROUP` | 11g string agg | **VALID** |
| `FETCH FIRST a nézetben` | TILOS 11g megoldásként | **TILTOTT** |

Jelölés: **KÖTELEZŐ** = a feladat/szintaxis kéri · **VALID** = 11g-ben elfogadott · **TIPIKUS** = gyakori lab · **KÖRNYEZETFÜGGŐ** = a lab dönti el.

## PÉLDA FELADATSZÖVEG (alternatív entitások)

Világok: `AUTHOR/BOOK, STUDENT/COURSE, CITY/PERSON, CUSTOMER/ORDER, CAR/OWNER` — **NE** TERMEK/KATEGORIA kész megoldást másolj.

- „Nézet: kurzusonként hallgatók száma és neveik listája.”
- „Városonként hány PERSON van (legalább 3).”
- „Autónként tulajdonosok LISTAGG.”

## LÉPÉSEK NULLÁRÓL

1. SELECT alapon csoportosítva
2. GROUP BY teljes
3. HAVING ha kell
4. CREATE VIEW AS …
5. SELECT a nézetből

## HA EZT ÍRJA

| Feladatszöveg | Teendő |
|---------------|--------|
| nézet / view | CREATE VIEW |
| X-enként / csoportonként | GROUP BY |
| legalább N a csoportban | HAVING |
| lista egy cellában | LISTAGG |

## TIPIKUS HIBÁK

- ORA-00979: kimaradt oszlop a GROUP BY-ból
- WHERE vs HAVING összekeverése
- LISTAGG túl hosszú → ORA-01489

## TIPIKUS ORA (ehhez a témához)

| Kód | Mit nézz |
|-----|----------|
| ORA-00979 | not a GROUP BY expression |
| ORA-01489 | LISTAGG too long |

## 10s ELLENŐRZÉS

- [ ] GROUP BY lista = nem aggregált SELECT oszlopok?
- [ ] Nézet SELECT-elhető?

## RÉSZLETES MAGYARÁZAT

→ [`../../13-VIEW/`](../../13-VIEW/) · [`../../08-GROUP-BY/`](../../08-GROUP-BY/)

## KAPCSOLÓDÓ

- [`../08-JOIN-ES-KAPCSOLAT/`](../08-JOIN-ES-KAPCSOLAT/)
- [`../09-TOP1-ES-SUBQUERY/`](../09-TOP1-ES-SUBQUERY/)

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
site:docs.oracle.com Oracle 11g CREATE VIEW GROUP BY HAVING LISTAGG syntax
```

```text
site:stackoverflow.com Oracle 11g CREATE VIEW GROUP BY HAVING LISTAGG -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference CREATE VIEW GROUP BY HAVING LISTAGG
```

```text
"Oracle 11g" CREATE VIEW GROUP BY HAVING LISTAGG ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```
