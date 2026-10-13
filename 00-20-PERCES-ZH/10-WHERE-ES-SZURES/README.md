# WHERE és szűrés

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

Sorszűrés WHERE-rel; NULL: IS NULL; LIKE / IN / BETWEEN.

## MIRE GONDOLJ

WHERE sorokra, HAVING csoportokra. Soha `= NULL`.

**Laikus:** csak azok ≈ amit a feladatszöveg magyarul kér; a SQL csak a pontos eszköz.

## MINIMÁLIS SZINTAXIS (11g)

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
SELECT <oszlopok>
FROM   <tabla>
WHERE  <o> = <e>
   AND <o> <> <e>
   AND <o> IN (<e1>, <e2>)
   AND <o> BETWEEN <a> AND <b>
   AND <o> LIKE '<minta%>'
   AND <o> IS NULL
   AND (<f1> OR <f2>);
```

## MIT ÍRHATOK (helyőrzők)

| Helyőrző | Mit írj | Jelölés | Példa gondolat |
|----------|---------|---------|----------------|
| `<feltetel>` | Logikai kifejezés | KÖTELEZŐ | status = 'OPEN' |
| `LIKE minta` | % és _ | VALID | 'A%' |

## ÉRTÉKEK JELENTÉSE

| Érték / minta | Jelentés | Jelölés |
|---------------|----------|---------|
| `IS NULL / IS NOT NULL` | NULL teszt | **KÖTELEZŐ NULL-nál** |
| `= NULL` | Soha nem igaz | **TILTOTT** |
| `BETWEEN` | Zárt intervallum | **VALID** |

Jelölés: **KÖTELEZŐ** = a feladat/szintaxis kéri · **VALID** = 11g-ben elfogadott · **TIPIKUS** = gyakori lab · **KÖRNYEZETFÜGGŐ** = a lab dönti el.

## PÉLDA FELADATSZÖVEG (alternatív entitások)

Világok: `AUTHOR/BOOK, STUDENT/COURSE, CITY/PERSON, CUSTOMER/ORDER, CAR/OWNER` — **NE** TERMEK/KATEGORIA kész megoldást másolj.

- „Csak az aktív COURSE-ok.”
- „PERSON ahol city IS NULL.”
- „ORDER dátum BETWEEN …”
- „CAR plate LIKE 'ABC%'.”

## LÉPÉSEK NULLÁRÓL

1. Írd a SELECT-et
2. WHERE feltételek AND/OR
3. NULL → IS NULL
4. Teszt COUNT

## HA EZT ÍRJA

| Feladatszöveg | Teendő |
|---------------|--------|
| csak azok / ahol | WHERE |
| hiányzik / nincs kitöltve | IS NULL |
| hasonló / kezdődik | LIKE |

## TIPIKUS HIBÁK

- = NULL
- AND/OR zárójel nélkül
- LIKE idézőjel nélkül

## TIPIKUS ORA (ehhez a témához)

| Kód | Mit nézz |
|-----|----------|
| ORA-00936 | missing expression |
| ORA-01722 | invalid number |

## 10s ELLENŐRZÉS

- [ ] NULL kezelés helyes?
- [ ] WHERE vs HAVING

## RÉSZLETES MAGYARÁZAT

→ [`../../04-SELECT/02-where.md`](../../04-SELECT/02-where.md) · [`../../05-FELTETELEK/`](../../05-FELTETELEK/)

## KAPCSOLÓDÓ

- [`../07-VIEW-ES-CSOPORTOSITAS/`](../07-VIEW-ES-CSOPORTOSITAS/)
- [`../11-DATUM/`](../11-DATUM/)

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
site:docs.oracle.com Oracle 11g WHERE IS NULL LIKE BETWEEN IN syntax
```

```text
site:stackoverflow.com Oracle 11g WHERE IS NULL LIKE BETWEEN IN -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference WHERE IS NULL LIKE BETWEEN IN
```

```text
"Oracle 11g" WHERE IS NULL LIKE BETWEEN IN ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```
