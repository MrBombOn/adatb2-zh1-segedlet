# Függőségi sorrend

**20 perc · GYORS**

## ASCII lánc (általános ZH)

```text
[USER / SCHEMA / QUOTA / GRANT]
            |
            v
    [CREATE TABLE szulo] -- PK
            |
            v
    [CREATE TABLE gyerek] -- FK → szulo
            |
            v
    [SEQUENCE] (ha kell ID)
            |
            v
    [INSERT szulo]  -->  [INSERT gyerek]
            |
            v
    [VIEW / MERGE / UPDATE]
            |
            v
    [SELECT / JOIN / GROUP BY / Top-N]
            |
            v
    [COMMIT] (ha a feladat / környezet kéri)
```

## Szabály

1. Amit más hivatkozik, **előbb** létezzen (szülő tábla, user, jog).  
2. FK-s INSERT előtt legyen szülő sor.  
3. VIEW a SELECT-képes táblák után.  
4. Lekérdezés legvégén — de ha elakadsz, előbb `SELECT` teszt kis lépésekben.

## Gyors ellenőrző

- [ ] User/jog kész?  
- [ ] Szülő tábla + PK?  
- [ ] Gyerek + FK?  
- [ ] Adat szülő→gyerek?  
- [ ] Lekérdezés?

## KERESÉS, HA ELAKADTAM

> **Figyelem:** Kerüld a MySQL / Postgres / SQL Server találatokat és a **12c+** megoldásokat (`FETCH FIRST`, `OFFSET … ROWS`, `IDENTITY`). Elsőbbség: hivatalos **Oracle 11g** dokumentáció.

Bemásolható keresők (5–10 mp):

```text
site:docs.oracle.com Oracle 11g foreign key parent child insert order syntax
```

```text
site:stackoverflow.com Oracle 11g foreign key parent child insert order -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference foreign key parent child insert order
```

```text
"Oracle 11g" foreign key parent child insert order ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```

```text
site:docs.oracle.com Oracle 11g referential integrity FOREIGN KEY
```

