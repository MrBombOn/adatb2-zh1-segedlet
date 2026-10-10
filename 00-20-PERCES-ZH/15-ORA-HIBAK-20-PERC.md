# ORA hibák – 20 perc

| Kód | Röviden | Mit nézz |
|-----|---------|----------|
| ORA-00904 | invalid identifier | oszlopnév |
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

**Módszer:** kód → sorpozíció → egyszerűsítsd a SQL-t.

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

```text
site:docs.oracle.com Oracle 11g ORA-00942
```

