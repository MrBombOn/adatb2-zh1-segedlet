# Constraint gyorsválasztó

**20 perc · GYORS** · Részletes: [`11-CONSTRAINTS/`](../11-CONSTRAINTS/)

## Döntés
| Szöveg | Constraint |
|--------|------------|
| egyértelmű azonosító | PRIMARY KEY |
| hivatkozzon másik táblára | FOREIGN KEY |
| egyedi, de nem PK | UNIQUE |
| ne lehessen üres | NOT NULL |
| értékfeltétel ugyanabban a sorban | CHECK |

## Named constraints konvenció (javasolt)
> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
CONSTRAINT pk_<tabla> PRIMARY KEY (<oszlop>)
CONSTRAINT fk_<gyerek>_<szulo> FOREIGN KEY (<oszlop>) REFERENCES <szulo>(<oszlop>)
CONSTRAINT uk_<tabla>_<oszlop> UNIQUE (<oszlop>)
CONSTRAINT ck_<tabla>_<oszlop> CHECK (<feltetel>)
```

## Minta
```sql
ALTER TABLE <gyerek> ADD CONSTRAINT fk_<gyerek>_<szulo>
  FOREIGN KEY (<fk_oszlop>) REFERENCES <szulo>(<pk_oszlop>);
```

## KERESÉS, HA ELAKADTAM

> **Figyelem:** Kerüld a MySQL / Postgres / SQL Server találatokat és a **12c+** megoldásokat (`FETCH FIRST`, `OFFSET … ROWS`, `IDENTITY`). Elsőbbség: hivatalos **Oracle 11g** dokumentáció.

Bemásolható keresők (5–10 mp):

```text
site:docs.oracle.com Oracle 11g PRIMARY KEY FOREIGN KEY UNIQUE CHECK NOT NULL syntax
```

```text
site:stackoverflow.com Oracle 11g PRIMARY KEY FOREIGN KEY UNIQUE CHECK NOT NULL -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference PRIMARY KEY FOREIGN KEY UNIQUE CHECK NOT NULL
```

```text
"Oracle 11g" PRIMARY KEY FOREIGN KEY UNIQUE CHECK NOT NULL ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```

```text
site:docs.oracle.com Oracle 11g constraint ALTER TABLE ADD CONSTRAINT
```

