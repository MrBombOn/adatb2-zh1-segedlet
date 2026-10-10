# Ha teljesen más feladat jön

**20 perc · GYORS**

## Döntési fa

```text
Új / idegen feladatszöveg
│
├─ Van CREATE USER / GRANT / QUOTA? → 03-SEMA-USER
├─ Van CREATE TABLE / oszloplista? → 04 + 05
├─ Van „üres másolat” / struktúra? → 07-CTAS
├─ Van tömeges INSERT / 5 rekord? → 06-INSERT ALL
├─ Van „ha van/ha nincs”? → 08-MERGE
├─ Van dátum szerinti szétválogatás? → 09
├─ Van nézet / csoport / lista? → 10
├─ Van leg… / top? → 11-ROWNUM
├─ Van „akkor is ha nincs”? → 12-LEFT
├─ Van „azok akik / átlag felett”? → 13-subquery
├─ Van dátumformátum? → 14
└─ Semmi nem passzol?
     ├─ Olvasás? → SELECT + WHERE + (JOIN?)
     ├─ Írás? → INSERT/UPDATE/DELETE
     └─ Struktúra? → CREATE/ALTER + constraint
```

## ≥70 kulcsmondat (gyors emlékeztető)

1. Először döntsd el: olvasás, írás vagy struktúra.
2. A táblanevek a feladatsorból jönnek, nem a gyakorló világból.
3. PK nélkül a gyerek FK vakrepülés.
4. FK = szabály; JOIN = lekérdezés.
5. WHERE sorokra szűr, HAVING csoportokra.
6. GROUP BY-ból kimaradt oszlop → ORA-00979.
7. NULL-ra ne használj egyenlőséget.
8. ROWNUM az ORDER BY utáni alkérdésen él igazán.
9. FETCH FIRST ezen a ZH-n tilos.
10. LIMIT MySQL reflex — felejtsd el.
11. IDENTITY helyett SEQUENCE.
12. INSERT ALL végén kell a SELECT … FROM dual.
13. CTAS WHERE 1=0 üres struktúra-közeli másolat.
14. CTAS után gyakran kell ALTER CONSTRAINT.
15. MERGE ON kulcsa legyen egyedi találat.
16. INSERT FIRST az első igaz ágat választja.
17. INSERT ALL minden igaz ágba ír.
18. LISTAGG hosszú szövegnél elhasalhat.
19. LEFT JOIN + IS NULL = „nincs pár”.
20. INNER JOIN elhagyja a pár nélkülieket.
21. 1:N JOIN szorozhatja a sorokat.
22. COUNT(*) sorokat számol.
23. COUNT(col) a NULL-okat kihagyja.
24. AVG/SUM NULL-t ignorál.
25. TO_DATE maszk nélkül kockázat.
26. TO_CHAR a megjelenítéshez.
27. SYSDATE a szerver ideje.
28. BETWEEN inkluzív.
29. AND erősebb, mint OR — zárójelezz.
30. UPDATE/DELETE előtt ugyanaz a SELECT.
31. WHERE nélküli UPDATE katasztrófa.
32. TRUNCATE nem ugyanaz, mint DELETE.
33. COMMIT tartósít, ROLLBACK visszavon.
34. DDL gyakran implicit commit.
35. ORA-00942 lehet joghiba is.
36. ORA-02291: nincs szülő.
37. ORA-02292: van gyerek.
38. ORA-01950: kvóta.
39. ORA-01031: privilege.
40. USER és SCHEMA Oracle-ben összetartozik.
41. GRANT CREATE SESSION a belépéshez.
42. QUOTA kell a táblaépítéshez tablespace-en.
43. Named constraint könnyebben olvasható hibánál.
44. CHECK ugyanarra a sorra vonatkozik.
45. UNIQUE engedi a NULL-t tipikusan.
46. Nézet = mentett SELECT.
47. Nem minden view updatable.
48. Subquery-t előbb külön futtasd.
49. EXISTS elég, ha csak létezés kell.
50. IN listánál NULL óvatosan.
51. DISTINCT nem helyettesíti a GROUP BY-t.
52. Alias WHERE-ben nem él.
53. ORDER BY lehet a végén.
54. DUAL skalár kifejezéshez.
55. VARCHAR2 a szokásos szövegtípus.
56. NUMBER a szám.
57. DATE dátum+idő másodpercig.
58. Hibaüzenet sorpozícióját nézd.
59. Egyszerűsítsd a SQL-t, amíg fut.
60. Először szülő, aztán gyerek adat.
61. A feladatsor sorrendje nem mindig a futási sorrend.
62. Ha idegen a szöveg: kulcsszó-táblázat.
63. Rajzolj PK–FK nyilakat.
64. Időszűke: biztos DDL/DML pontok előbb.
65. Ne másolj tanulási példát vakon.
66. Placeholder-t cseréld a feladatra.
67. Oracle 11g: maradj a tanult dialektusnál.
68. PL/SQL Developer a gyakorló kliens.
69. Ha elakadsz: START ITT táblázat.
70. Végső checklist 60 másodperc.
71. Saját munka — ez a lényeg.
72. Pánik helyett ORA kód.
73. Egy JOIN feltétel = egy kapcsolat.
74. Több tábla → több ON.
75. HAVING-ben aggregátum.
76. WHERE-ben ne aggregátumot erőltess.
