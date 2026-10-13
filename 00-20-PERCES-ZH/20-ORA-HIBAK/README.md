# ORA hibák – gyors

**P0 · GYORS** · Globális lista + topic-kötött ORA a témamappákban.

## HOL TALÁLOM?

| Kell | Hol |
|------|-----|
| Gyors kód→javítás | ez a táblázat |
| Téma szerinti ORA | pl. [`../01-SEMA-USER/`](../01-SEMA-USER/) |
| Részletes | [`../../18-HIBAK/`](../../18-HIBAK/) |

## GYORS TÁBLÁZAT

| Kód | Röviden | Mit nézz |
|-----|---------|----------|
| ORA-00904 | invalid identifier | oszlopnév / alias |
| ORA-00933 | SQL command not properly ended | szintaxis |
| ORA-00936 | missing expression | vessző / lista |
| ORA-00942 | table or view does not exist | név / jog / séma |
| ORA-00979 | not a GROUP BY expression | GROUP BY lista |
| ORA-01400 | cannot insert NULL | NOT NULL |
| ORA-00001 | unique constraint | duplikált kulcs |
| ORA-02291 | parent key not found | FK szülő |
| ORA-02292 | child record found | előbb gyerek |
| ORA-01861 | literal does not match format | TO_DATE maszk |
| ORA-12899 | value too large | VARCHAR2 hossz |
| ORA-01950 | no privileges on tablespace | QUOTA |
| ORA-01031 | insufficient privileges | GRANT |
| ORA-01489 | result of string concat is too long | LISTAGG |
| ORA-01427 | single-row subquery returns more | `=` helyett IN |

**Módszer:** kód → sorpozíció → egyszerűsítsd a SQL-t.

## 10s ELLENŐRZÉS

- [ ] Elolvastad az ORA üzenet **szövegét** is?
- [ ] Nem 12c+ szintaxist erőltetsz?

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
site:docs.oracle.com Oracle 11g ORA-00942 ORA-02291 ORA-00979 syntax
```

```text
site:stackoverflow.com Oracle 11g ORA-00942 ORA-02291 ORA-00979 -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference ORA-00942 ORA-02291 ORA-00979
```

```text
"Oracle 11g" ORA-00942 ORA-02291 ORA-00979 ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```
