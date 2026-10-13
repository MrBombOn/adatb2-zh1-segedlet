# ZH technikai menet (szabályzat-kompatibilis)

> Csak általános, szabályzatbarát lépések — **nem** konkrét intézményi vizsgaszabály kijátszása.

1. Belépés a lab / vizsgakörnyezetbe a hivatalos útmutató szerint  
2. Kapcsolódás az adatbázishoz a **kiadott** credentialdel / TNS-sel  
3. Ellenőrzés: `SELECT * FROM dual;`  
4. Feladatsor elolvasása → függőségi sorrend papíron  
5. DDL → DML → lekérdezések  
6. Hibánál: ORA kód olvasása, javítás, továbblépés  
7. Idő: könnyű pontok először  
8. Beadás / mentés a **hivatalos** csatornán  

**Ne:** idegen anyag bemásolása, tiltott eszköz, más munkájának használata.

## KERESÉS, HA ELAKADTAM

> **Figyelem:** Kerüld a MySQL / Postgres / SQL Server találatokat és a **12c+** megoldásokat (`FETCH FIRST`, `OFFSET … ROWS`, `IDENTITY`). Elsőbbség: hivatalos **Oracle 11g** dokumentáció.

Bemásolható keresők (5–10 mp):

```text
site:docs.oracle.com Oracle 11g connect Oracle 11g "PL/SQL Developer" TNS syntax
```

```text
site:stackoverflow.com Oracle 11g connect Oracle 11g "PL/SQL Developer" TNS -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference connect Oracle 11g "PL/SQL Developer" TNS
```

```text
"Oracle 11g" connect Oracle 11g "PL/SQL Developer" TNS ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```

```text
Oracle 11g XE connection TNS listener
```
