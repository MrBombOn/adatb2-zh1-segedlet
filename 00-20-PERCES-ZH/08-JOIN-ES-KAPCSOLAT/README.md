# JOIN és kapcsolat

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

Több tábla összekapcsolása. „Akkor is ha nincs pár” → LEFT JOIN (+ IS NULL).

## MIRE GONDOLJ

FK = szabály az adatokra; JOIN = lekérdezés. ON feltétel: gyerek.fk = szulo.pk.

**Laikus:** tartozik ≈ amit a feladatszöveg magyarul kér; a SQL csak a pontos eszköz.

## MINIMÁLIS SZINTAXIS (11g)

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
SELECT <a>.<oszlopok>, <b>.<oszlopok>
FROM   <a>
JOIN   <b> ON <b>.<fk> = <a>.<pk>;

SELECT <bal>.*, <jobb>.*
FROM   <bal>
LEFT JOIN <jobb> ON <jobb>.<fk> = <bal>.<pk>
WHERE  <jobb>.<pk> IS NULL;   -- nincs pár
```

## MIT ÍRHATOK (helyőrzők)

| Helyőrző | Mit írj | Jelölés | Példa gondolat |
|----------|---------|---------|----------------|
| `<a>, <b>` | Táblák / aliasok | KÖTELEZŐ | author a, book b |
| `ON …` | Kapcsoló feltétel | KÖTELEZŐ | b.author_id = a.author_id |

## ÉRTÉKEK JELENTÉSE

| Érték / minta | Jelentés | Jelölés |
|---------------|----------|---------|
| `INNER JOIN / JOIN` | Csak párnál | **VALID** |
| `LEFT JOIN` | Bal megmarad | **VALID** |
| `WHERE jobb.pk IS NULL` | Nincs pár szűrés | **TIPIKUS** |

Jelölés: **KÖTELEZŐ** = a feladat/szintaxis kéri · **VALID** = 11g-ben elfogadott · **TIPIKUS** = gyakori lab · **KÖRNYEZETFÜGGŐ** = a lab dönti el.

## PÉLDA FELADATSZÖVEG (alternatív entitások)

Világok: `AUTHOR/BOOK, STUDENT/COURSE, CITY/PERSON, CUSTOMER/ORDER, CAR/OWNER` — **NE** TERMEK/KATEGORIA kész megoldást másolj.

- „Könyvek szerző nevével.” → BOOK JOIN AUTHOR
- „Szerzők könyv nélkül.” → AUTHOR LEFT JOIN BOOK WHERE book_id IS NULL
- „Hallgatók kurzusai.” → STUDENT JOIN ENROLLMENT JOIN COURSE
- „Városok személy nélkül.” → CITY LEFT JOIN PERSON …
- „Autók tulajdonossal / tulajdonos autó nélkül.” → CAR/OWNER

## LÉPÉSEK NULLÁRÓL

1. Rajzold 1:N
2. Válaszd INNER vs LEFT
3. Írd az ON-t
4. „nincs pár” ágnál IS NULL
5. Teszt: szorzás?

## HA EZT ÍRJA

| Feladatszöveg | Teendő |
|---------------|--------|
| tartozik / együtt / neve és… | JOIN |
| akkor is ha nincs / minden X Y nélkül | LEFT JOIN + IS NULL |

## TIPIKUS HIBÁK

- Cartesian szorzat (hiányzó ON)
- WHERE a LEFT-et INNER-ré teszi rossz helyen
- FK és JOIN összekeverése

## TIPIKUS ORA (ehhez a témához)

| Kód | Mit nézz |
|-----|----------|
| ORA-00904 | oszlop/alias |
| ORA-00942 | tábla |

## 10s ELLENŐRZÉS

- [ ] ON a helyes kulcsokra?
- [ ] LEFT + IS NULL a „nincs” ágon?

## RÉSZLETES MAGYARÁZAT

→ [`../../07-JOIN/`](../../07-JOIN/)

## KAPCSOLÓDÓ

- [`../03-CONSTRAINT/`](../03-CONSTRAINT/)
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
site:docs.oracle.com Oracle 11g JOIN LEFT JOIN ON IS NULL syntax
```

```text
site:stackoverflow.com Oracle 11g JOIN LEFT JOIN ON IS NULL -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference JOIN LEFT JOIN ON IS NULL
```

```text
"Oracle 11g" JOIN LEFT JOIN ON IS NULL ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```
