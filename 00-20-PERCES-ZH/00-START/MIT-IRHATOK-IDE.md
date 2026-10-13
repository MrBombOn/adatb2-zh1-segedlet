# MIT ÍRHATOK IDE? — Ctrl+F szótár

Helyőrző → mit tölts ki. Jelölés: KÖTELEZŐ / VALID / TIPIKUS / KÖRNYEZETFÜGGŐ.

| Helyőrző | Mit írj | Jelölés | Példa gondolat | Téma |
|-----------|---------|---------|----------------|------|
| `<user_nev>` | User név a feladatsorból | **KÖTELEZŐ** | zh_user1 | 01 |
| `<jelszo>` | IDENTIFIED BY jelszó | **KÖTELEZŐ** | lab adja | 01 |
| `<tablespace_nev>` | Tablespace név | **KÖRNYEZETFÜGGŐ** | gyakran USERS, de ne vak | 01 |
| `<meret>` | Kvóta | **VALID** | 10M / UNLIMITED | 01 |
| `<tabla>` | Táblanév | **KÖTELEZŐ** | BOOK / STUDENT | 02 |
| `<oszlop>` | Oszlopnév | **KÖTELEZŐ** | title / name | 02 |
| `VARCHAR2(<n>)` | Hossz | **VALID** | 50, 100 | 02 |
| `NUMBER` | Szám/ID típus | **VALID** | id | 02 |
| `DATE` | Dátum típus | **VALID** | published_on | 02 |
| `<seq_nev>` | Sequence | **TIPIKUS** | seq_book | 02 |
| `pk_<tabla>` | PK név | **TIPIKUS** | pk_book | 03 |
| `fk_<gyerek>_<szulo>` | FK név | **TIPIKUS** | fk_book_author | 03 |
| `CHECK (<feltetel>)` | Feltétel | **KÖTELEZŐ ha CK** | price > 0 | 03 |
| `INSERT ALL …` | Több sor | **VALID 11g** | SELECT 1 FROM dual végén | 04 |
| `VALUES (<e>)` | Literál/kifejezés | **KÖTELEZŐ** | TO_DATE ha kell | 04 |
| `WHERE 1=0` | Üres CTAS | **VALID** | struktúra másolat | 05 |
| `MERGE ON (<kulcs>)` | Egyezés | **KÖTELEZŐ** | id / isbn | 05 |
| `WHEN <feltetel>` | Multitable ág | **KÖTELEZŐ** | dátum < … | 06 |
| `INSERT FIRST` | Első igaz ág | **VALID** | szétválogatás | 06 |
| `GROUP BY <c>` | Csoportkulcs | **KÖTELEZŐ aggregáláskor** | course_id | 07 |
| `HAVING <f>` | Csoportszűrés | **VALID** | COUNT(*) >= 3 | 07 |
| `LISTAGG(<e>,',')` | String agg | **VALID 11g** | nevek listája | 07 |
| `ON <b>.fk = <a>.pk` | JOIN feltétel | **KÖTELEZŐ** | author_id | 08 |
| `LEFT JOIN … IS NULL` | Nincs pár | **TIPIKUS** | hiányzó kapcsolat | 08 |
| `ROWNUM <= <n>` | Top-N | **VALID 11g** | n=1 | 09 |
| `ROW_NUMBER() OVER` | Analitikus Top | **VALID** | rn=1 | 09 |
| `FETCH FIRST` | TILOS megoldás | **TILTOTT** | csak figyelmeztetésben | 09 |
| `EXISTS (SELECT 1…)` | Létezés | **VALID** | korrelált | 09 |
| `IS NULL` | NULL teszt | **KÖTELEZŐ NULL-nál** | ne = NULL | 10 |
| `LIKE '<minta%>'` | Minta | **VALID** | 'A%' | 10 |
| `TO_DATE('<sz>','YYYY-MM-DD')` | Dátum literál | **TIPIKUS** | maszk egyezzen | 11 |
| `TO_CHAR(<d>,…)` | Formázás | **VALID** | YYYY-MM-DD | 11 |
| `SYSDATE` | Most | **VALID** | dual | 11 |
| `UPDATE … WHERE` | Módosítás | **KÖTELEZŐ WHERE gyakorlat** | … | 12 |
| `DELETE … WHERE` | Törlés | **KÖTELEZŐ WHERE gyakorlat** | … | 12 |
| `ALTER TABLE ADD` | Oszlop/constraint | **VALID** | … | 13 |
| `GRANT SELECT ON …` | Object jog | **TIPIKUS** | … | 14 |
| `WITH GRANT OPTION` | Object továbbadás | **KÖRNYEZETFÜGGŐ** | ha kéri | 14 |
| `WITH ADMIN OPTION` | System továbbadás | **KÖRNYEZETFÜGGŐ** | ha kéri | 14 |
| `COMMIT` | Véglegesítés | **VALID** | ha kell | 15 |
| `ROLLBACK` | Visszavonás | **VALID** | ha kell | 15 |
| `CREATE SYNONYM` | Álnév | **VALID** | FOR schema.obj | 16 |
| `NVL(<o>,<x>)` | NULL helyettes | **TIPIKUS** | … | 17 |
| `CASE WHEN … END` | Feltételes | **VALID** | … | 17 |
| `UNION / MINUS` | Halmaz | **VALID** | oszlopszám egyezzen | 19 |
| `USERS tablespace` | Gyakori név | **TIPIKUS/KÖRNYEZETFÜGGŐ** | ne vak kötelező | 01 |
| `IDENTITY` | TILOS 11g ZH-n | **TILTOTT** | SEQUENCE helyett | 02 |

## Kapcsolódó

- Témák README **MIT ÍRHATOK** szekciói
- [`../99-MASTER/`](../99-MASTER/)
