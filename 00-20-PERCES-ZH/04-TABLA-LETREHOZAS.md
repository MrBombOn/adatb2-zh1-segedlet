# Tábla létrehozás

**20 perc · GYORS réteg** · Részletes: [`10-DDL/create-table.md`](../10-DDL/create-table.md)

## Magyar szinonimák (feladatszöveg)
hozz létre táblát / oszlopok / adattípusok / kötelező mező

## MI KELL? (1 mondat)
CREATE TABLE + típusok + (gyakran) constraint-ek.

## Kitöltendő szintaktikai minta
> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
CREATE TABLE <tabla> (
  <id_oszlop>   NUMBER       NOT NULL,
  <nev_oszlop>  VARCHAR2(<n>) NOT NULL,
  <datum_oszlop> DATE,
  <szulo_id>    NUMBER,
  CONSTRAINT <pk_nev> PRIMARY KEY (<id_oszlop>)
);
```

## TIPIKUS HIBA
Fenntartott szó névként; hiányzó vessző; 12c IDENTITY használata (TILOS itt).

## ELLENŐRZÉS (10 mp)
DESC / lekérdezés `user_tables`-ből; próbáld az INSERT-et.

## 11g ID
```sql
CREATE SEQUENCE <seq_nev> START WITH 1 INCREMENT BY 1;
-- INSERT-nél: <seq_nev>.NEXTVAL
```
