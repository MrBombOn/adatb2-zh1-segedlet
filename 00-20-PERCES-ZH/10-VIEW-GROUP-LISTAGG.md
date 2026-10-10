# VIEW + GROUP BY + LISTAGG

**20 perc · GYORS**

## Szinonimák
nézet / csoportonként / listázd egy sorban / fűzd össze

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
CREATE OR REPLACE VIEW <nezet> AS
SELECT <csoport_oszlop>,
       COUNT(*) AS darab,
       LISTAGG(<elem_oszlop>, ',') WITHIN GROUP (ORDER BY <elem_oszlop>) AS lista
FROM   <tabla>
GROUP BY <csoport_oszlop>;
```

## FIGYELEM
- LISTAGG 11g R2-ben elérhető; túl hosszú lista → ORA-01489  
- VIEW-ban a GROUP BY szabály ugyanúgy él  
- `CREATE OR REPLACE VIEW` kényelmes gyakorláskor

## Ellenőrzés
```sql
SELECT * FROM <nezet>;
```
