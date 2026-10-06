# Gyakori ORA hibák

| Kód | Jelentés tanulói nyelven | Mit nézz |
|-----|--------------------------|----------|
| ORA-00904 | érvénytelen azonosító | oszlopnév elírás |
| ORA-00933 | SQL nem zárul jól | szintaxis, pontosvessző/klóz |
| ORA-00936 | hiányzó kifejezés | SELECT lista / vessző |
| ORA-00942 | nincs tábla / nincs jog | név, séma, GRANT |
| ORA-00979 | nem GROUP BY kifejezés | GROUP BY lista |
| ORA-01400 | NULL a NOT NULL-ba | kötelező oszlop |
| ORA-00001 | UNIQUE/PK sértés | duplikált kulcs |
| ORA-02291 | FK: nincs szülő | előbb szülő sor |
| ORA-02292 | FK: van gyerek | előbb gyerekek |
| ORA-01861 | dátum formátum | TO_DATE maszk |
| ORA-12899 | túl hosszú érték | VARCHAR2 hossz |

## Módszer

1. Olvasd el az ORA kódot  
2. Nézd a **sor pozíciót** az üzenetben  
3. Egyszerűsítsd a SQL-t, amíg fut
