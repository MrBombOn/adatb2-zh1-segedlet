# Szétválogatás (multitable INSERT)

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

Egy SELECT-ből több célba: INSERT FIRST vagy INSERT ALL + WHEN.

## MIRE GONDOLJ

FIRST = első igaz ág; ALL = minden igaz ág. Dátum: TO_DATE maszk.

**Laikus:** szétválogatás ≈ amit a feladatszöveg magyarul kér; a SQL csak a pontos eszköz.

## MINIMÁLIS SZINTAXIS (11g)

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
INSERT FIRST
  WHEN <feltetel1> THEN INTO <t1> (<oszlopok>) VALUES (<…>)
  WHEN <feltetel2> THEN INTO <t2> (<oszlopok>) VALUES (<…>)
  ELSE INTO <t_egyeb> (<oszlopok>) VALUES (<…>)
SELECT <oszlopok> FROM <forras>;

INSERT ALL
  WHEN <feltetel1> THEN INTO <t1> VALUES (<…>)
  WHEN <feltetel2> THEN INTO <t2> VALUES (<…>)
SELECT <oszlopok> FROM <forras>;
```

## MIT ÍRHATOK (helyőrzők)

| Helyőrző | Mit írj | Jelölés | Példa gondolat |
|----------|---------|---------|----------------|
| `<feltetel1>` | WHEN feltétel | KÖTELEZŐ | hire_date < TO_DATE('2020-01-01','YYYY-MM-DD') |
| `<t1>` | Céltábla 1 | KÖTELEZŐ | OLD_ORDERS |
| `FIRST vs ALL` | Első igaz vs minden igaz | KÖTELEZŐ döntés | szöveg: „csak egybe”→FIRST |

## ÉRTÉKEK JELENTÉSE

| Érték / minta | Jelentés | Jelölés |
|---------------|----------|---------|
| `INSERT FIRST` | Első illeszkedő WHEN | **VALID** |
| `INSERT ALL + WHEN` | Minden illeszkedő WHEN | **VALID** |
| `TO_DATE(...,'YYYY-MM-DD')` | Dátum literál | **TIPIKUS** |

Jelölés: **KÖTELEZŐ** = a feladat/szintaxis kéri · **VALID** = 11g-ben elfogadott · **TIPIKUS** = gyakori lab · **KÖRNYEZETFÜGGŐ** = a lab dönti el.

## PÉLDA FELADATSZÖVEG (alternatív entitások)

Világok: `AUTHOR/BOOK, STUDENT/COURSE, CITY/PERSON, CUSTOMER/ORDER, CAR/OWNER` — **NE** TERMEK/KATEGORIA kész megoldást másolj.

- „A 2020 előtti ORDER-eket tedd OLD_ORDER-be, a többit NEW_ORDER-be.”
- „PERSON születési év szerint ARCH / CURRENT táblákba.”
- „BOOK kiadás éve < 2000 → CLASSIC, különben MODERN.”

## LÉPÉSEK NULLÁRÓL

1. Céltáblák léteznek-e?
2. FIRST vagy ALL?
3. WHEN feltételek + TO_DATE
4. SELECT forrás
5. COUNT célokban

## HA EZT ÍRJA

| Feladatszöveg | Teendő |
|---------------|--------|
| dátum szerint más táblába / szétválogatás | INSERT FIRST/ALL WHEN |
| ha … akkor ebbe a táblába | WHEN … THEN INTO |

## TIPIKUS HIBÁK

- FIRST/ALL összekeverése
- Dátum maszk nélkül
- Céltábla struktúra nem passzol

## TIPIKUS ORA (ehhez a témához)

| Kód | Mit nézz |
|-----|----------|
| ORA-01861 | dátum maszk |
| ORA-00947 | not enough values |

## 10s ELLENŐRZÉS

- [ ] Minden forrássor elhelyezve?
- [ ] ELSE kell-e?
- [ ] 11g — nincs modern dialect

## RÉSZLETES MAGYARÁZAT

→ [`../../09-DML/insert.md`](../../09-DML/insert.md) · [`../11-DATUM/`](../11-DATUM/)

## KAPCSOLÓDÓ

- [`../04-ADATFELTOLTES/`](../04-ADATFELTOLTES/)
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
site:docs.oracle.com Oracle 11g INSERT FIRST INSERT ALL WHEN multitable syntax
```

```text
site:stackoverflow.com Oracle 11g INSERT FIRST INSERT ALL WHEN multitable -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference INSERT FIRST INSERT ALL WHEN multitable
```

```text
"Oracle 11g" INSERT FIRST INSERT ALL WHEN multitable ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```
