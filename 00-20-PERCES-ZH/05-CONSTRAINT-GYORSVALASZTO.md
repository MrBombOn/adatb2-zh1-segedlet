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
