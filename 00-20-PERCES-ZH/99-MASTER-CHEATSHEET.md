# Master cheatsheet (Oracle 11g)

**GYORS · kitöltendő minták · NE kész ZH-válasz**

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

## 0. Aranyszabályok
- Oracle 11g only: NINCS FETCH FIRST, LIMIT, IDENTITY, AUTO_INCREMENT
- Top-N: ROWNUM / ROW_NUMBER
- NULL: IS NULL; NVL(<o>, <x>)
- Kliens: PL/SQL Developer

## 1. dual
```sql
SELECT * FROM dual;
SELECT user, SYSDATE FROM dual;
```

## 2. SELECT váz
```sql
SELECT <oszlopok>
FROM   <tabla>
WHERE  <feltetel>
GROUP BY <csoport>
HAVING <csoport_feltetel>
ORDER BY <kifejezes> [ASC|DESC];
```

## 3. WHERE operátorok
```sql
WHERE <o> = <e>
WHERE <o> <> <e>
WHERE <o> IN (<e1>, <e2>)
WHERE <o> BETWEEN <a> AND <b>
WHERE <o> LIKE '<minta%>'
WHERE <o> IS NULL
WHERE <f1> AND (<f2> OR <f3>)
```

## 4. JOIN
```sql
FROM <a> a JOIN <b> b ON b.<fk> = a.<pk>
FROM <a> a LEFT JOIN <b> b ON b.<fk> = a.<pk>
FROM <a> a LEFT JOIN <b> b ON … WHERE b.<pk> IS NULL
FROM <t> x JOIN <t> y ON x.<o> = y.<o>  -- self
```

## 5. GROUP / HAVING / aggregátum
```sql
SELECT <c>, COUNT(*), SUM(<n>), AVG(<n>), MIN(<o>), MAX(<o>)
FROM <t>
GROUP BY <c>
HAVING COUNT(*) >= <n>;
```

## 6. CASE / NVL
```sql
SELECT CASE WHEN <f> THEN <a> ELSE <b> END AS <alias> FROM <t>;
SELECT NVL(<o>, <helyettes>) FROM <t>;
```

## 7. Dátum
```sql
TO_DATE('<sz>', 'YYYY-MM-DD')
TO_CHAR(<d>, 'YYYY-MM-DD')
ADD_MONTHS(<d>, <n>)
EXTRACT(YEAR FROM <d>)
SYSDATE
```

## 8. Top-N 11g
```sql
SELECT * FROM (
  SELECT <oszlopok> FROM <t> ORDER BY <r> DESC
) WHERE ROWNUM <= <n>;

SELECT * FROM (
  SELECT <oszlopok>, ROW_NUMBER() OVER (ORDER BY <r> DESC) rn FROM <t>
) WHERE rn = 1;
```

## 9. Subquery
```sql
WHERE <n> > (SELECT AVG(<n>) FROM <t>)
WHERE <id> IN (SELECT <id> FROM <t2> WHERE <f>)
WHERE EXISTS (SELECT 1 FROM <t2> x WHERE x.<fk> = t.<pk>)
WHERE NOT EXISTS (SELECT 1 FROM <t2> x WHERE x.<fk> = t.<pk>)
```

## 10. INSERT / INSERT ALL
```sql
INSERT INTO <t> (<o1>, <o2>) VALUES (<e1>, <e2>);

INSERT ALL
  INTO <t> (<o1>, <o2>) VALUES (<a1>, <a2>)
  INTO <t> (<o1>, <o2>) VALUES (<b1>, <b2>)
SELECT 1 FROM dual;
```

## 11. UPDATE / DELETE
```sql
UPDATE <t> SET <o> = <e> WHERE <f>;
DELETE FROM <t> WHERE <f>;
-- előtte: SELECT COUNT(*) FROM <t> WHERE <f>;
```

## 12. MERGE
```sql
MERGE INTO <cel> c
USING <forras> f ON (c.<k> = f.<k>)
WHEN MATCHED THEN UPDATE SET c.<o> = f.<o>
WHEN NOT MATCHED THEN INSERT (<oszlopok>) VALUES (<ertekek>);
```

## 13. Multitable INSERT
```sql
INSERT FIRST
  WHEN <f1> THEN INTO <t1> VALUES (<…>)
  WHEN <f2> THEN INTO <t2> VALUES (<…>)
SELECT … FROM <forras>;

INSERT ALL
  WHEN <f1> THEN INTO <t1> VALUES (<…>)
  WHEN <f2> THEN INTO <t2> VALUES (<…>)
SELECT … FROM <forras>;
```

## 14. CTAS
```sql
CREATE TABLE <uj> AS SELECT * FROM <regi> WHERE 1 = 0;
-- + ALTER TABLE … ADD CONSTRAINT …
```

## 15. DDL tábla
```sql
CREATE TABLE <t> (
  <id> NUMBER NOT NULL,
  <nev> VARCHAR2(<n>) NOT NULL,
  <szulo> NUMBER,
  CONSTRAINT pk_<t> PRIMARY KEY (<id>),
  CONSTRAINT fk_<t>_<szulo> FOREIGN KEY (<szulo>) REFERENCES <szulo_t>(<id>),
  CONSTRAINT uk_<t>_<nev> UNIQUE (<nev>),
  CONSTRAINT ck_<t>_<nev> CHECK (<feltetel>)
);
```

## 16. ALTER constraint
```sql
ALTER TABLE <t> ADD CONSTRAINT <nev> PRIMARY KEY (<o>);
ALTER TABLE <t> ADD CONSTRAINT <nev> FOREIGN KEY (<o>) REFERENCES <s>(<o>);
ALTER TABLE <t> ADD CONSTRAINT <nev> UNIQUE (<o>);
ALTER TABLE <t> ADD CONSTRAINT <nev> CHECK (<f>);
```

## 17. SEQUENCE
```sql
CREATE SEQUENCE <seq> START WITH 1 INCREMENT BY 1;
INSERT INTO <t> (<id>, <nev>) VALUES (<seq>.NEXTVAL, <nev_ertek>);
```

## 18. VIEW + LISTAGG
```sql
CREATE OR REPLACE VIEW <v> AS
SELECT <c>,
       COUNT(*) AS darab,
       LISTAGG(<e>, ',') WITHIN GROUP (ORDER BY <e>) AS lista
FROM <t>
GROUP BY <c>;
```

## 19. USER / GRANT / QUOTA
```sql
CREATE USER <u> IDENTIFIED BY <jelszo>;
ALTER USER <u> QUOTA UNLIMITED ON <tablespace>;
GRANT CREATE SESSION TO <u>;
GRANT CREATE TABLE TO <u>;
GRANT CREATE VIEW TO <u>;
GRANT SELECT ON <schema>.<t> TO <u>;
```

## 20. Tranzakció
```sql
COMMIT;
ROLLBACK;
SAVEPOINT <nev>;
ROLLBACK TO <nev>;
```

## 21. Karakter / szám függvények
```sql
UPPER(<o>) LOWER(<o>) SUBSTR(<o>,<k>,<h>) LENGTH(<o>)
ROUND(<n>,<d>) TRUNC(<n>,<d>) MOD(<a>,<b>)
```

## 22. Dictionary gyors
```sql
SELECT table_name FROM user_tables;
SELECT column_name, data_type FROM user_tab_columns WHERE table_name = <NAGYBETUS_NEV>;
SELECT constraint_name, constraint_type FROM user_constraints;
```

## 23. Gyakori ORA
- 00942 tábla/jog · 00979 GROUP BY · 00001 unique · 02291/02292 FK
- 01400 NULL · 01861 dátum · 01950 kvóta · 01031 privilege · 01489 LISTAGG

## 24. Függőség egy sorban
`USER → TABLE szulo → TABLE gyerek → SEQUENCE → INSERT szulo → INSERT gyerek → VIEW → SELECT`

## 25. Mit NE
- LIMIT / FETCH FIRST / OFFSET ROWS
- IDENTITY / AUTO_INCREMENT / SERIAL
- `= NULL`
- MySQL backtick, PostgreSQL `::`
- UPDATE/DELETE WHERE nélkül
- másolható „kész megoldás” a tanulási példából

## Emlékeztető blokk 1
- Placeholder minta 1: cseréld `<helyőrző>` → feladatsor név
- Ellenőrző kérdés 1: hány sort várok? van NULL? van FK?
