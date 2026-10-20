# 20 PERCES ZH – HA SEMMIT NEM TUDSZ, EZT NYISD MEG

**Oracle Database 11g / 11g R2 ONLY** · Kliens: **PL/SQL Developer** · Placeholder minták (nem megoldásbank)

> Nincs TERMEK/KATEGORIA / KONYV/KOLCSONZES kész megoldás.
> Abszolút zero-knowledge: a feladatszövegből olvasol mindent — **soha** nem kell „előre tudnod” a sémát.

**Mappa:** ez a `20PERC/` one-stop. Canonical / részletes: [`../00-20-PERCES-ZH/`](../00-20-PERCES-ZH/) és [`../01-KORNYEZET/`](../01-KORNYEZET/)…[`../22-ZH/`](../22-ZH/).

---

## 0) Óvodás döntési tábla — mit csináljak?

| A papír ezt kéri (magyarul) | Nyisd / írd |
|-----------------------------|-------------|
| User / séma / jelszó / kvóta / jog | [`01-SEMA-ES-USER.md`](01-SEMA-ES-USER.md) |
| Hozz létre táblát | [`02-TABLA-LETREHOZAS.md`](02-TABLA-LETREHOZAS.md) |
| PK / FK / CHECK / NOT NULL | [`03-CONSTRAINT.md`](03-CONSTRAINT.md) |
| Vegyél fel / több sor egyszerre | [`04-ADATFELTOLTES.md`](04-ADATFELTOLTES.md) |
| Üres másolat / ha van–ha nincs / szétválogatás | [`05-MASOLAT-MERGE-SZETVALOGATAS.md`](05-MASOLAT-MERGE-SZETVALOGATAS.md) |
| Együtt / akkor is ha nincs pár | [`06-JOIN-ES-LEFT.md`](06-JOIN-ES-LEFT.md) |
| Csoportonként / legalább N / nézet | [`07-GROUP-HAVING-VIEW.md`](07-GROUP-HAVING-VIEW.md) |
| Leg… / top / akiknek van… | [`08-TOP1-SUBQUERY.md`](08-TOP1-SUBQUERY.md) |
| Dátum / mai nap / formátum | [`09-DATUM.md`](09-DATUM.md) |
| Módosíts / törölj / % / EXISTS | [`10-DML.md`](10-DML.md) |
| Rang / partíciónként összeg | [`11-ANALITIKUS.md`](11-ANALITIKUS.md) |
| Semmi se stimmel | [`12-ISMERETLEN-FELADAT.md`](12-ISMERETLEN-FELADAT.md) |
| Először: mit akar a feladat? | [`00-MIT-AKAR-A-FELADAT.md`](00-MIT-AKAR-A-FELADAT.md) |

**Jelölés:** **KÖTELEZŐ** = a feladat/szintaxis kéri · **VALID** = 11g OK · **TIPIKUS** = gyakori lab · **KÖRNYEZETFÜGGŐ** = a lab dönti el (pl. tablespace — **USERS nem kötelező**).

**TILOS 11g-n:** `FETCH FIRST`, `OFFSET … ROWS`, `LIMIT`, `IDENTITY`, `IF EXISTS` (DROP USER), MySQL backtick.

---

## 1) P0 témák — szintaxis HELYBEN

### 1.1 USER / séma / DROP

**HA EZT LÁTOD:** hozz létre usert · ha már létezik töröld · adj jogot · kvóta

**EZT JELENTI:** USER ≈ séma; 11g-n nincs IF EXISTS

**EZ KELL:** ellenőrzés → DROP USER … CASCADE (ha kell) → CREATE USER → QUOTA → GRANT

**ÍRD EZT:**

```sql
SELECT username FROM all_users WHERE username = UPPER('<user_nev>');
-- ha van sor:
DROP USER <user_nev> CASCADE;
-- nincs IF EXISTS 11g-n

CREATE USER <user_nev> IDENTIFIED BY <jelszo>;
ALTER USER <user_nev> QUOTA <meret> ON <tablespace_nev>;  -- KÖRNYEZETFÜGGŐ
GRANT CREATE SESSION, CREATE TABLE TO <user_nev>;
```

**MIT CSERÉLJEK:** `<user_nev>`, `<jelszo>`, `<meret>`, `<tablespace_nev>`

**HONNAN VESZEM:** feladat (név/jelszó) · tablespace = **KÖRNYEZETFÜGGŐ** (gyakran USERS, de nem kötelező)

**FUTTATÁS:** SYSTEM/privilegizált userrel; majd csatlakozz az új userrel

**10s ELLENŐRZÉS:** `SELECT user FROM dual;` · `all_users` újra

**HA HIBÁT KAPSZ:** ORA-01918 / ORA-01940 / ORA-01950 → jog / session / quota

**RÉSZLETESEN:** [`../00-20-PERCES-ZH/01-SEMA-USER/DROP-USER.md`](../00-20-PERCES-ZH/01-SEMA-USER/DROP-USER.md)
### 1.2 CREATE TABLE + típus

**HA EZT LÁTOD:** hozd létre a … táblát · oszlopok · azonosító

**EZT JELENTI:** tábla = oszlopok + típusok; ID: SEQUENCE (nem IDENTITY)

**EZ KELL:** CREATE TABLE + típus-döntés

**ÍRD EZT:**

```sql
CREATE TABLE <tabla> (
  <id>     NUMBER        NOT NULL,
  <nev>    VARCHAR2(<n>) NOT NULL,
  <datum>  DATE,
  <szulo>  NUMBER,
  CONSTRAINT <pk_nev> PRIMARY KEY (<id>)
);
CREATE SEQUENCE <seq> START WITH 1 INCREMENT BY 1;
```

**MIT CSERÉLJEK:** `NUMBER` / `VARCHAR2(n)` / `DATE` / `CHAR(1)`

**HONNAN VESZEM:** oszlopnevek = **feladat**; hossz = **feladat** vagy VALID tipikus 50/100/255

**FUTTATÁS:** a saját sémauserrel

**10s ELLENŐRZÉS:** `DESC <tabla>;`

**HA HIBÁT KAPSZ:** ORA-00955 név ütközik · ORA-02260 PK

**RÉSZLETESEN:** [`../00-20-PERCES-ZH/02-TABLA-LETREHOZAS/README.md`](../00-20-PERCES-ZH/02-TABLA-LETREHOZAS/README.md)
### Adattípus döntési tábla

| Fogalom a szövegben | Típus (VALID) |
|---------------------|---------------|
| azonosító / kód szám | `NUMBER` |
| név / cím / szöveg | `VARCHAR2(n)` |
| dátum / születés / határidő | `DATE` |
| igen/nem · jel | `CHAR(1)` vagy `VARCHAR2(1)` + CHECK |
| pénz / ár | `NUMBER(p,s)` ha a feladat kéri |

### 1.3 Constraint (PK/FK/CHECK LENGTH)

**HA EZT LÁTOD:** elsődleges kulcs · idegen kulcs · legalább N karakter · NOT NULL

**EZT JELENTI:** szabály az oszlopon / táblán

**EZ KELL:** CONSTRAINT … PRIMARY KEY / FOREIGN KEY / CHECK

**ÍRD EZT:**

```sql
ALTER TABLE <tabla> ADD CONSTRAINT <ck_nev>
  CHECK (LENGTH(<szoveg_oszlop>) >= <n>);
-- vagy CREATE TABLE-ben:
-- CONSTRAINT <fk_nev> FOREIGN KEY (<fk>) REFERENCES <szulo>(<pk>)
```

**MIT CSERÉLJEK:** `LENGTH(...) >= n` ha „legalább N karakter”

**HONNAN VESZEM:** n, oszlop = **feladat**; constraint név = **TIPIKUS** (`ck_…`, `pk_…`, `fk_…`)

**FUTTATÁS:** DDL után

**10s ELLENŐRZÉS:** rossz hossz INSERT → ORA-02290

**HA HIBÁT KAPSZ:** ORA-02290 CHECK · ORA-02291 FK

**RÉSZLETESEN:** [`../00-20-PERCES-ZH/03-CONSTRAINT/CHECK-LENGTH.md`](../00-20-PERCES-ZH/03-CONSTRAINT/CHECK-LENGTH.md)
### 1.4 INSERT / INSERT ALL

**HA EZT LÁTOD:** vegyél fel · több rekord · több táblába egyszerre

**EZT JELENTI:** DML adatbevitel

**EZ KELL:** INSERT ALL … SELECT … FROM dual

**ÍRD EZT:**

```sql
INSERT ALL
  INTO <t1> (<o1>, <o2>) VALUES (<v11>, <v12>)
  INTO <t1> (<o1>, <o2>) VALUES (<v21>, <v22>)
  INTO <t2> (<a>, <b>)   VALUES (<v31>, <v32>)
SELECT 1 FROM dual;
```

**MIT CSERÉLJEK:** tábla/oszlop/érték a feladatból; FK sorrend: szülő előbb

**HONNAN VESZEM:** **feladat**

**FUTTATÁS:** COMMIT ha a menet kéri

**10s ELLENŐRZÉS:** `SELECT COUNT(*) FROM <t1>;`

**HA HIBÁT KAPSZ:** ORA-02291 FK · ORA-00001 UK

**RÉSZLETESEN:** [`../00-20-PERCES-ZH/04-ADATFELTOLTES/INSERT-ALL-TOBB-TABLABA.md`](../00-20-PERCES-ZH/04-ADATFELTOLTES/INSERT-ALL-TOBB-TABLABA.md)
### 1.5 CTAS / MERGE / szétválogatás

**HA EZT LÁTOD:** üres másolat · ha még nincs · dátum szerint más táblába

**EZT JELENTI:** struktúra másolás / upsert / feltételes multitable INSERT

**EZ KELL:** CTAS `WHERE 1=0` · MERGE · INSERT FIRST/ALL

**ÍRD EZT:**

```sql
CREATE TABLE <uj> AS SELECT * FROM <forras> WHERE 1 = 0;
-- figyelmeztetés: constraint-ek NEM mind jönnek át

MERGE INTO <cel> c
USING (SELECT <kulcs>, <adat> FROM dual) s
ON (c.<kulcs> = s.<kulcs>)
WHEN NOT MATCHED THEN INSERT (<kulcs>, <adat>) VALUES (s.<kulcs>, s.<adat>);

INSERT FIRST
  WHEN <felt1> THEN INTO <t1> VALUES (...)
  WHEN <felt2> THEN INTO <t2> VALUES (...)
  ELSE INTO <t_egyeb> VALUES (...)
SELECT ... FROM <forras>;
```

**MIT CSERÉLJEK:** `1=0` = üres; MERGE ágak a szöveg szerint

**HONNAN VESZEM:** **feladat**

**FUTTATÁS:** sorok száma / MERGE eredmény

**10s ELLENŐRZÉS:** `SELECT COUNT(*) FROM <uj>;` = 0 CTAS-nél

**HA HIBÁT KAPSZ:** ORA-00942 · ORA-30926 MERGE

**RÉSZLETESEN:** [`../00-20-PERCES-ZH/05-MASOLAT-ES-MERGE/README.md`](../00-20-PERCES-ZH/05-MASOLAT-ES-MERGE/README.md)
### 1.6 JOIN / LEFT + nincs pár

**HA EZT LÁTOD:** együtt · kapcsolódó · *azokat is… semmi* · *függetlenül a kapcsolattól* · *nulla kapcsolódó* · *hiányában is*

**EZT JELENTI:** INNER = csak pár; LEFT = bal oldal akkor is ha jobb NULL

**EZ KELL:** LEFT JOIN + IS NULL **vagy** COUNT(jobb.pk)=0

**ÍRD EZT:**

```sql
SELECT <bal>.*
FROM   <bal>
LEFT JOIN <jobb> ON <jobb>.<fk> = <bal>.<pk>
WHERE  <jobb>.<pk> IS NULL;

-- darabszámmal:
SELECT <bal>.<pk>, COUNT(<jobb>.<pk>) AS db
FROM   <bal>
LEFT JOIN <jobb> ON <jobb>.<fk> = <bal>.<pk>
GROUP BY <bal>.<pk>
HAVING COUNT(<jobb>.<pk>) = 0;
```

**MIT CSERÉLJEK:** **CSAPDA:** `COUNT(*)` — NULL pároknál is 1-et ad GROUP után. Használj `COUNT(<jobb>.<pk>)`.

**HONNAN VESZEM:** tábla/kulcs = **feladat**

**FUTTATÁS:** LEFT-es sorok: jobb oszlop NULL

**10s ELLENŐRZÉS:** van-e olyan bal sor, aminek nincs jobbja

**HA HIBÁT KAPSZ:** ORA-00904 oszlopnév

**RÉSZLETESEN:** [`../00-20-PERCES-ZH/08-JOIN-ES-KAPCSOLAT/LEFT-JOIN-COUNT-NULL.md`](../00-20-PERCES-ZH/08-JOIN-ES-KAPCSOLAT/LEFT-JOIN-COUNT-NULL.md)
### 1.7 GROUP BY / HAVING / VIEW

**HA EZT LÁTOD:** csoportonként · legalább/pontosan/több mint N · nézet

**EZT JELENTI:** aggregálás + csoportszűrés; HAVING a csoport eredményére

**EZ KELL:** GROUP BY + HAVING COUNT(*) <operator> <n>

**ÍRD EZT:**

```sql
SELECT <c>, COUNT(*) AS db
FROM   <t>
GROUP BY <c>
HAVING COUNT(*) <operator> <n>;

CREATE OR REPLACE VIEW <nezet> AS
SELECT <c>, COUNT(*) AS db
FROM   <t>
GROUP BY <c>;
```

**MIT CSERÉLJEK:** operátor: kevesebb mint=`<` · legfeljebb=`<=` · pontosan=`=` · legalább=`>=` · több mint=`>`

**HONNAN VESZEM:** **feladat** — ne fix `>=`

**FUTTATÁS:** nézet után `SELECT * FROM <nezet>;`

**10s ELLENŐRZÉS:** minden nem aggregált SELECT-oszlop a GROUP BY-ban

**HA HIBÁT KAPSZ:** ORA-00979 · ORA-00937

**RÉSZLETESEN:** [`../00-20-PERCES-ZH/07-VIEW-ES-CSOPORTOSITAS/HAVING-COUNT.md`](../00-20-PERCES-ZH/07-VIEW-ES-CSOPORTOSITAS/HAVING-COUNT.md)
### WHERE vs HAVING

| Szűrés tárgya | Hol |
|---------------|-----|
| Egyedi sor (még GROUP előtt) | **WHERE** |
| Csoport / aggregátum (COUNT, SUM…) | **HAVING** |

### 1.8 Top-1 / subquery (ROWNUM)

**HA EZT LÁTOD:** leg… · top N · átlag felett · akik szerepelnek…

**EZT JELENTI:** Top-N 11g-n: ROWNUM / ROW_NUMBER — **TILOS FETCH FIRST**

**EZ KELL:** külső szűrés ROWNUM / rn

**ÍRD EZT:**

```sql
SELECT * FROM (
  SELECT <oszlopok> FROM <tabla> ORDER BY <rendezes> DESC
) WHERE ROWNUM <= <n>;

SELECT * FROM (
  SELECT <oszlopok>,
         ROW_NUMBER() OVER (ORDER BY <rendezes> DESC) AS rn
  FROM   <tabla>
) WHERE rn = 1;

SELECT <oszlopok> FROM <tabla> t
WHERE EXISTS (
  SELECT 1 FROM <masik> m WHERE m.<fk> = t.<pk>
);
```

**MIT CSERÉLJEK:** `ORDER BY` a belső SELECT-ben; ROWNUM kívül

**HONNAN VESZEM:** **feladat**

**FUTTATÁS:** 1 (vagy N) sor jön-e

**10s ELLENŐRZÉS:** FETCH FIRST megjelenik? → töröld, cseréld ROWNUM-ra

**HA HIBÁT KAPSZ:** ORA-00933

**RÉSZLETESEN:** [`../00-20-PERCES-ZH/09-TOP1-ES-SUBQUERY/README.md`](../00-20-PERCES-ZH/09-TOP1-ES-SUBQUERY/README.md)
### 1.9 Dátum / TRUNC

**HA EZT LÁTOD:** mai nap · idő nélkül · TO_DATE / TO_CHAR

**EZT JELENTI:** `DATE` tartalmazhat időt; napra vágás: TRUNC

**EZ KELL:** TRUNC(SYSDATE) / TO_DATE

**ÍRD EZT:**

```sql
SELECT *
FROM   <tabla>
WHERE  TRUNC(<datum_oszlop>) = TRUNC(SYSDATE);

SELECT TO_CHAR(<datum>, '<formatum>') FROM <tabla>;
-- pl. formatum: YYYY.MM.DD
```

**MIT CSERÉLJEK:** `TRUNC` ha nap kell idő nélkül

**HONNAN VESZEM:** **feladat** formátum / oszlop

**FUTTATÁS:** futtasd a SELECT-et

**10s ELLENŐRZÉS:** mai napra szűrt sorok

**HA HIBÁT KAPSZ:** ORA-01861 formátum

**RÉSZLETESEN:** [`../00-20-PERCES-ZH/11-DATUM/DATUM-IDOPONT-NELKUL.md`](../00-20-PERCES-ZH/11-DATUM/DATUM-IDOPONT-NELKUL.md)
### 1.10 DML — % UPDATE + EXISTS

**HA EZT LÁTOD:** N%-kal emeld · csak akiknek van kapcsolódó…

**EZT JELENTI:** UPDATE értékkel / alselecttel

**EZ KELL:** aritmetika + EXISTS (vagy IN)

**ÍRD EZT:**

```sql
UPDATE <tabla> t
SET    t.<szam> = t.<szam> * (1 + <szazalek>/100)
WHERE  EXISTS (
  SELECT 1 FROM <kapcsolodo> k WHERE k.<fk> = t.<pk>
);
```

**MIT CSERÉLJEK:** `+` emelés, `-` csökkentés a szöveg szerint; EXISTS vs IN

**HONNAN VESZEM:** **feladat**

**FUTTATÁS:** futtasd; COMMIT ha a menet kéri

**10s ELLENŐRZÉS:** `SELECT` előtte/utána

**HA HIBÁT KAPSZ:** ORA-01407 NOT NULL

**RÉSZLETESEN:** [`../00-20-PERCES-ZH/12-DML/SZAZALEKOS-MODOSITAS.md`](../00-20-PERCES-ZH/12-DML/SZAZALEKOS-MODOSITAS.md)
### 1.11 LIKE kis/nagybetű + 5 komponens

**HA EZT LÁTOD:** tartalmazza … · nem számít a kis/nagy · LEFT+COUNT+HAVING együtt

**EZT JELENTI:** case-insensitive: UPPER/LOWER mindkét oldalon

**EZ KELL:** UPPER … LIKE UPPER · vagy OT-komponenses váz

**ÍRD EZT:**

```sql
WHERE UPPER(<oszlop>) LIKE UPPER('%<minta>%')

-- 5 komponens:
SELECT <bal>.<pk>, <bal>.<nev>, COUNT(<jobb>.<pk>) AS db
FROM   <bal>
LEFT JOIN <jobb> ON <jobb>.<fk> = <bal>.<pk>
WHERE  UPPER(<bal>.<szoveg>) LIKE UPPER('%<minta>%')
GROUP BY <bal>.<pk>, <bal>.<nev>
HAVING COUNT(<jobb>.<pk>) <operator> <n>;
```

**MIT CSERÉLJEK:** `<operator>`: `<` `<=` `=` `>=` `>` a szöveg szerint

**HONNAN VESZEM:** **feladat**

**FUTTATÁS:** futtasd a SELECT-et

**10s ELLENŐRZÉS:** minta talál-e; darab küszöb stimmel-e

**HA HIBÁT KAPSZ:** COUNT(*) csapda LEFT-nél

**RÉSZLETESEN:** [`../00-20-PERCES-ZH/00-START/OT-KOMPONENSES-LEKERDEZES.md`](../00-20-PERCES-ZH/00-START/OT-KOMPONENSES-LEKERDEZES.md)
### 1.12 Analitikus — SUM OVER + ROW_NUMBER

**HA EZT LÁTOD:** csoportonként rang · minden sor mellett összeg

**EZT JELENTI:** OVER (PARTITION BY …) — GROUP nem ugyanaz mint PARTITION

**EZ KELL:** MÓD A (minden sor) vagy MÓD B (rn=1)

**ÍRD EZT:**

```sql
-- MÓD A: minden sor marad (NINCS WHERE rn=1)
SELECT e.<oszlopok>,
       SUM(e.<n>) OVER (PARTITION BY e.<p>) AS part_sum,
       ROW_NUMBER() OVER (PARTITION BY e.<p> ORDER BY e.<r> DESC) AS rn
FROM   <tabla> e;

-- MÓD B: csak csoport első
SELECT * FROM (
  SELECT e.<oszlopok>,
         SUM(e.<n>) OVER (PARTITION BY e.<p>) AS part_sum,
         ROW_NUMBER() OVER (PARTITION BY e.<p> ORDER BY e.<r> DESC) AS rn
  FROM   <tabla> e
) WHERE rn = 1;
```

**MIT CSERÉLJEK:** minden sor? → A · csak győztes? → B

**HONNAN VESZEM:** **feladat**

**FUTTATÁS:** futtasd; nézd a sorok számát

**10s ELLENŐRZÉS:** sorok száma: A ≈ bemenet; B ≈ partíciók száma

**HA HIBÁT KAPSZ:** **TILOS** FETCH FIRST

**RÉSZLETESEN:** [`../00-20-PERCES-ZH/18-ANALITIKUS/INTEGRATED-SUM-ROW-NUMBER.md`](../00-20-PERCES-ZH/18-ANALITIKUS/INTEGRATED-SUM-ROW-NUMBER.md)
### GROUP BY vs PARTITION BY

| | GROUP BY | PARTITION BY (OVER) |
|--|----------|---------------------|
| Sorok | Összevon (kevesebb sor) | Megtartja a sorokat |
| Tipikus | COUNT/SUM egy csoportban | „minden sor mellett csoportösszeg” |

---

## 2) Eredeti ZH feladattípusok 1–8 (általános minták)

> NEM szó szerinti feladatsor. NEM kész megoldás.

| # | Típus | Szövegjel | Írd / nyisd |
|---|-------|-----------|-------------|
| 1 | User / séma / jog | hozz létre usert, kvóta, GRANT | §1.1 · [`01-SEMA-ES-USER.md`](01-SEMA-ES-USER.md) |
| 2 | Tábla + constraint | CREATE TABLE, PK, FK, CHECK | §1.2–1.3 |
| 3 | Tömeges adat | több rekord egyszerre | §1.4 |
| 4 | Üres másolat | struktúra adat nélkül | §1.5 CTAS |
| 5 | Feltételes szétválogatás | dátum szerint más táblába | §1.5 INSERT FIRST |
| 6 | MERGE / upsert | ha még nincs / ha van | §1.5 MERGE |
| 7 | Nézet + aggregálás | VIEW, GROUP, lista | §1.7 |
| 8 | Lekérdezés / JOIN / Top-N | listázd, pár nélkül, leg… | §1.6 · §1.8 |

Részletes: [`../23-KORABBI-ZH-MINTAK/00-mit-tesztelt-a-korabbi-zh.md`](../23-KORABBI-ZH-MINTAK/00-mit-tesztelt-a-korabbi-zh.md)

---

## 3) Pót ZH minták 0–6

| # | Minta | Szövegjel | Hol |
|---|-------|-----------|-----|
| 0 | DROP USER + CREATE | ha már létezik | §1.1 |
| 1 | CHECK LENGTH | legalább N karakter | §1.3 |
| 2 | INSERT ALL több tábla | több táblába egyszerre | §1.4 |
| 3 | TRUNC nap | mai nap / idő nélkül | §1.9 |
| 4 | %-os UPDATE | N%-kal emeld/csökkentsd | §1.10 |
| 5 | UPDATE + EXISTS | akiknek van … | §1.10 |
| 6 | LEFT/HAVING/analitikus | nincs pár · legalább N · rang | §1.6 · §1.7 · §1.12 |

Részletes: [`../23-KORABBI-ZH-MINTAK/01-pot-zh-mit-tesztelt.md`](../23-KORABBI-ZH-MINTAK/01-pot-zh-mit-tesztelt.md)

---

## 4) Kombinált feladattípusok A–H (teljes váz)

### A) LEFT + COUNT + HAVING + LIKE

```sql
SELECT <bal>.<pk>, <bal>.<nev>, COUNT(<jobb>.<pk>) AS db
FROM   <bal>
LEFT JOIN <jobb> ON <jobb>.<fk> = <bal>.<pk>
WHERE  UPPER(<bal>.<szoveg>) LIKE UPPER('%<minta>%')
GROUP BY <bal>.<pk>, <bal>.<nev>
HAVING COUNT(<jobb>.<pk>) <operator> <n>;
```

### B) UPDATE + EXISTS

```sql
UPDATE <tabla> t
SET    t.<oszlop> = <uj_ertek>
WHERE  EXISTS (SELECT 1 FROM <kapcs> k WHERE k.<fk> = t.<pk>);
```

### C) SUM OVER + ROW_NUMBER (MÓD B győztes)

```sql
SELECT * FROM (
  SELECT e.*,
         SUM(e.<n>) OVER (PARTITION BY e.<p>) AS part_sum,
         ROW_NUMBER() OVER (PARTITION BY e.<p> ORDER BY e.<r> DESC) AS rn
  FROM <tabla> e
) WHERE rn = 1;
```

### D) CHECK LENGTH + CREATE TABLE

```sql
CREATE TABLE <tabla> (
  <id>  NUMBER PRIMARY KEY,
  <nev> VARCHAR2(<max>),
  CONSTRAINT <ck> CHECK (LENGTH(<nev>) >= <min>)
);
```

### E) INSERT ALL több különböző táblába

```sql
INSERT ALL
  INTO <t1> (<o…>) VALUES (<v…>)
  INTO <t2> (<o…>) VALUES (<v…>)
SELECT 1 FROM dual;
```

### F) TRUNC + szűrés + listázás

```sql
SELECT <oszlopok>
FROM   <tabla>
WHERE  TRUNC(<datum>) = TRUNC(SYSDATE);
```

### G) Százalékos UPDATE

```sql
UPDATE <tabla>
SET    <szam> = <szam> * (1 + <szazalek>/100)
WHERE  <feltetel>;
```

### H) DROP USER ellenőrzés + CREATE + GRANT

```sql
SELECT username FROM all_users WHERE username = UPPER('<user_nev>');
DROP USER <user_nev> CASCADE;   -- csak ha létezik; nincs IF EXISTS
CREATE USER <user_nev> IDENTIFIED BY <jelszo>;
ALTER USER <user_nev> QUOTA <meret> ON <tablespace_nev>;  -- KÖRNYEZETFÜGGŐ
GRANT CREATE SESSION, CREATE TABLE TO <user_nev>;
```

---

## 5) Gyors csapdák

| Csapda | Helyes |
|--------|--------|
| `COUNT(*)` LEFT „nincs pár”-nál | `COUNT(<jobb>.<pk>)` |
| `WHERE rn = 1` amikor minden sor kell | MÓD A — nincs szűrés |
| Fix `HAVING … >=` | Olvasd: `<` `<=` `=` `>=` `>` |
| `FETCH FIRST` | `ROWNUM` / `ROW_NUMBER` |
| `IF EXISTS` DROP USER | `all_users` check → `DROP … CASCADE` |
| Tablespace = mindig USERS | **KÖRNYEZETFÜGGŐ** — nem kötelező |

---

## 6) További fájlok ebben a mappában

| Fájl | Mire |
|------|------|
| [`00-MIT-AKAR-A-FELADAT.md`](00-MIT-AKAR-A-FELADAT.md) | Magyar ige → eszköz |
| [`01-SEMA-ES-USER.md`](01-SEMA-ES-USER.md) … [`12-ISMERETLEN-FELADAT.md`](12-ISMERETLEN-FELADAT.md) | Téma-lapok |
| [`AUDIT.md`](AUDIT.md) | 11g / link / TILTOTT checklist |

Ha elakadtál a részletes fán: [`../00-20-PERCES-ZH/00-START/README.md`](../00-20-PERCES-ZH/00-START/README.md)
