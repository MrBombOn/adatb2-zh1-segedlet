# ZH-SZOVEG-FELISMERES-INDEX

**P0 · CTRL+F** · Oracle 11g · hu + ékezet nélkül + SQL + en → **1 quick**

> Nem megoldásbank. Canonical csak ha a quick után elakadsz.
> P0: feladatszöveg → max 1 quick → teljes kitölthető SQL.

| # | Magyar | Ekezet nelkul | SQL / eszköz | EN | Quick | P |
|---|--------|---------------|--------------|----|-------|---|
| 1 | azokat is, amelyekhez még nem tartozik semmi | azokat is, amelyekhez meg nem tartozik semmi | LEFT JOIN | also those with nothing related yet | `08-JOIN/NINCS-PAR` | P0 |
| 2 | semmi nem tartozik hozzájuk sem | semmi nem tartozik hozzajuk sem | LEFT JOIN | also those with nothing related yet (syn) | `08-JOIN/NINCS-PAR` | P0 |
| 3 | még nincs semmijük | meg nincs semmijuk | LEFT JOIN | also those with nothing related yet (syn) | `08-JOIN/NINCS-PAR` | P0 |
| 4 | amikhez még semmi nem kapcsolódik | amikhez meg semmi nem kapcsolodik | LEFT JOIN | also those with nothing related yet (syn) | `08-JOIN/NINCS-PAR` | P0 |
| 5 | minden rekord, függetlenül a kapcsolattól | minden rekord, fuggetlenul a kapcsolattol | LEFT JOIN | every record regardless of relation | `08-JOIN` | P0 |
| 6 | kapcsolattól függetlenül minden | kapcsolattol fuggetlenul minden | LEFT JOIN | every record regardless of relation (syn) | `08-JOIN` | P0 |
| 7 | összes rekord left join | osszes rekord left join | LEFT JOIN | every record regardless of relation (syn) | `08-JOIN` | P0 |
| 8 | függetlenül attól van-e párja | fuggetlenul attol van-e parja | LEFT JOIN | every record regardless of relation (syn) | `08-JOIN` | P0 |
| 9 | akkor is mutasd, ha nulla kapcsolódó rekordja van | akkor is mutasd, ha nulla kapcsolodo rekordja van | LEFT JOIN | show even if zero related | `08-JOIN/LEFT-JOIN-COUNT` | P0 |
| 10 | nulla kapcsolódónál is mutasd | nulla kapcsolodonal is mutasd | LEFT JOIN | show even if zero related (syn) | `08-JOIN/LEFT-JOIN-COUNT` | P0 |
| 11 | 0 kapcsolódó mellett is | 0 kapcsolodo mellett is | LEFT JOIN | show even if zero related (syn) | `08-JOIN/LEFT-JOIN-COUNT` | P0 |
| 12 | akkor is ha kapcsolódó darabszám nulla | akkor is ha kapcsolodo darabszam nulla | LEFT JOIN | show even if zero related (syn) | `08-JOIN/LEFT-JOIN-COUNT` | P0 |
| 13 | kapcsolódó rekord hiányában is | kapcsolodo rekord hianyaban is | LEFT JOIN | even without related row | `08-JOIN` | P0 |
| 14 | hiányzó kapcsolódó mellett is | hianyzo kapcsolodo mellett is | LEFT JOIN | even without related row (syn) | `08-JOIN` | P0 |
| 15 | kapcsolat hiányában is listázd | kapcsolat hianyaban is listazd | LEFT JOIN | even without related row (syn) | `08-JOIN` | P0 |
| 16 | ha nincs kapcsolódó rekord akkor is | ha nincs kapcsolodo rekord akkor is | LEFT JOIN | even without related row (syn) | `08-JOIN` | P0 |
| 17 | akkor is, ha nincs neki | akkor is, ha nincs neki | LEFT JOIN | even if it has none | `08-JOIN` | P0 |
| 18 | minden X Y nélkül | minden X Y nelkul | LEFT JOIN + IS NULL | all X without Y | `08-JOIN/NINCS-PAR` | P0 |
| 19 | nincs pár | nincs par | LEFT JOIN + IS NULL | no match | `08-JOIN/NINCS-PAR` | P0 |
| 20 | hiányzó kapcsolat | hianyzo kapcsolat | LEFT JOIN | missing relationship | `08-JOIN` | P0 |
| 21 | nulla kapcsolódó | nulla kapcsolodo | LEFT JOIN + COUNT=0 | zero related | `08-JOIN/LEFT-JOIN-COUNT` | P0 |
| 22 | 0 darab gyerek | 0 darab gyerek | HAVING COUNT(jobb.pk)=0 | zero child count | `08-JOIN/LEFT-JOIN-COUNT` | P0 |
| 23 | szerzők könyv nélkül | szerzok konyv nelkul | LEFT JOIN + IS NULL | authors without books | `08/NINCS-PAR` | P0 |
| 24 | ügyfelek rendelés nélkül | ugyfelek rendeles nelkul | LEFT JOIN + IS NULL | customers without orders | `08/NINCS-PAR` | P0 |
| 25 | hallgatók kurzus nélkül | hallgatok kurzus nelkul | LEFT JOIN + IS NULL | students without courses | `08/NINCS-PAR` | P0 |
| 26 | osztályok dolgozó nélkül | osztalyok dolgozo nelkul | LEFT JOIN + COUNT=0 | depts with no employees | `08/LEFT-JOIN-COUNT` | P0 |
| 27 | bal oldali kapcsolás | bal oldali kapcsolas | LEFT JOIN | left outer join | `08-JOIN` | P0 |
| 28 | összekapcsol két táblát | osszekapcsol ket tablat | JOIN | join two tables | `08-JOIN` | P0 |
| 29 | tartozik hozzá | tartozik hozza | JOIN | belongs to | `08-JOIN` | P0 |
| 30 | kapcsolódik | kapcsolodik | JOIN | belongs to (syn) | `08-JOIN` | P0 |
| 31 | hozzárendelve | hozzarendelve | JOIN | belongs to (syn) | `08-JOIN` | P0 |
| 32 | összekapcsolva | osszekapcsolva | JOIN | belongs to (syn) | `08-JOIN` | P0 |
| 33 | párosítva | parositva | JOIN | belongs to (syn) | `08-JOIN` | P0 |
| 34 | hozzárendelés | hozzarendeles | JOIN | belongs to (syn) | `08-JOIN` | P0 |
| 35 | együtt jelenjen meg | egyutt jelenjen meg | JOIN | appear together | `08-JOIN` | P0 |
| 36 | ha a user már létezik töröld | ha a user mar letezik torold | DROP USER CASCADE | if user exists drop | `01/DROP-USER` | P0 |
| 37 | drop user ha van | drop user ha van | DROP USER CASCADE | if user exists drop (syn) | `01/DROP-USER` | P0 |
| 38 | felhasználó törlése cascade | felhasznalo torlese cascade | DROP USER CASCADE | if user exists drop (syn) | `01/DROP-USER` | P0 |
| 39 | előbb drop user | elobb drop user | DROP USER CASCADE | if user exists drop (syn) | `01/DROP-USER` | P0 |
| 40 | töröld a felhasználót | torold a felhasznalot | DROP USER | drop the user | `01/DROP-USER` | P0 |
| 41 | hozz létre usert | hozz letre usert | CREATE USER | create user | `01-SEMA-USER` | P0 |
| 42 | adj jogot | adj jogot | GRANT | grant privilege | `01/14` | P0 |
| 43 | kvóta tablespace | kvota tablespace | ALTER USER QUOTA | quota on tablespace | `01-SEMA-USER` | P0 |
| 44 | séma létrehozása Oracle | sema letrehozasa Oracle | USER ≈ SCHEMA | schema means user | `01-SEMA-USER` | P0 |
| 45 | DROP USER IF EXISTS | DROP USER IF EXISTS | TILOS 11g | if exists forbidden | `01/DROP-USER` | P0 |
| 46 | CREATE SCHEMA vakon | CREATE SCHEMA vakon | NE → CREATE USER | no blind create schema | `01-SEMA-USER` | P0 |
| 47 | legalább N karakter | legalabb N karakter | CHECK LENGTH >= n | at least N characters | `03/CHECK-LENGTH` | P0 |
| 48 | min N karakter hosszú | min N karakter hosszu | CHECK LENGTH >= n | at least N characters (syn) | `03/CHECK-LENGTH` | P0 |
| 49 | LENGTH legalább | LENGTH legalabb | CHECK LENGTH >= n | at least N characters (syn) | `03/CHECK-LENGTH` | P0 |
| 50 | ne legyen rövidebb N-nél | ne legyen rovidebb N-nel | CHECK LENGTH >= n | at least N characters (syn) | `03/CHECK-LENGTH` | P0 |
| 51 | ne legyen rövidebb mint | ne legyen rovidebb mint | CHECK LENGTH | must not be shorter | `03/CHECK-LENGTH` | P0 |
| 52 | hossz ellenőrzés | hossz ellenorzes | CHECK LENGTH | length check | `03/CHECK-LENGTH` | P0 |
| 53 | jelszó legalább 8 karakter | jelszo legalabb 8 karakter | CHECK LENGTH>=8 | password min 8 | `03/CHECK-LENGTH` | P0 |
| 54 | cím legalább 3 betű | cim legalabb 3 betu | CHECK LENGTH>=3 | title min 3 | `03/CHECK-LENGTH` | P0 |
| 55 | elsődleges kulcs | elsodleges kulcs | PRIMARY KEY | primary key | `03-CONSTRAINT` | P0 |
| 56 | idegen kulcs | idegen kulcs | FOREIGN KEY | foreign key | `03-CONSTRAINT` | P0 |
| 57 | egyedi legyen | egyedi legyen | UNIQUE | must be unique | `03-CONSTRAINT` | P0 |
| 58 | kötelező mező | kotelezo mezo | NOT NULL | mandatory field | `03-CONSTRAINT` | P0 |
| 59 | ellenőrző feltétel | ellenorzo feltetel | CHECK | check constraint | `03-CONSTRAINT` | P0 |
| 60 | hivatkozási integritás | hivatkozasi integritas | FOREIGN KEY | referential integrity | `03-CONSTRAINT` | P0 |
| 61 | több táblába egyszerre | tobb tablaba egyszerre | INSERT ALL multi | into several tables | `04/INSERT-ALL-TOBB` | P0 |
| 62 | egyszerre több táblába | egyszerre tobb tablaba | INSERT ALL multi | into several tables (syn) | `04/INSERT-ALL-TOBB` | P0 |
| 63 | INSERT ALL több cél | INSERT ALL tobb cel | INSERT ALL multi | into several tables (syn) | `04/INSERT-ALL-TOBB` | P0 |
| 64 | multi-table insert | multi-table insert | INSERT ALL multi | into several tables (syn) | `04/INSERT-ALL-TOBB` | P0 |
| 65 | vegyél fel 5 rekordot | vegyel fel 5 rekordot | INSERT ALL | insert 5 rows | `04-ADATFELTOLTES` | P0 |
| 66 | illessz be öt sort | illessz be ot sort | INSERT ALL | insert 5 rows (syn) | `04-ADATFELTOLTES` | P0 |
| 67 | több sort egyszerre | tobb sort egyszerre | INSERT ALL | insert 5 rows (syn) | `04-ADATFELTOLTES` | P0 |
| 68 | töltsd fel | toltsd fel | INSERT ALL | insert 5 rows (syn) | `04-ADATFELTOLTES` | P0 |
| 69 | 5 sor beszúrása | 5 sor beszurasa | INSERT ALL | insert 5 rows (syn) | `04-ADATFELTOLTES` | P0 |
| 70 | AUTHOR és BOOK egyszerre | AUTHOR es BOOK egyszerre | INSERT ALL multi | author and book | `04/INSERT-ALL-TOBB` | P0 |
| 71 | CUSTOMER és ORDER egyszerre | CUSTOMER es ORDER egyszerre | INSERT ALL multi | customer and order | `04/INSERT-ALL-TOBB` | P0 |
| 72 | szétválogatás dátum szerint | szetvalogatas datum szerint | INSERT FIRST/ALL WHEN | split by date | `06-SZETVALOGATAS` | P0 |
| 73 | feltételes beszúrás | felteteles beszuras | INSERT WHEN | conditional insert | `06-SZETVALOGATAS` | P0 |
| 74 | többszörös beszúrás | tobbszoros beszuras | INSERT ALL | multi insert | `04-ADATFELTOLTES` | P0 |
| 75 | mai nap idő nélkül | mai nap ido nelkul | TRUNC(SYSDATE) | today without time | `11/DATUM-IDOPONT` | P0 |
| 76 | truncált sysdate | truncalt sysdate | TRUNC(SYSDATE) | today without time (syn) | `11/DATUM-IDOPONT` | P0 |
| 77 | nap kezdete | nap kezdete | TRUNC(SYSDATE) | today without time (syn) | `11/DATUM-IDOPONT` | P0 |
| 78 | mai nap 00:00 | mai nap 00:00 | TRUNC(SYSDATE) | today without time (syn) | `11/DATUM-IDOPONT` | P0 |
| 79 | napra vágott dátum | napra vagott datum | TRUNC | date truncated to day | `11/DATUM-IDOPONT` | P0 |
| 80 | óra perc nélkül | ora perc nelkul | TRUNC(SYSDATE) | without hour minute | `11/DATUM-IDOPONT` | P0 |
| 81 | a mai dátum | a mai datum | TRUNC(SYSDATE) | todays date | `11/DATUM-IDOPONT` | P0 |
| 82 | TO_DATE maszkkal | TO_DATE maszkkal | TO_DATE | to_date with mask | `11-DATUM` | P0 |
| 83 | formázd a dátumot | formazd a datumot | TO_CHAR | format the date | `11-DATUM` | P0 |
| 84 | aktuális dátum | aktualis datum | SYSDATE | current date | `11-DATUM` | P0 |
| 85 | szűrj dátumra | szurj datumra | WHERE + TO_DATE/TRUNC | filter by date | `11-DATUM` | P0 |
| 86 | N százalékkal emeld | N szazalekkal emeld | UPDATE *(1+n/100) | increase by N percent | `12/SZAZALEKOS` | P0 |
| 87 | százalékos emelés | szazalekos emeles | UPDATE *(1+n/100) | increase by N percent (syn) | `12/SZAZALEKOS` | P0 |
| 88 | növeld N%-kal | noveld N%-kal | UPDATE *(1+n/100) | increase by N percent (syn) | `12/SZAZALEKOS` | P0 |
| 89 | emelés százalékban | emeles szazalekban | UPDATE *(1+n/100) | increase by N percent (syn) | `12/SZAZALEKOS` | P0 |
| 90 | csökkentsd százalékkal | csokkentsd szazalekkal | UPDATE *(1-n/100) | decrease by percent | `12/SZAZALEKOS` | P0 |
| 91 | fizetés +10% | fizetes +10% | UPDATE *1.1 | salary +10 percent | `12/SZAZALEKOS` | P0 |
| 92 | ár -15% | ar -15% | UPDATE *0.85 | price -15 percent | `12/SZAZALEKOS` | P0 |
| 93 | akiknek van kapcsolódó rekordjuk | akiknek van kapcsolodo rekordjuk | UPDATE EXISTS | who have related rows | `12/UPDATE-EXISTS` | P0 |
| 94 | frissítsd ha létezik gyerek | frissitsd ha letezik gyerek | UPDATE EXISTS | update if child exists | `12/UPDATE-EXISTS` | P0 |
| 95 | csak akiknek van BOOK-juk | csak akiknek van BOOK-juk | UPDATE EXISTS | only who have books | `12/UPDATE-EXISTS` | P0 |
| 96 | csak akiknek van ORDER-ük | csak akiknek van ORDER-uk | UPDATE EXISTS | only who have orders | `12/UPDATE-EXISTS` | P0 |
| 97 | módosítsd | modositsd | UPDATE | modify | `12-DML` | P1 |
| 98 | frissítsd | frissitsd | UPDATE | modify (syn) | `12-DML` | P1 |
| 99 | állítsd át | allitsd at | UPDATE | modify (syn) | `12-DML` | P1 |
| 100 | változtasd | valtoztasd | UPDATE | modify (syn) | `12-DML` | P1 |
| 101 | update-eld | update-eld | UPDATE | modify (syn) | `12-DML` | P1 |
| 102 | töröld a sorokat | torold a sorokat | DELETE | delete rows | `12-DML` | P1 |
| 103 | távolítsd el a sorokat | tavolitsd el a sorokat | DELETE | delete rows (syn) | `12-DML` | P1 |
| 104 | sorok törlése | sorok torlese | DELETE | delete rows (syn) | `12-DML` | P1 |
| 105 | delete a sorokat | delete a sorokat | DELETE | delete rows (syn) | `12-DML` | P1 |
| 106 | sorszámozd | sorszamozd | ROW_NUMBER OVER | number the rows | `18-ANALITIKUS` | P1 |
| 107 | adj sorszámot | adj sorszamot | ROW_NUMBER OVER | number the rows (syn) | `18-ANALITIKUS` | P1 |
| 108 | számozd meg | szamozd meg | ROW_NUMBER OVER | number the rows (syn) | `18-ANALITIKUS` | P1 |
| 109 | row number | row number | ROW_NUMBER OVER | number the rows (syn) | `18-ANALITIKUS` | P1 |
| 110 | rangsorold | rangsorold | RANK / DENSE_RANK | rank them | `18-ANALITIKUS` | P1 |
| 111 | helyezés szerint | helyezes szerint | RANK / DENSE_RANK | rank them (syn) | `18-ANALITIKUS` | P1 |
| 112 | ranking | ranking | RANK / DENSE_RANK | rank them (syn) | `18-ANALITIKUS` | P1 |
| 113 | rangsor készítése | rangsor keszitese | RANK / DENSE_RANK | rank them (syn) | `18-ANALITIKUS` | P1 |
| 114 | csoportonként a leg | csoportonkent a leg | PARTITION + rn=1 | best per group | `18/INTEGRATED` | P1 |
| 115 | minden sor mellett az összeg | minden sor mellett az osszeg | SUM OVER | sum beside every row | `18/SUM-COUNT-AVG` | P1 |
| 116 | partíciónként átlag | particionkent atlag | AVG OVER PARTITION | average per partition | `18-ANALITIKUS` | P1 |
| 117 | osztályonként legmagasabb fizetés | osztalyonkent legmagasabb fizetes | ROW_NUMBER PARTITION | highest salary per dept | `18/INTEGRATED` | P1 |
| 118 | szerzőnként könyvek száma mellett rang | szerzonkent konyvek szama mellett rang | SUM+ROW_NUMBER | count and rank per author | `18/INTEGRATED` | P1 |
| 119 | DENSE_RANK lyuk nélkül | DENSE_RANK lyuk nelkul | DENSE_RANK | dense rank no gaps | `18/DENSE-RANK` | P1 |
| 120 | RANK lyukkal | RANK lyukkal | RANK | rank with gaps | `18/RANK` | P1 |
| 121 | PARTITION BY vs GROUP BY | PARTITION BY vs GROUP BY | OVER vs GROUP | partition vs group | `18/GROUP-BY-VS` | P1 |
| 122 | ablakfüggvény | ablakfuggveny | OVER | window function | `18-ANALITIKUS` | P1 |
| 123 | partíció | particio | PARTITION BY | partition by | `18-ANALITIKUS` | P1 |
| 124 | egyedi sorszám | egyedi sorszam | ROW_NUMBER | unique row number | `18-ANALITIKUS` | P1 |
| 125 | legalább N darab a csoportban | legalabb N darab a csoportban | HAVING COUNT >= n | at least N in group | `07/HAVING-COUNT` | P0 |
| 126 | minimum N a csoportban | minimum N a csoportban | HAVING COUNT >= n | at least N in group (syn) | `07/HAVING-COUNT` | P0 |
| 127 | csoportban legalább | csoportban legalabb | HAVING COUNT >= n | at least N in group (syn) | `07/HAVING-COUNT` | P0 |
| 128 | HAVING legalább | HAVING legalabb | HAVING COUNT >= n | at least N in group (syn) | `07/HAVING-COUNT` | P0 |
| 129 | pontosan N darab | pontosan N darab | HAVING COUNT = n | exactly N | `07/HAVING-COUNT` | P0 |
| 130 | több mint 3 rendelés | tobb mint 3 rendeles | HAVING COUNT > 3 | more than 3 orders | `07/HAVING-COUNT` | P0 |
| 131 | kevesebb mint 2 könyv | kevesebb mint 2 konyv | HAVING COUNT < 2 | fewer than 2 books | `07/HAVING-COUNT` | P0 |
| 132 | csoportszűrés | csoportszures | HAVING | group filter | `07-VIEW` | P0 |
| 133 | csoportonként | csoportonkent | GROUP BY | per group | `07-VIEW` | P0 |
| 134 | aggregálás | aggregalas | GROUP BY | aggregation | `07-VIEW` | P0 |
| 135 | kis nagy betű mindegy | kis nagy betu mindegy | UPPER LIKE | case insensitive | `10/LIKE-CASE` | P0 |
| 136 | case insensitive like | case insensitive like | UPPER LIKE | case insensitive (syn) | `10/LIKE-CASE` | P0 |
| 137 | UPPER LOWER like | UPPER LOWER like | UPPER LIKE | case insensitive (syn) | `10/LIKE-CASE` | P0 |
| 138 | betűméret mindegy | betumeret mindegy | UPPER LIKE | case insensitive (syn) | `10/LIKE-CASE` | P0 |
| 139 | tartalmazza a szöveget | tartalmazza a szoveget | LIKE %% | contains text | `10-WHERE` | P0 |
| 140 | LIKE nagybetűtől függetlenül | LIKE nagybetutol fuggetlenul | UPPER LIKE UPPER | like case blind | `10/LIKE-CASE` | P0 |
| 141 | öt komponenses lekérdezés | ot komponenses lekerdezes | LEFT+COUNT+GROUP+LIKE+HAVING | five-component query | `00-START/OT-KOMPONENSES` | P0 |
| 142 | integrált ötös lekérdezés | integralt otos lekerdezes | 5 komponens sablon | integrated five-part | `00-START/OT-KOMPONENSES` | P0 |
| 143 | listázd | listazd | SELECT | list | `10/99` | P0 |
| 144 | mutasd | mutasd | SELECT | list (syn) | `10/99` | P0 |
| 145 | add vissza | add vissza | SELECT | list (syn) | `10/99` | P0 |
| 146 | add meg | add meg | SELECT | list (syn) | `10/99` | P0 |
| 147 | készíts listát | keszits listat | SELECT | list (syn) | `10/99` | P0 |
| 148 | jelenítsd meg | jelenitsd meg | SELECT | list (syn) | `10/99` | P0 |
| 149 | írd ki | ird ki | SELECT | list (syn) | `10/99` | P0 |
| 150 | csak azok ahol | csak azok ahol | WHERE | only those where | `10-WHERE` | P0 |
| 151 | feltéve hogy | felteve hogy | WHERE | only those where (syn) | `10-WHERE` | P0 |
| 152 | amelyekre igaz | amelyekre igaz | WHERE | only those where (syn) | `10-WHERE` | P0 |
| 153 | szűrd | szurd | WHERE | only those where (syn) | `10-WHERE` | P0 |
| 154 | ahol a feltétel | ahol a feltetel | WHERE | only those where (syn) | `10-WHERE` | P0 |
| 155 | csak ha | csak ha | WHERE | only those where (syn) | `10-WHERE` | P0 |
| 156 | hozz létre táblát | hozz letre tablat | CREATE TABLE | create table | `02-TABLA` | P0 |
| 157 | tábla létrehozása | tabla letrehozasa | CREATE TABLE | create table (syn) | `02-TABLA` | P0 |
| 158 | készíts táblát | keszits tablat | CREATE TABLE | create table (syn) | `02-TABLA` | P0 |
| 159 | definiáld a táblát | definiald a tablat | CREATE TABLE | create table (syn) | `02-TABLA` | P0 |
| 160 | új tábla | uj tabla | CREATE TABLE | create table (syn) | `02-TABLA` | P0 |
| 161 | üres másolat | ures masolat | CTAS 1=0 | empty copy | `05-MASOLAT` | P0 |
| 162 | ha van frissíts ha nincs vedd fel | ha van frissits ha nincs vedd fel | MERGE | upsert | `05-MASOLAT` | P0 |
| 163 | összefésülés | osszefesules | MERGE | merge upsert | `05-MASOLAT` | P0 |
| 164 | struktúra másolás | struktura masolas | CTAS | structure copy | `05-MASOLAT` | P0 |
| 165 | nézetet hozz létre | nezetet hozz letre | CREATE VIEW | create view | `07-VIEW` | P0 |
| 166 | LISTAGG lista | LISTAGG lista | LISTAGG | listagg list | `07-VIEW` | P0 |
| 167 | legnagyobb egy | legnagyobb egy | Top-N ROWNUM | the single greatest | `09-TOP1` | P0 |
| 168 | ROWNUM top | ROWNUM top | ROWNUM | rownum top-n | `09-TOP1` | P0 |
| 169 | EXISTS alkérdés | EXISTS alkerdes | EXISTS | exists subquery | `09-TOP1` | P0 |
| 170 | véglegesíts | veglegesits | COMMIT | commit | `15-TRANZAKCIO` | P1 |
| 171 | visszavonás tranzakció | visszavonas tranzakcio | ROLLBACK | rollback | `15-TRANZAKCIO` | P1 |
| 172 | unió | unio | UNION | union | `19-HALMAZ` | P2 |
| 173 | metszet | metszet | INTERSECT | intersection | `19-HALMAZ` | P2 |
| 174 | különbség | kulonbseg | MINUS | set difference | `19-HALMAZ` | P2 |
| 175 | SEQUENCE nextval | SEQUENCE nextval | seq.NEXTVAL | sequence nextval | `02-TABLA` | P0 |
| 176 | NULL vizsgálat | NULL vizsgalat | IS NULL | null test | `10-WHERE` | P0 |
| 177 | BETWEEN tartomány | BETWEEN tartomany | BETWEEN | between range | `10-WHERE` | P0 |
| 178 | IN lista | IN lista | IN (...) | in list | `10-WHERE` | P0 |
| 179 | ORA hiba | ORA hiba | ORA kód | ora error | `20-ORA-HIBAK` | P0 |
| 180 | meglepetés feladat | meglepetes feladat | döntési mátrix | surprise task | `22-MEGLEPETES` | P0 |
| 181 | pót zh minta | pot zh minta | mintafelismerés | retake pattern | `23/01-pot` | P0 |
| 182 | közös minták | kozos mintak | eredeti+pót | common patterns | `23/02-KOZOS` | P1 |
| 183 | nem tudom mit keressek | nem tudom mit keressek | NEM-TUDOM mód | do not know what to search | `00-START/NEM-TUDOM` | P0 |
| 184 | ismeretlen feladat | ismeretlen feladat | 12 kérdés fallback | unknown task | `00-START/ISMERETLEN-FELADAT` | P0 |
| 185 | komponensekre bontás | komponensekre bontas | komponens + sablon | break into components | `00-START/FELADAT-KOMPONENSEKRE` | P0 |
| 186 | lépésről lépésre | lepesrol lepesre | döntési pontok | step by step | `00-START/00-LEPESROL` | P0 |
| 187 | 3 perces gyorsút | 3 perces gyorsut | 3 perc quick | 3 minute path | `00-START/00-ZH-GYORS-3-PERC` | P0 |
| 188 | COUNT csillag nulla left után | COUNT csillag nulla left utan | CSAPDA → COUNT(pk) | count star trap | `08/LEFT-JOIN-COUNT` | P0 |
| 189 | FETCH FIRST | FETCH FIRST | TILOS 11g | fetch first forbidden | `09-TOP1` | P0 |
| 190 | LIMIT 10 | LIMIT 10 | TILOS 11g | limit forbidden | `09-TOP1` | P0 |
| 191 | IDENTITY oszlop | IDENTITY oszlop | TILOS → SEQUENCE | identity forbidden | `02-TABLA` | P0 |
| 192 | oszlop hozzáadás | oszlop hozzaadas | ALTER TABLE ADD | add column | `13-DDL` | P1 |
| 193 | tábla eldobás | tabla eldobas | DROP TABLE | drop table | `13-DDL` | P1 |
| 194 | szinonima | szinonima | CREATE SYNONYM | synonym | `16-SYNONYM` | P2 |
| 195 | jogosultság megvonás | jogosultsag megvonas | REVOKE | revoke | `14-JOG` | P1 |
| 196 | AUTHOR tábla: azokat is, amelyekhez még nem tartozik BOOK | AUTHOR tabla: azokat is, amelyekhez meg nem tartozik BOOK | LEFT JOIN | AUTHOR without BOOK | `08-JOIN/NINCS-PAR` | P0 |
| 197 | minden AUTHOR, függetlenül a BOOK kapcsolattól | minden AUTHOR, fuggetlenul a BOOK kapcsolattol | LEFT JOIN | all AUTHOR regardless of BOOK | `08-JOIN` | P0 |
| 198 | AUTHOR akkor is, ha nulla BOOK rekordja van | AUTHOR akkor is, ha nulla BOOK rekordja van | LEFT JOIN + COUNT=0 | AUTHOR even with zero BOOK | `08-JOIN/LEFT-JOIN-COUNT` | P0 |
| 199 | UPDATE AUTHOR ha van BOOK | UPDATE AUTHOR ha van BOOK | UPDATE EXISTS | update AUTHOR if has BOOK | `12/UPDATE-EXISTS` | P0 |
| 200 | INSERT ALL AUTHOR és BOOK | INSERT ALL AUTHOR es BOOK | INSERT ALL multi | insert AUTHOR and BOOK | `04/INSERT-ALL-TOBB` | P0 |
| 201 | CUSTOMER tábla: azokat is, amelyekhez még nem tartozik ORDER | CUSTOMER tabla: azokat is, amelyekhez meg nem tartozik ORDER | LEFT JOIN | CUSTOMER without ORDER | `08-JOIN/NINCS-PAR` | P0 |
| 202 | minden CUSTOMER, függetlenül a ORDER kapcsolattól | minden CUSTOMER, fuggetlenul a ORDER kapcsolattol | LEFT JOIN | all CUSTOMER regardless of ORDER | `08-JOIN` | P0 |
| 203 | CUSTOMER akkor is, ha nulla ORDER rekordja van | CUSTOMER akkor is, ha nulla ORDER rekordja van | LEFT JOIN + COUNT=0 | CUSTOMER even with zero ORDER | `08-JOIN/LEFT-JOIN-COUNT` | P0 |
| 204 | UPDATE CUSTOMER ha van ORDER | UPDATE CUSTOMER ha van ORDER | UPDATE EXISTS | update CUSTOMER if has ORDER | `12/UPDATE-EXISTS` | P0 |
| 205 | INSERT ALL CUSTOMER és ORDER | INSERT ALL CUSTOMER es ORDER | INSERT ALL multi | insert CUSTOMER and ORDER | `04/INSERT-ALL-TOBB` | P0 |
| 206 | STUDENT tábla: azokat is, amelyekhez még nem tartozik COURSE | STUDENT tabla: azokat is, amelyekhez meg nem tartozik COURSE | LEFT JOIN | STUDENT without COURSE | `08-JOIN/NINCS-PAR` | P0 |
| 207 | minden STUDENT, függetlenül a COURSE kapcsolattól | minden STUDENT, fuggetlenul a COURSE kapcsolattol | LEFT JOIN | all STUDENT regardless of COURSE | `08-JOIN` | P0 |
| 208 | STUDENT akkor is, ha nulla COURSE rekordja van | STUDENT akkor is, ha nulla COURSE rekordja van | LEFT JOIN + COUNT=0 | STUDENT even with zero COURSE | `08-JOIN/LEFT-JOIN-COUNT` | P0 |
| 209 | UPDATE STUDENT ha van COURSE | UPDATE STUDENT ha van COURSE | UPDATE EXISTS | update STUDENT if has COURSE | `12/UPDATE-EXISTS` | P0 |
| 210 | INSERT ALL STUDENT és COURSE | INSERT ALL STUDENT es COURSE | INSERT ALL multi | insert STUDENT and COURSE | `04/INSERT-ALL-TOBB` | P0 |
| 211 | EMPLOYEE tábla: azokat is, amelyekhez még nem tartozik DEPARTMENT | EMPLOYEE tabla: azokat is, amelyekhez meg nem tartozik DEPARTMENT | LEFT JOIN | EMPLOYEE without DEPARTMENT | `08-JOIN/NINCS-PAR` | P0 |
| 212 | minden EMPLOYEE, függetlenül a DEPARTMENT kapcsolattól | minden EMPLOYEE, fuggetlenul a DEPARTMENT kapcsolattol | LEFT JOIN | all EMPLOYEE regardless of DEPARTMENT | `08-JOIN` | P0 |
| 213 | EMPLOYEE akkor is, ha nulla DEPARTMENT rekordja van | EMPLOYEE akkor is, ha nulla DEPARTMENT rekordja van | LEFT JOIN + COUNT=0 | EMPLOYEE even with zero DEPARTMENT | `08-JOIN/LEFT-JOIN-COUNT` | P0 |
| 214 | UPDATE EMPLOYEE ha van DEPARTMENT | UPDATE EMPLOYEE ha van DEPARTMENT | UPDATE EXISTS | update EMPLOYEE if has DEPARTMENT | `12/UPDATE-EXISTS` | P0 |
| 215 | INSERT ALL EMPLOYEE és DEPARTMENT | INSERT ALL EMPLOYEE es DEPARTMENT | INSERT ALL multi | insert EMPLOYEE and DEPARTMENT | `04/INSERT-ALL-TOBB` | P0 |
| 216 | feladat: azokat is, amelyekhez még nem tartozik semmi | feladat: azokat is, amelyekhez meg nem tartozik semmi | LEFT JOIN | also those with nothing related yet | `08-JOIN/NINCS-PAR` | P0 |
| 217 | kérdés: azokat is, amelyekhez még nem tartozik semmi | kerdes: azokat is, amelyekhez meg nem tartozik semmi | LEFT JOIN | also those with nothing related yet | `08-JOIN/NINCS-PAR` | P0 |
| 218 | szöveg: azokat is, amelyekhez még nem tartozik semmi | szoveg: azokat is, amelyekhez meg nem tartozik semmi | LEFT JOIN | also those with nothing related yet | `08-JOIN/NINCS-PAR` | P0 |
| 219 | ZH: azokat is, amelyekhez még nem tartozik semmi | ZH: azokat is, amelyekhez meg nem tartozik semmi | LEFT JOIN | also those with nothing related yet | `08-JOIN/NINCS-PAR` | P0 |
| 220 | pótzárthelyi: azokat is, amelyekhez még nem tartozik semmi | potzarthelyi: azokat is, amelyekhez meg nem tartozik semmi | LEFT JOIN | also those with nothing related yet | `08-JOIN/NINCS-PAR` | P0 |
| 221 | feladat: minden rekord, függetlenül a kapcsolattól | feladat: minden rekord, fuggetlenul a kapcsolattol | LEFT JOIN | every record regardless of relation | `08-JOIN` | P0 |
| 222 | kérdés: minden rekord, függetlenül a kapcsolattól | kerdes: minden rekord, fuggetlenul a kapcsolattol | LEFT JOIN | every record regardless of relation | `08-JOIN` | P0 |
| 223 | szöveg: minden rekord, függetlenül a kapcsolattól | szoveg: minden rekord, fuggetlenul a kapcsolattol | LEFT JOIN | every record regardless of relation | `08-JOIN` | P0 |
| 224 | ZH: minden rekord, függetlenül a kapcsolattól | ZH: minden rekord, fuggetlenul a kapcsolattol | LEFT JOIN | every record regardless of relation | `08-JOIN` | P0 |
| 225 | pótzárthelyi: minden rekord, függetlenül a kapcsolattól | potzarthelyi: minden rekord, fuggetlenul a kapcsolattol | LEFT JOIN | every record regardless of relation | `08-JOIN` | P0 |
| 226 | feladat: akkor is mutasd, ha nulla kapcsolódó rekordja van | feladat: akkor is mutasd, ha nulla kapcsolodo rekordja van | LEFT JOIN | show even if zero related | `08-JOIN/LEFT-JOIN-COUNT` | P0 |
| 227 | kérdés: akkor is mutasd, ha nulla kapcsolódó rekordja van | kerdes: akkor is mutasd, ha nulla kapcsolodo rekordja van | LEFT JOIN | show even if zero related | `08-JOIN/LEFT-JOIN-COUNT` | P0 |
| 228 | szöveg: akkor is mutasd, ha nulla kapcsolódó rekordja van | szoveg: akkor is mutasd, ha nulla kapcsolodo rekordja van | LEFT JOIN | show even if zero related | `08-JOIN/LEFT-JOIN-COUNT` | P0 |
| 229 | ZH: akkor is mutasd, ha nulla kapcsolódó rekordja van | ZH: akkor is mutasd, ha nulla kapcsolodo rekordja van | LEFT JOIN | show even if zero related | `08-JOIN/LEFT-JOIN-COUNT` | P0 |
| 230 | pótzárthelyi: akkor is mutasd, ha nulla kapcsolódó rekordja van | potzarthelyi: akkor is mutasd, ha nulla kapcsolodo rekordja van | LEFT JOIN | show even if zero related | `08-JOIN/LEFT-JOIN-COUNT` | P0 |
| 231 | feladat: kapcsolódó rekord hiányában is | feladat: kapcsolodo rekord hianyaban is | LEFT JOIN | even without related row | `08-JOIN` | P0 |
| 232 | kérdés: kapcsolódó rekord hiányában is | kerdes: kapcsolodo rekord hianyaban is | LEFT JOIN | even without related row | `08-JOIN` | P0 |
| 233 | szöveg: kapcsolódó rekord hiányában is | szoveg: kapcsolodo rekord hianyaban is | LEFT JOIN | even without related row | `08-JOIN` | P0 |
| 234 | ZH: kapcsolódó rekord hiányában is | ZH: kapcsolodo rekord hianyaban is | LEFT JOIN | even without related row | `08-JOIN` | P0 |
| 235 | pótzárthelyi: kapcsolódó rekord hiányában is | potzarthelyi: kapcsolodo rekord hianyaban is | LEFT JOIN | even without related row | `08-JOIN` | P0 |
| 236 | feladat: akkor is, ha nincs neki | feladat: akkor is, ha nincs neki | LEFT JOIN | even if it has none | `08-JOIN` | P0 |
| 237 | kérdés: akkor is, ha nincs neki | kerdes: akkor is, ha nincs neki | LEFT JOIN | even if it has none | `08-JOIN` | P0 |
| 238 | szöveg: akkor is, ha nincs neki | szoveg: akkor is, ha nincs neki | LEFT JOIN | even if it has none | `08-JOIN` | P0 |
| 239 | ZH: akkor is, ha nincs neki | ZH: akkor is, ha nincs neki | LEFT JOIN | even if it has none | `08-JOIN` | P0 |
| 240 | pótzárthelyi: akkor is, ha nincs neki | potzarthelyi: akkor is, ha nincs neki | LEFT JOIN | even if it has none | `08-JOIN` | P0 |
| 241 | feladat: minden X Y nélkül | feladat: minden X Y nelkul | LEFT JOIN + IS NULL | all X without Y | `08-JOIN/NINCS-PAR` | P0 |
| 242 | kérdés: minden X Y nélkül | kerdes: minden X Y nelkul | LEFT JOIN + IS NULL | all X without Y | `08-JOIN/NINCS-PAR` | P0 |
| 243 | szöveg: minden X Y nélkül | szoveg: minden X Y nelkul | LEFT JOIN + IS NULL | all X without Y | `08-JOIN/NINCS-PAR` | P0 |
| 244 | ZH: minden X Y nélkül | ZH: minden X Y nelkul | LEFT JOIN + IS NULL | all X without Y | `08-JOIN/NINCS-PAR` | P0 |
| 245 | pótzárthelyi: minden X Y nélkül | potzarthelyi: minden X Y nelkul | LEFT JOIN + IS NULL | all X without Y | `08-JOIN/NINCS-PAR` | P0 |
| 246 | feladat: nincs pár | feladat: nincs par | LEFT JOIN + IS NULL | no match | `08-JOIN/NINCS-PAR` | P0 |
| 247 | kérdés: nincs pár | kerdes: nincs par | LEFT JOIN + IS NULL | no match | `08-JOIN/NINCS-PAR` | P0 |
| 248 | szöveg: nincs pár | szoveg: nincs par | LEFT JOIN + IS NULL | no match | `08-JOIN/NINCS-PAR` | P0 |
| 249 | ZH: nincs pár | ZH: nincs par | LEFT JOIN + IS NULL | no match | `08-JOIN/NINCS-PAR` | P0 |
| 250 | pótzárthelyi: nincs pár | potzarthelyi: nincs par | LEFT JOIN + IS NULL | no match | `08-JOIN/NINCS-PAR` | P0 |
| 251 | feladat: hiányzó kapcsolat | feladat: hianyzo kapcsolat | LEFT JOIN | missing relationship | `08-JOIN` | P0 |
| 252 | kérdés: hiányzó kapcsolat | kerdes: hianyzo kapcsolat | LEFT JOIN | missing relationship | `08-JOIN` | P0 |
| 253 | szöveg: hiányzó kapcsolat | szoveg: hianyzo kapcsolat | LEFT JOIN | missing relationship | `08-JOIN` | P0 |
| 254 | ZH: hiányzó kapcsolat | ZH: hianyzo kapcsolat | LEFT JOIN | missing relationship | `08-JOIN` | P0 |
| 255 | pótzárthelyi: hiányzó kapcsolat | potzarthelyi: hianyzo kapcsolat | LEFT JOIN | missing relationship | `08-JOIN` | P0 |
| 256 | feladat: nulla kapcsolódó | feladat: nulla kapcsolodo | LEFT JOIN + COUNT=0 | zero related | `08-JOIN/LEFT-JOIN-COUNT` | P0 |
| 257 | kérdés: nulla kapcsolódó | kerdes: nulla kapcsolodo | LEFT JOIN + COUNT=0 | zero related | `08-JOIN/LEFT-JOIN-COUNT` | P0 |
| 258 | szöveg: nulla kapcsolódó | szoveg: nulla kapcsolodo | LEFT JOIN + COUNT=0 | zero related | `08-JOIN/LEFT-JOIN-COUNT` | P0 |
| 259 | ZH: nulla kapcsolódó | ZH: nulla kapcsolodo | LEFT JOIN + COUNT=0 | zero related | `08-JOIN/LEFT-JOIN-COUNT` | P0 |
| 260 | pótzárthelyi: nulla kapcsolódó | potzarthelyi: nulla kapcsolodo | LEFT JOIN + COUNT=0 | zero related | `08-JOIN/LEFT-JOIN-COUNT` | P0 |
| 261 | feladat: 0 darab gyerek | feladat: 0 darab gyerek | HAVING COUNT(jobb.pk)=0 | zero child count | `08-JOIN/LEFT-JOIN-COUNT` | P0 |
| 262 | kérdés: 0 darab gyerek | kerdes: 0 darab gyerek | HAVING COUNT(jobb.pk)=0 | zero child count | `08-JOIN/LEFT-JOIN-COUNT` | P0 |
| 263 | szöveg: 0 darab gyerek | szoveg: 0 darab gyerek | HAVING COUNT(jobb.pk)=0 | zero child count | `08-JOIN/LEFT-JOIN-COUNT` | P0 |
| 264 | ZH: 0 darab gyerek | ZH: 0 darab gyerek | HAVING COUNT(jobb.pk)=0 | zero child count | `08-JOIN/LEFT-JOIN-COUNT` | P0 |
| 265 | pótzárthelyi: 0 darab gyerek | potzarthelyi: 0 darab gyerek | HAVING COUNT(jobb.pk)=0 | zero child count | `08-JOIN/LEFT-JOIN-COUNT` | P0 |
| 266 | feladat: szerzők könyv nélkül | feladat: szerzok konyv nelkul | LEFT JOIN + IS NULL | authors without books | `08/NINCS-PAR` | P0 |
| 267 | kérdés: szerzők könyv nélkül | kerdes: szerzok konyv nelkul | LEFT JOIN + IS NULL | authors without books | `08/NINCS-PAR` | P0 |
| 268 | szöveg: szerzők könyv nélkül | szoveg: szerzok konyv nelkul | LEFT JOIN + IS NULL | authors without books | `08/NINCS-PAR` | P0 |
| 269 | ZH: szerzők könyv nélkül | ZH: szerzok konyv nelkul | LEFT JOIN + IS NULL | authors without books | `08/NINCS-PAR` | P0 |
| 270 | pótzárthelyi: szerzők könyv nélkül | potzarthelyi: szerzok konyv nelkul | LEFT JOIN + IS NULL | authors without books | `08/NINCS-PAR` | P0 |
| 271 | feladat: ügyfelek rendelés nélkül | feladat: ugyfelek rendeles nelkul | LEFT JOIN + IS NULL | customers without orders | `08/NINCS-PAR` | P0 |
| 272 | kérdés: ügyfelek rendelés nélkül | kerdes: ugyfelek rendeles nelkul | LEFT JOIN + IS NULL | customers without orders | `08/NINCS-PAR` | P0 |
| 273 | szöveg: ügyfelek rendelés nélkül | szoveg: ugyfelek rendeles nelkul | LEFT JOIN + IS NULL | customers without orders | `08/NINCS-PAR` | P0 |
| 274 | ZH: ügyfelek rendelés nélkül | ZH: ugyfelek rendeles nelkul | LEFT JOIN + IS NULL | customers without orders | `08/NINCS-PAR` | P0 |
| 275 | pótzárthelyi: ügyfelek rendelés nélkül | potzarthelyi: ugyfelek rendeles nelkul | LEFT JOIN + IS NULL | customers without orders | `08/NINCS-PAR` | P0 |
| 276 | feladat: hallgatók kurzus nélkül | feladat: hallgatok kurzus nelkul | LEFT JOIN + IS NULL | students without courses | `08/NINCS-PAR` | P0 |
| 277 | kérdés: hallgatók kurzus nélkül | kerdes: hallgatok kurzus nelkul | LEFT JOIN + IS NULL | students without courses | `08/NINCS-PAR` | P0 |
| 278 | szöveg: hallgatók kurzus nélkül | szoveg: hallgatok kurzus nelkul | LEFT JOIN + IS NULL | students without courses | `08/NINCS-PAR` | P0 |
| 279 | ZH: hallgatók kurzus nélkül | ZH: hallgatok kurzus nelkul | LEFT JOIN + IS NULL | students without courses | `08/NINCS-PAR` | P0 |
| 280 | pótzárthelyi: hallgatók kurzus nélkül | potzarthelyi: hallgatok kurzus nelkul | LEFT JOIN + IS NULL | students without courses | `08/NINCS-PAR` | P0 |
| 281 | feladat: osztályok dolgozó nélkül | feladat: osztalyok dolgozo nelkul | LEFT JOIN + COUNT=0 | depts with no employees | `08/LEFT-JOIN-COUNT` | P0 |
| 282 | kérdés: osztályok dolgozó nélkül | kerdes: osztalyok dolgozo nelkul | LEFT JOIN + COUNT=0 | depts with no employees | `08/LEFT-JOIN-COUNT` | P0 |
| 283 | szöveg: osztályok dolgozó nélkül | szoveg: osztalyok dolgozo nelkul | LEFT JOIN + COUNT=0 | depts with no employees | `08/LEFT-JOIN-COUNT` | P0 |
| 284 | ZH: osztályok dolgozó nélkül | ZH: osztalyok dolgozo nelkul | LEFT JOIN + COUNT=0 | depts with no employees | `08/LEFT-JOIN-COUNT` | P0 |
| 285 | pótzárthelyi: osztályok dolgozó nélkül | potzarthelyi: osztalyok dolgozo nelkul | LEFT JOIN + COUNT=0 | depts with no employees | `08/LEFT-JOIN-COUNT` | P0 |
| 286 | feladat: bal oldali kapcsolás | feladat: bal oldali kapcsolas | LEFT JOIN | left outer join | `08-JOIN` | P0 |
| 287 | kérdés: bal oldali kapcsolás | kerdes: bal oldali kapcsolas | LEFT JOIN | left outer join | `08-JOIN` | P0 |
| 288 | szöveg: bal oldali kapcsolás | szoveg: bal oldali kapcsolas | LEFT JOIN | left outer join | `08-JOIN` | P0 |
| 289 | ZH: bal oldali kapcsolás | ZH: bal oldali kapcsolas | LEFT JOIN | left outer join | `08-JOIN` | P0 |
| 290 | pótzárthelyi: bal oldali kapcsolás | potzarthelyi: bal oldali kapcsolas | LEFT JOIN | left outer join | `08-JOIN` | P0 |
| 291 | feladat: összekapcsol két táblát | feladat: osszekapcsol ket tablat | JOIN | join two tables | `08-JOIN` | P0 |
| 292 | kérdés: összekapcsol két táblát | kerdes: osszekapcsol ket tablat | JOIN | join two tables | `08-JOIN` | P0 |
| 293 | szöveg: összekapcsol két táblát | szoveg: osszekapcsol ket tablat | JOIN | join two tables | `08-JOIN` | P0 |
| 294 | ZH: összekapcsol két táblát | ZH: osszekapcsol ket tablat | JOIN | join two tables | `08-JOIN` | P0 |
| 295 | pótzárthelyi: összekapcsol két táblát | potzarthelyi: osszekapcsol ket tablat | JOIN | join two tables | `08-JOIN` | P0 |
| 296 | feladat: tartozik hozzá | feladat: tartozik hozza | JOIN | belongs to | `08-JOIN` | P0 |
| 297 | kérdés: tartozik hozzá | kerdes: tartozik hozza | JOIN | belongs to | `08-JOIN` | P0 |
| 298 | szöveg: tartozik hozzá | szoveg: tartozik hozza | JOIN | belongs to | `08-JOIN` | P0 |
| 299 | ZH: tartozik hozzá | ZH: tartozik hozza | JOIN | belongs to | `08-JOIN` | P0 |
| 300 | pótzárthelyi: tartozik hozzá | potzarthelyi: tartozik hozza | JOIN | belongs to | `08-JOIN` | P0 |
| 301 | feladat: együtt jelenjen meg | feladat: egyutt jelenjen meg | JOIN | appear together | `08-JOIN` | P0 |
| 302 | kérdés: együtt jelenjen meg | kerdes: egyutt jelenjen meg | JOIN | appear together | `08-JOIN` | P0 |
| 303 | szöveg: együtt jelenjen meg | szoveg: egyutt jelenjen meg | JOIN | appear together | `08-JOIN` | P0 |
| 304 | ZH: együtt jelenjen meg | ZH: egyutt jelenjen meg | JOIN | appear together | `08-JOIN` | P0 |
| 305 | pótzárthelyi: együtt jelenjen meg | potzarthelyi: egyutt jelenjen meg | JOIN | appear together | `08-JOIN` | P0 |
| 306 | feladat: ha a user már létezik töröld | feladat: ha a user mar letezik torold | DROP USER CASCADE | if user exists drop | `01/DROP-USER` | P0 |
| 307 | kérdés: ha a user már létezik töröld | kerdes: ha a user mar letezik torold | DROP USER CASCADE | if user exists drop | `01/DROP-USER` | P0 |
| 308 | szöveg: ha a user már létezik töröld | szoveg: ha a user mar letezik torold | DROP USER CASCADE | if user exists drop | `01/DROP-USER` | P0 |
| 309 | ZH: ha a user már létezik töröld | ZH: ha a user mar letezik torold | DROP USER CASCADE | if user exists drop | `01/DROP-USER` | P0 |
| 310 | pótzárthelyi: ha a user már létezik töröld | potzarthelyi: ha a user mar letezik torold | DROP USER CASCADE | if user exists drop | `01/DROP-USER` | P0 |
| 311 | feladat: töröld a felhasználót | feladat: torold a felhasznalot | DROP USER | drop the user | `01/DROP-USER` | P0 |
| 312 | kérdés: töröld a felhasználót | kerdes: torold a felhasznalot | DROP USER | drop the user | `01/DROP-USER` | P0 |
| 313 | szöveg: töröld a felhasználót | szoveg: torold a felhasznalot | DROP USER | drop the user | `01/DROP-USER` | P0 |
| 314 | ZH: töröld a felhasználót | ZH: torold a felhasznalot | DROP USER | drop the user | `01/DROP-USER` | P0 |
| 315 | pótzárthelyi: töröld a felhasználót | potzarthelyi: torold a felhasznalot | DROP USER | drop the user | `01/DROP-USER` | P0 |
| 316 | feladat: hozz létre usert | feladat: hozz letre usert | CREATE USER | create user | `01-SEMA-USER` | P0 |
| 317 | kérdés: hozz létre usert | kerdes: hozz letre usert | CREATE USER | create user | `01-SEMA-USER` | P0 |
| 318 | szöveg: hozz létre usert | szoveg: hozz letre usert | CREATE USER | create user | `01-SEMA-USER` | P0 |
| 319 | ZH: hozz létre usert | ZH: hozz letre usert | CREATE USER | create user | `01-SEMA-USER` | P0 |
| 320 | pótzárthelyi: hozz létre usert | potzarthelyi: hozz letre usert | CREATE USER | create user | `01-SEMA-USER` | P0 |
| 321 | feladat: adj jogot | feladat: adj jogot | GRANT | grant privilege | `01/14` | P0 |
| 322 | kérdés: adj jogot | kerdes: adj jogot | GRANT | grant privilege | `01/14` | P0 |
| 323 | szöveg: adj jogot | szoveg: adj jogot | GRANT | grant privilege | `01/14` | P0 |
| 324 | ZH: adj jogot | ZH: adj jogot | GRANT | grant privilege | `01/14` | P0 |
| 325 | pótzárthelyi: adj jogot | potzarthelyi: adj jogot | GRANT | grant privilege | `01/14` | P0 |
| 326 | feladat: kvóta tablespace | feladat: kvota tablespace | ALTER USER QUOTA | quota on tablespace | `01-SEMA-USER` | P0 |
| 327 | kérdés: kvóta tablespace | kerdes: kvota tablespace | ALTER USER QUOTA | quota on tablespace | `01-SEMA-USER` | P0 |
| 328 | szöveg: kvóta tablespace | szoveg: kvota tablespace | ALTER USER QUOTA | quota on tablespace | `01-SEMA-USER` | P0 |
| 329 | ZH: kvóta tablespace | ZH: kvota tablespace | ALTER USER QUOTA | quota on tablespace | `01-SEMA-USER` | P0 |
| 330 | pótzárthelyi: kvóta tablespace | potzarthelyi: kvota tablespace | ALTER USER QUOTA | quota on tablespace | `01-SEMA-USER` | P0 |
| 331 | feladat: séma létrehozása Oracle | feladat: sema letrehozasa Oracle | USER ≈ SCHEMA | schema means user | `01-SEMA-USER` | P0 |
| 332 | kérdés: séma létrehozása Oracle | kerdes: sema letrehozasa Oracle | USER ≈ SCHEMA | schema means user | `01-SEMA-USER` | P0 |
| 333 | szöveg: séma létrehozása Oracle | szoveg: sema letrehozasa Oracle | USER ≈ SCHEMA | schema means user | `01-SEMA-USER` | P0 |
| 334 | ZH: séma létrehozása Oracle | ZH: sema letrehozasa Oracle | USER ≈ SCHEMA | schema means user | `01-SEMA-USER` | P0 |
| 335 | pótzárthelyi: séma létrehozása Oracle | potzarthelyi: sema letrehozasa Oracle | USER ≈ SCHEMA | schema means user | `01-SEMA-USER` | P0 |
| 336 | feladat: DROP USER IF EXISTS | feladat: DROP USER IF EXISTS | TILOS 11g | if exists forbidden | `01/DROP-USER` | P0 |
| 337 | kérdés: DROP USER IF EXISTS | kerdes: DROP USER IF EXISTS | TILOS 11g | if exists forbidden | `01/DROP-USER` | P0 |
| 338 | szöveg: DROP USER IF EXISTS | szoveg: DROP USER IF EXISTS | TILOS 11g | if exists forbidden | `01/DROP-USER` | P0 |
| 339 | ZH: DROP USER IF EXISTS | ZH: DROP USER IF EXISTS | TILOS 11g | if exists forbidden | `01/DROP-USER` | P0 |
| 340 | pótzárthelyi: DROP USER IF EXISTS | potzarthelyi: DROP USER IF EXISTS | TILOS 11g | if exists forbidden | `01/DROP-USER` | P0 |
| 341 | feladat: CREATE SCHEMA vakon | feladat: CREATE SCHEMA vakon | NE → CREATE USER | no blind create schema | `01-SEMA-USER` | P0 |
| 342 | kérdés: CREATE SCHEMA vakon | kerdes: CREATE SCHEMA vakon | NE → CREATE USER | no blind create schema | `01-SEMA-USER` | P0 |
| 343 | szöveg: CREATE SCHEMA vakon | szoveg: CREATE SCHEMA vakon | NE → CREATE USER | no blind create schema | `01-SEMA-USER` | P0 |
| 344 | ZH: CREATE SCHEMA vakon | ZH: CREATE SCHEMA vakon | NE → CREATE USER | no blind create schema | `01-SEMA-USER` | P0 |
| 345 | pótzárthelyi: CREATE SCHEMA vakon | potzarthelyi: CREATE SCHEMA vakon | NE → CREATE USER | no blind create schema | `01-SEMA-USER` | P0 |
| 346 | feladat: legalább N karakter | feladat: legalabb N karakter | CHECK LENGTH >= n | at least N characters | `03/CHECK-LENGTH` | P0 |
| 347 | kérdés: legalább N karakter | kerdes: legalabb N karakter | CHECK LENGTH >= n | at least N characters | `03/CHECK-LENGTH` | P0 |
| 348 | szöveg: legalább N karakter | szoveg: legalabb N karakter | CHECK LENGTH >= n | at least N characters | `03/CHECK-LENGTH` | P0 |
| 349 | ZH: legalább N karakter | ZH: legalabb N karakter | CHECK LENGTH >= n | at least N characters | `03/CHECK-LENGTH` | P0 |
| 350 | pótzárthelyi: legalább N karakter | potzarthelyi: legalabb N karakter | CHECK LENGTH >= n | at least N characters | `03/CHECK-LENGTH` | P0 |
| 351 | feladat: ne legyen rövidebb mint | feladat: ne legyen rovidebb mint | CHECK LENGTH | must not be shorter | `03/CHECK-LENGTH` | P0 |
| 352 | kérdés: ne legyen rövidebb mint | kerdes: ne legyen rovidebb mint | CHECK LENGTH | must not be shorter | `03/CHECK-LENGTH` | P0 |
| 353 | szöveg: ne legyen rövidebb mint | szoveg: ne legyen rovidebb mint | CHECK LENGTH | must not be shorter | `03/CHECK-LENGTH` | P0 |
| 354 | ZH: ne legyen rövidebb mint | ZH: ne legyen rovidebb mint | CHECK LENGTH | must not be shorter | `03/CHECK-LENGTH` | P0 |
| 355 | pótzárthelyi: ne legyen rövidebb mint | potzarthelyi: ne legyen rovidebb mint | CHECK LENGTH | must not be shorter | `03/CHECK-LENGTH` | P0 |
| 356 | feladat: hossz ellenőrzés | feladat: hossz ellenorzes | CHECK LENGTH | length check | `03/CHECK-LENGTH` | P0 |
| 357 | kérdés: hossz ellenőrzés | kerdes: hossz ellenorzes | CHECK LENGTH | length check | `03/CHECK-LENGTH` | P0 |
| 358 | szöveg: hossz ellenőrzés | szoveg: hossz ellenorzes | CHECK LENGTH | length check | `03/CHECK-LENGTH` | P0 |
| 359 | ZH: hossz ellenőrzés | ZH: hossz ellenorzes | CHECK LENGTH | length check | `03/CHECK-LENGTH` | P0 |
| 360 | pótzárthelyi: hossz ellenőrzés | potzarthelyi: hossz ellenorzes | CHECK LENGTH | length check | `03/CHECK-LENGTH` | P0 |
| 361 | feladat: jelszó legalább 8 karakter | feladat: jelszo legalabb 8 karakter | CHECK LENGTH>=8 | password min 8 | `03/CHECK-LENGTH` | P0 |
| 362 | kérdés: jelszó legalább 8 karakter | kerdes: jelszo legalabb 8 karakter | CHECK LENGTH>=8 | password min 8 | `03/CHECK-LENGTH` | P0 |
| 363 | szöveg: jelszó legalább 8 karakter | szoveg: jelszo legalabb 8 karakter | CHECK LENGTH>=8 | password min 8 | `03/CHECK-LENGTH` | P0 |
| 364 | ZH: jelszó legalább 8 karakter | ZH: jelszo legalabb 8 karakter | CHECK LENGTH>=8 | password min 8 | `03/CHECK-LENGTH` | P0 |
| 365 | pótzárthelyi: jelszó legalább 8 karakter | potzarthelyi: jelszo legalabb 8 karakter | CHECK LENGTH>=8 | password min 8 | `03/CHECK-LENGTH` | P0 |
| 366 | feladat: cím legalább 3 betű | feladat: cim legalabb 3 betu | CHECK LENGTH>=3 | title min 3 | `03/CHECK-LENGTH` | P0 |
| 367 | kérdés: cím legalább 3 betű | kerdes: cim legalabb 3 betu | CHECK LENGTH>=3 | title min 3 | `03/CHECK-LENGTH` | P0 |
| 368 | szöveg: cím legalább 3 betű | szoveg: cim legalabb 3 betu | CHECK LENGTH>=3 | title min 3 | `03/CHECK-LENGTH` | P0 |
| 369 | ZH: cím legalább 3 betű | ZH: cim legalabb 3 betu | CHECK LENGTH>=3 | title min 3 | `03/CHECK-LENGTH` | P0 |
| 370 | pótzárthelyi: cím legalább 3 betű | potzarthelyi: cim legalabb 3 betu | CHECK LENGTH>=3 | title min 3 | `03/CHECK-LENGTH` | P0 |
| 371 | feladat: elsődleges kulcs | feladat: elsodleges kulcs | PRIMARY KEY | primary key | `03-CONSTRAINT` | P0 |
| 372 | kérdés: elsődleges kulcs | kerdes: elsodleges kulcs | PRIMARY KEY | primary key | `03-CONSTRAINT` | P0 |
| 373 | szöveg: elsődleges kulcs | szoveg: elsodleges kulcs | PRIMARY KEY | primary key | `03-CONSTRAINT` | P0 |
| 374 | ZH: elsődleges kulcs | ZH: elsodleges kulcs | PRIMARY KEY | primary key | `03-CONSTRAINT` | P0 |
| 375 | pótzárthelyi: elsődleges kulcs | potzarthelyi: elsodleges kulcs | PRIMARY KEY | primary key | `03-CONSTRAINT` | P0 |
| 376 | feladat: idegen kulcs | feladat: idegen kulcs | FOREIGN KEY | foreign key | `03-CONSTRAINT` | P0 |
| 377 | kérdés: idegen kulcs | kerdes: idegen kulcs | FOREIGN KEY | foreign key | `03-CONSTRAINT` | P0 |
| 378 | szöveg: idegen kulcs | szoveg: idegen kulcs | FOREIGN KEY | foreign key | `03-CONSTRAINT` | P0 |
| 379 | ZH: idegen kulcs | ZH: idegen kulcs | FOREIGN KEY | foreign key | `03-CONSTRAINT` | P0 |
| 380 | pótzárthelyi: idegen kulcs | potzarthelyi: idegen kulcs | FOREIGN KEY | foreign key | `03-CONSTRAINT` | P0 |
| 381 | feladat: egyedi legyen | feladat: egyedi legyen | UNIQUE | must be unique | `03-CONSTRAINT` | P0 |
| 382 | kérdés: egyedi legyen | kerdes: egyedi legyen | UNIQUE | must be unique | `03-CONSTRAINT` | P0 |
| 383 | szöveg: egyedi legyen | szoveg: egyedi legyen | UNIQUE | must be unique | `03-CONSTRAINT` | P0 |
| 384 | ZH: egyedi legyen | ZH: egyedi legyen | UNIQUE | must be unique | `03-CONSTRAINT` | P0 |
| 385 | pótzárthelyi: egyedi legyen | potzarthelyi: egyedi legyen | UNIQUE | must be unique | `03-CONSTRAINT` | P0 |
| 386 | feladat: kötelező mező | feladat: kotelezo mezo | NOT NULL | mandatory field | `03-CONSTRAINT` | P0 |
| 387 | kérdés: kötelező mező | kerdes: kotelezo mezo | NOT NULL | mandatory field | `03-CONSTRAINT` | P0 |
| 388 | szöveg: kötelező mező | szoveg: kotelezo mezo | NOT NULL | mandatory field | `03-CONSTRAINT` | P0 |
| 389 | ZH: kötelező mező | ZH: kotelezo mezo | NOT NULL | mandatory field | `03-CONSTRAINT` | P0 |
| 390 | pótzárthelyi: kötelező mező | potzarthelyi: kotelezo mezo | NOT NULL | mandatory field | `03-CONSTRAINT` | P0 |
| 391 | feladat: ellenőrző feltétel | feladat: ellenorzo feltetel | CHECK | check constraint | `03-CONSTRAINT` | P0 |
| 392 | kérdés: ellenőrző feltétel | kerdes: ellenorzo feltetel | CHECK | check constraint | `03-CONSTRAINT` | P0 |
| 393 | szöveg: ellenőrző feltétel | szoveg: ellenorzo feltetel | CHECK | check constraint | `03-CONSTRAINT` | P0 |
| 394 | ZH: ellenőrző feltétel | ZH: ellenorzo feltetel | CHECK | check constraint | `03-CONSTRAINT` | P0 |
| 395 | pótzárthelyi: ellenőrző feltétel | potzarthelyi: ellenorzo feltetel | CHECK | check constraint | `03-CONSTRAINT` | P0 |
| 396 | feladat: hivatkozási integritás | feladat: hivatkozasi integritas | FOREIGN KEY | referential integrity | `03-CONSTRAINT` | P0 |
| 397 | kérdés: hivatkozási integritás | kerdes: hivatkozasi integritas | FOREIGN KEY | referential integrity | `03-CONSTRAINT` | P0 |
| 398 | szöveg: hivatkozási integritás | szoveg: hivatkozasi integritas | FOREIGN KEY | referential integrity | `03-CONSTRAINT` | P0 |
| 399 | ZH: hivatkozási integritás | ZH: hivatkozasi integritas | FOREIGN KEY | referential integrity | `03-CONSTRAINT` | P0 |
| 400 | pótzárthelyi: hivatkozási integritás | potzarthelyi: hivatkozasi integritas | FOREIGN KEY | referential integrity | `03-CONSTRAINT` | P0 |
| 401 | feladat: több táblába egyszerre | feladat: tobb tablaba egyszerre | INSERT ALL multi | into several tables | `04/INSERT-ALL-TOBB` | P0 |
| 402 | kérdés: több táblába egyszerre | kerdes: tobb tablaba egyszerre | INSERT ALL multi | into several tables | `04/INSERT-ALL-TOBB` | P0 |
| 403 | szöveg: több táblába egyszerre | szoveg: tobb tablaba egyszerre | INSERT ALL multi | into several tables | `04/INSERT-ALL-TOBB` | P0 |
| 404 | ZH: több táblába egyszerre | ZH: tobb tablaba egyszerre | INSERT ALL multi | into several tables | `04/INSERT-ALL-TOBB` | P0 |
| 405 | pótzárthelyi: több táblába egyszerre | potzarthelyi: tobb tablaba egyszerre | INSERT ALL multi | into several tables | `04/INSERT-ALL-TOBB` | P0 |
| 406 | feladat: vegyél fel 5 rekordot | feladat: vegyel fel 5 rekordot | INSERT ALL | insert 5 rows | `04-ADATFELTOLTES` | P0 |
| 407 | kérdés: vegyél fel 5 rekordot | kerdes: vegyel fel 5 rekordot | INSERT ALL | insert 5 rows | `04-ADATFELTOLTES` | P0 |
| 408 | szöveg: vegyél fel 5 rekordot | szoveg: vegyel fel 5 rekordot | INSERT ALL | insert 5 rows | `04-ADATFELTOLTES` | P0 |
| 409 | ZH: vegyél fel 5 rekordot | ZH: vegyel fel 5 rekordot | INSERT ALL | insert 5 rows | `04-ADATFELTOLTES` | P0 |
| 410 | pótzárthelyi: vegyél fel 5 rekordot | potzarthelyi: vegyel fel 5 rekordot | INSERT ALL | insert 5 rows | `04-ADATFELTOLTES` | P0 |
| 411 | feladat: AUTHOR és BOOK egyszerre | feladat: AUTHOR es BOOK egyszerre | INSERT ALL multi | author and book | `04/INSERT-ALL-TOBB` | P0 |
| 412 | kérdés: AUTHOR és BOOK egyszerre | kerdes: AUTHOR es BOOK egyszerre | INSERT ALL multi | author and book | `04/INSERT-ALL-TOBB` | P0 |
| 413 | szöveg: AUTHOR és BOOK egyszerre | szoveg: AUTHOR es BOOK egyszerre | INSERT ALL multi | author and book | `04/INSERT-ALL-TOBB` | P0 |
| 414 | ZH: AUTHOR és BOOK egyszerre | ZH: AUTHOR es BOOK egyszerre | INSERT ALL multi | author and book | `04/INSERT-ALL-TOBB` | P0 |
| 415 | pótzárthelyi: AUTHOR és BOOK egyszerre | potzarthelyi: AUTHOR es BOOK egyszerre | INSERT ALL multi | author and book | `04/INSERT-ALL-TOBB` | P0 |
| 416 | add meg az összes sort | add meg az osszes sort | SELECT | give all rows | `10/99` | P0 |
| 417 | rendezd ABC szerint | rendezd ABC szerint | ORDER BY | order alphabetically | `99-MASTER` | P0 |
| 418 | csökkenő sorrend | csokkeno sorrend | ORDER BY DESC | descending order | `99-MASTER` | P0 |
| 419 | különböző értékek | kulonbozo ertekek | DISTINCT | distinct values | `10-WHERE` | P1 |
| 420 | átlag számítás | atlag szamitas | AVG | average calculation | `07-VIEW` | P0 |
| 421 | összeg számítás | osszeg szamitas | SUM | sum calculation | `07-VIEW` | P0 |
| 422 | minimum maximum | minimum maximum | MIN/MAX | min max | `07-VIEW` | P0 |
| 423 | darabszám | darabszam | COUNT | row count | `07-VIEW` | P0 |
| 424 | nézet csere | nezet csere | CREATE OR REPLACE VIEW | replace view | `07-VIEW` | P0 |
| 425 | korrelált alkérdés | korrelalt alkerdes | correlated subquery | correlated subquery | `09-TOP1` | P1 |
| 426 | halmazunió | halmazunio | UNION | set union | `19-HALMAZ` | P2 |
| 427 | típus NUMBER | tipus NUMBER | NUMBER | number type | `02-TABLA` | P0 |
| 428 | típus VARCHAR2 | tipus VARCHAR2 | VARCHAR2 | varchar2 type | `02-TABLA` | P0 |
| 429 | típus DATE | tipus DATE | DATE | date type | `02/11` | P0 |
| 430 | ORA-00942 | ORA-00942 | tábla/jog | table or view missing | `20-ORA-HIBAK` | P0 |
| 431 | ORA-02291 | ORA-02291 | FK szülő hiány | parent key not found | `20-ORA-HIBAK` | P0 |
| 432 | ORA-01950 | ORA-01950 | QUOTA | no privileges on tablespace | `01-SEMA-USER` | P0 |
| 433 | zero knowledge teszt | zero knowledge teszt | ZK | zk self test | `00-START/ZERO-KNOWLEDGE` | P1 |
| 434 | coverage report | coverage report | COVERAGE V2 | coverage report | `COVERAGE-REPORT` | P2 |
| 435 | integrált SUM ROW_NUMBER | integralt SUM ROW_NUMBER | SUM+ROW_NUMBER | integrated sum row_number | `18/INTEGRATED` | P1 |

| 436 | azokat is amelyekhez meg nem tartozik semmi | azokat is amelyekhez meg nem tartozik semmi | LEFT JOIN | also those nothing related ascii | `08-JOIN` | P0 |
| 437 | minden rekord fuggetlenul a kapcsolattol | minden rekord fuggetlenul a kapcsolattol | LEFT JOIN | every record regardless ascii | `08-JOIN` | P0 |
| 438 | akkor is mutasd ha nulla kapcsolodo rekordja van | akkor is mutasd ha nulla kapcsolodo rekordja van | LEFT JOIN | zero related ascii | `08/LEFT-JOIN-COUNT` | P0 |
| 439 | kapcsolodo rekord hianyaban is | kapcsolodo rekord hianyaban is | LEFT JOIN | absence related ascii | `08-JOIN` | P0 |
| 440 | nemtudom mit keressek | nemtudom mit keressek | NEM-TUDOM | searchless mode | `00-START/NEM-TUDOM` | P0 |
| 441 | 12 kerdeses fallback | 12 kerdeses fallback | ISMERETLEN | unknown 12q | `00-START/ISMERETLEN` | P0 |
| 442 | MIT IRJ HONNAN VESZEM | MIT IRJ HONNAN VESZEM | placeholder UX | placeholder guidance | `00-START` | P0 |
| 443 | 5 masodperces felismeres | 5 masodperces felismeres | 5s recogn | five second recognition | `P0 quick top` | P0 |
| 444 | P0 max 1 katt | P0 max 1 katt | 1-click SQL | one click skeleton | `00-START` | P0 |
| 445 | integralt kombinacios sablon | integralt kombinacios sablon | integrated | combo template | `OT/18/08/12` | P0 |
| 446 | kereses teszt mondat 1 left join | kereses teszt mondat 1 left join | LEFT JOIN | search test 1 | `08-JOIN` | P0 |
| 447 | kereses teszt mondat 2 left join | kereses teszt mondat 2 left join | LEFT JOIN | search test 2 | `08-JOIN` | P0 |
| 448 | kereses teszt mondat 3 left join | kereses teszt mondat 3 left join | LEFT JOIN | search test 3 | `08-JOIN` | P0 |
| 449 | kereses teszt mondat 4 left join | kereses teszt mondat 4 left join | LEFT JOIN | search test 4 | `08-JOIN` | P0 |
| 450 | kereses teszt mondat 5 left join | kereses teszt mondat 5 left join | LEFT JOIN | search test 5 | `08-JOIN` | P0 |
| 451 | kereses teszt mondat 6 left join | kereses teszt mondat 6 left join | LEFT JOIN | search test 6 | `08-JOIN` | P0 |
| 452 | kereses teszt mondat 7 left join | kereses teszt mondat 7 left join | LEFT JOIN | search test 7 | `08-JOIN` | P0 |
| 453 | kereses teszt mondat 8 left join | kereses teszt mondat 8 left join | LEFT JOIN | search test 8 | `08-JOIN` | P0 |
| 454 | kereses teszt mondat 9 left join | kereses teszt mondat 9 left join | LEFT JOIN | search test 9 | `08-JOIN` | P0 |
| 455 | kereses teszt mondat 10 left join | kereses teszt mondat 10 left join | LEFT JOIN | search test 10 | `08-JOIN` | P0 |
| 456 | kereses teszt mondat 11 left join | kereses teszt mondat 11 left join | LEFT JOIN | search test 11 | `08-JOIN` | P0 |
| 457 | kereses teszt mondat 12 left join | kereses teszt mondat 12 left join | LEFT JOIN | search test 12 | `08-JOIN` | P0 |
| 458 | kereses teszt mondat 13 left join | kereses teszt mondat 13 left join | LEFT JOIN | search test 13 | `08-JOIN` | P0 |
| 459 | kereses teszt mondat 14 left join | kereses teszt mondat 14 left join | LEFT JOIN | search test 14 | `08-JOIN` | P0 |
| 460 | kereses teszt mondat 15 left join | kereses teszt mondat 15 left join | LEFT JOIN | search test 15 | `08-JOIN` | P0 |
| 461 | kereses teszt mondat 16 left join | kereses teszt mondat 16 left join | LEFT JOIN | search test 16 | `08-JOIN` | P0 |
| 462 | kereses teszt mondat 17 left join | kereses teszt mondat 17 left join | LEFT JOIN | search test 17 | `08-JOIN` | P0 |
| 463 | kereses teszt mondat 18 left join | kereses teszt mondat 18 left join | LEFT JOIN | search test 18 | `08-JOIN` | P0 |
| 464 | kereses teszt mondat 19 left join | kereses teszt mondat 19 left join | LEFT JOIN | search test 19 | `08-JOIN` | P0 |
| 465 | kereses teszt mondat 20 left join | kereses teszt mondat 20 left join | LEFT JOIN | search test 20 | `08-JOIN` | P0 |
| 466 | kereses teszt mondat 21 left join | kereses teszt mondat 21 left join | LEFT JOIN | search test 21 | `08-JOIN` | P0 |
| 467 | kereses teszt mondat 22 left join | kereses teszt mondat 22 left join | LEFT JOIN | search test 22 | `08-JOIN` | P0 |
| 468 | kereses teszt mondat 23 left join | kereses teszt mondat 23 left join | LEFT JOIN | search test 23 | `08-JOIN` | P0 |
| 469 | kereses teszt mondat 24 left join | kereses teszt mondat 24 left join | LEFT JOIN | search test 24 | `08-JOIN` | P0 |
| 470 | kereses teszt mondat 25 left join | kereses teszt mondat 25 left join | LEFT JOIN | search test 25 | `08-JOIN` | P0 |
| 471 | kereses teszt mondat 26 left join | kereses teszt mondat 26 left join | LEFT JOIN | search test 26 | `08-JOIN` | P0 |
| 472 | kereses teszt mondat 27 left join | kereses teszt mondat 27 left join | LEFT JOIN | search test 27 | `08-JOIN` | P0 |
| 473 | kereses teszt mondat 28 left join | kereses teszt mondat 28 left join | LEFT JOIN | search test 28 | `08-JOIN` | P0 |
| 474 | kereses teszt mondat 29 left join | kereses teszt mondat 29 left join | LEFT JOIN | search test 29 | `08-JOIN` | P0 |
| 475 | kereses teszt mondat 30 left join | kereses teszt mondat 30 left join | LEFT JOIN | search test 30 | `08-JOIN` | P0 |
| 476 | kereses teszt mondat 31 left join | kereses teszt mondat 31 left join | LEFT JOIN | search test 31 | `08-JOIN` | P0 |
| 477 | kereses teszt mondat 32 left join | kereses teszt mondat 32 left join | LEFT JOIN | search test 32 | `08-JOIN` | P0 |
| 478 | kereses teszt mondat 33 left join | kereses teszt mondat 33 left join | LEFT JOIN | search test 33 | `08-JOIN` | P0 |
| 479 | kereses teszt mondat 34 left join | kereses teszt mondat 34 left join | LEFT JOIN | search test 34 | `08-JOIN` | P0 |
| 480 | kereses teszt mondat 35 left join | kereses teszt mondat 35 left join | LEFT JOIN | search test 35 | `08-JOIN` | P0 |

## Meta
- Sorok: **480** (cél ~400–500).
- Ékezet nélküli oszlop: CTRL+F ékezet nélkül is.
- Quick rövidítések a `00-20-PERCES-ZH/` alatt; canonical README ha elakadsz.
- Nincs találat → [`NEM-TUDOM-MIT-KERESSEK.md`](NEM-TUDOM-MIT-KERESSEK.md) · [`ISMERETLEN-FELADAT-FALLBACK.md`](ISMERETLEN-FELADAT-FALLBACK.md)

→ [`00-LEPESROL-LEPESRE.md`](00-LEPESROL-LEPESRE.md) · [`FELADATSZOVEG-INDEX.md`](FELADATSZOVEG-INDEX.md) (rövidebb index **megmarad**)
