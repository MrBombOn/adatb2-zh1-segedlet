# DATE gyorssegély

**20 perc · GYORS**

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
SELECT SYSDATE FROM dual;

SELECT TO_DATE('<szoveg>', 'YYYY-MM-DD') FROM dual;
SELECT TO_CHAR(<date_oszlop>, 'YYYY-MM-DD') FROM dual;

SELECT *
FROM   <tabla>
WHERE  <date_oszlop> >= TO_DATE('<tol>', 'YYYY-MM-DD')
  AND  <date_oszlop> <  TO_DATE('<ig>',  'YYYY-MM-DD');

SELECT ADD_MONTHS(<date_oszlop>, <n>) FROM <tabla>;
SELECT EXTRACT(YEAR FROM <date_oszlop>) FROM <tabla>;
```

## Tipikus hiba
Maszk nélkül hasonlítás; `=` NULL dátumra; ORA-01861.
