# Feladatszöveg index

Ctrl+F a magyar megfogalmazásra → mappa. Oracle 11g. Nincs kész megoldásbank.

| # | Ha ezt látod / így fogalmazzák | Eszköz | Mappa | P |
|---|-------------------------------|--------|-------|---|
| 1 | listázd / mutasd / add vissza | SELECT | `10-WHERE-ES-SZURES / 99` | P0 |
| 2 | csak azok / ahol / feltéve hogy | WHERE | `10-WHERE-ES-SZURES` | P0 |
| 3 | csökkenő / növekvő / ABC sorrend | ORDER BY | `99-MASTER` | P0 |
| 4 | különböző értékek | DISTINCT / UNIQUE | `03 / 10` | P1 |
| 5 | tartozik hozzá / együtt jelenjen meg | JOIN | `08-JOIN-ES-KAPCSOLAT` | P0 |
| 6 | akkor is, ha nincs neki … | LEFT JOIN | `08-JOIN-ES-KAPCSOLAT` | P0 |
| 7 | minden X Y nélkül | LEFT + IS NULL | `08-JOIN-ES-KAPCSOLAT` | P0 |
| 8 | hiányzó kapcsolat / nincs pár | LEFT + IS NULL | `08` | P0 |
| 9 | X-enként / csoportonként | GROUP BY | `07-VIEW-ES-CSOPORTOSITAS` | P0 |
| 10 | legalább N darab a csoportban | HAVING | `07` | P0 |
| 11 | hány / darabszám | COUNT | `07` | P0 |
| 12 | összeg / átlag / min / max | SUM/AVG/MIN/MAX | `07` | P0 |
| 13 | lista egy cellában / összefűzve | LISTAGG | `07` | P0 |
| 14 | hozz létre nézetet | CREATE VIEW | `07` | P0 |
| 15 | vegyél fel új sort | INSERT | `04-ADATFELTOLTES` | P0 |
| 16 | több sort egyszerre / 5 rekord | INSERT ALL | `04` | P0 |
| 17 | módosítsd az értéket | UPDATE | `12-DML` | P1 |
| 18 | töröld a sorokat | DELETE | `12-DML` | P1 |
| 19 | ha létezik frissíts, különben vedd fel | MERGE | `05-MASOLAT-ES-MERGE` | P0 |
| 20 | üres szerkezeti másolat | CTAS WHERE 1=0 | `05` | P0 |
| 21 | másold a struktúrát adat nélkül | CTAS 1=0 | `05` | P0 |
| 22 | szétválogatás dátum szerint | INSERT FIRST/ALL | `06-SZETVALOGATAS` | P0 |
| 23 | ha … akkor ebbe a táblába | WHEN … INTO | `06` | P0 |
| 24 | hozz létre táblát | CREATE TABLE | `02-TABLA-LETREHOZAS` | P0 |
| 25 | oszlopok legyenek … típusúak | CREATE TABLE típusok | `02` | P0 |
| 26 | elsődleges kulcs | PRIMARY KEY | `03-CONSTRAINT` | P0 |
| 27 | idegen kulcs / hivatkozzon | FOREIGN KEY | `03` | P0 |
| 28 | egyedi legyen | UNIQUE | `03` | P0 |
| 29 | kötelező mező / ne lehessen üres | NOT NULL | `03` | P0 |
| 30 | ellenőrző feltétel / csak ezek | CHECK | `03` | P0 |
| 31 | hozz létre usert / felhasználót | CREATE USER | `01-SEMA-USER` | P0 |
| 32 | séma létrehozása (Oracle) | USER ≈ SCHEMA | `01` | P0 |
| 33 | adj jogot / engedélyezd | GRANT | `01 / 14` | P0 |
| 34 | kvóta / tablespace hely | QUOTA | `01` | P0 |
| 35 | vedd el a jogot | REVOKE | `14-JOGOSULTSAG` | P1 |
| 36 | a legdrágább / legújabb / top 1 | ROWNUM | `09-TOP1-ES-SUBQUERY` | P0 |
| 37 | első N sor rendezés után | ROWNUM alkérdés | `09` | P0 |
| 38 | nagyobb mint az átlag | subquery AVG | `09` | P0 |
| 39 | azok akik / létezik olyan | EXISTS / IN | `09` | P0 |
| 40 | nincs olyan / nem létezik | NOT EXISTS | `09` | P0 |
| 41 | formázott dátum | TO_CHAR | `11-DATUM` | P0 |
| 42 | szövegből dátum | TO_DATE | `11` | P0 |
| 43 | aktuális idő / ma | SYSDATE | `11` | P0 |
| 44 | hiányzik / nincs kitöltve | IS NULL | `10` | P0 |
| 45 | ha nincs legyen 0 / N/A | NVL | `17-FUGGVENYEK` | P1 |
| 46 | nagybetűre / részstring | UPPER/SUBSTR | `17` | P1 |
| 47 | véglegesítsd | COMMIT | `15-TRANZAKCIO` | P1 |
| 48 | vonjad vissza | ROLLBACK | `15` | P1 |
| 49 | adj oszlopot a táblához | ALTER TABLE ADD | `13-DDL` | P1 |
| 50 | töröld a táblát | DROP TABLE | `13` | P1 |
| 51 | álnév / rövidebb néven | SYNONYM | `16-SYNONYM` | P2 |
| 52 | unió / metszet / különbség | UNION/INTERSECT/MINUS | `19` | P2 |
| 53 | sorszámozás / rang | ROW_NUMBER/RANK | `18-ANALITIKUS` | P2 |
| 54 | automatikus azonosító | SEQUENCE (nem IDENTITY) | `02` | P0 |
| 55 | LIMIT / FETCH FIRST a szövegben mint ötlet | TILOS → ROWNUM | `09` | P0 |
| 56 | ORA-00942 | tábla/jog/séma | `20-ORA-HIBAK` | P0 |
| 57 | ORA-02291 | FK szülő hiány | `20 / 03` | P0 |
| 58 | ORA-00001 | unique/PK | `20 / 03` | P0 |
| 59 | ORA-00979 | GROUP BY hiány | `20 / 07` | P0 |
| 60 | ORA-01861 | dátum maszk | `20 / 11` | P0 |
| 61 | ORA-01950 | kvóta | `20 / 01` | P0 |
| 62 | ORA-01031 | privilege | `20 / 14` | P0 |
| 63 | előbb a szülő tábla | függőség | `00-START menet` | P0 |
| 64 | kész megoldást másoljak? | NEM — placeholder | `README szabályok` | P0 |
| 65 | AUTHOR és BOOK együtt | JOIN minta világ | `08` | P0 |
| 66 | STUDENT / COURSE / ENROLLMENT | JOIN/GROUP világ | `08 / 07` | P0 |
| 67 | CITY / PERSON | LEFT „nincs lakó” | `08` | P0 |
| 68 | CUSTOMER / ORDER | 1:N tipikus | `08 / 04` | P0 |
| 69 | CAR / OWNER | JOIN/LEFT | `08` | P0 |
| 70 | teljesen más feladat jön | döntési fa | `22-MEGLEPETES-FELADAT` | P0 |
| 71 | WITH GRANT OPTION | object jog továbbadás | `14` | P1 |
| 72 | WITH ADMIN OPTION | system jog továbbadás | `14` | P1 |
| 73 | SAVEPOINT | köztes pont | `15` | P2 |
| 74 | TRUNCATE | ürítés DDL jelleg | `13` | P1 |
| 75 | CASE WHEN | feltételes kifejezés | `17` | P1 |
| 76 | BETWEEN … AND | intervallum | `10` | P0 |
| 77 | IN (…) | halmaz tagság | `10 / 09` | P0 |
| 78 | LIKE | mintaillesztés | `10` | P0 |
| 79 | ADD_MONTHS / EXTRACT | dátum számítás | `11` | P1 |
| 80 | CREATE SEQUENCE | ID 11g | `02` | P0 |
| 81 | DESC / user_tables | ellenőrzés | `99 / dictionary` | P1 |
| 82 | dual | egy soros teszt | `99` | P0 |
| 83 | implicit COMMIT DDL után | tranzakció figyelem | `15 / 13` | P1 |
| 84 | nem értem a feladatsort | MIT-KER + index | `00-START` | P0 |
| 85 | mit írjak a helyőrzőbe | MIT-IRHATOK-IDE | `00-START` | P0 |
| 86 | keresés docs-ban | 21-KERESOSEGED | `21` | P1 |
| 87 | P0 mi az | kötelező ZH mag | `COURSE-COVERAGE` | P0 |
| 88 | P2 tartalék | ha van idő | `16/18/19` | P2 |
| 89 | nézet + csoport + lista együtt | VIEW+GROUP+LISTAGG | `07` | P0 |
| 90 | korrelált alkérdés | EXISTS | `09` | P1 |
| 91 | self join | ugyanaz a tábla 2 alias | `08 / tanuló JOIN` | P2 |
| 92 | FULL OUTER JOIN | ritkább | `tanuló 07-JOIN` | P2 |
| 93 | role hozzárendelés | GRANT role TO user | `14` | P2 |
| 94 | tablespace USERS kötelező? | NEM vakon — KÖRNYEZETFÜGGŐ | `01` | P0 |
| 95 | CREATE SCHEMA utasítás | Kerüld vakon; USER≈SCHEMA | `01` | P0 |
| 96 | MySQL backtick / PG :: | TILOS | `22 / README` | P0 |
| 97 | AUTO_INCREMENT / SERIAL | TILOS → SEQUENCE | `02` | P0 |
| 98 | OFFSET … ROWS | TILOS 12c+ | `09` | P0 |
| 99 | beadás előtti checklist | 16 régi → témák 10s + ORA | `00/20` | P0 |
| 100 | próba-ZH gyakorlás | 20-GYAKORLAS/PROBA-ZH | `gyakorlás` | P1 |
| 101 | korábbi mintafelismerés | 23-KORABBI-ZH-MINTAK | `minták` | P1 |
| 102 | részletes magyarázat kell | tanulói réteg link a README-ből | `01–22` | P0 |
| 103 | gyors minden minta | 99-MASTER | `99` | P0 |
| 104 | szintaxis Ctrl+F | SZINTAXIS-INDEX | `99` | P0 |
| 105 | ha elakadtam kereső | KERESÉS blokk | `minden README` | P0 |
| 106 | null kezelés összehasonlításban | IS NULL / NVL | `10 / 17` | P0 |
| 107 | GROUP BY-ból kimaradt oszlop | ORA-00979 | `07 / 20` | P0 |
| 108 | FK INSERT sorrend | előbb szülő | `04 / 00 menet` | P0 |
| 109 | VIEW a SELECT után a függőségben | függőségi lánc | `00-START` | P0 |
| 110 | több tábla neve + „és” | JOIN kulcs keresés | `08` | P0 |
| 111 | azok az X ahol Y darab ≥ n | GROUP BY + HAVING | `07` | P0 |
| 112 | másold át feltétellel más táblába | INSERT … SELECT / FIRST | `06 / 04` | P0 |
| 113 | upsert | MERGE | `05` | P0 |
| 114 | klónozás struktúra | CTAS | `05` | P0 |
| 115 | PL/SQL Developer csatlakozás | ZH technikai menet | `00-START` | P0 |
| 116 | SELECT * FROM dual ellenőrzés | kapcsolat él | `00 ZH menet` | P0 |
| 117 | időhiány: biztos pontok először | 20-PERCES-MENET | `00` | P0 |
| 118 | meglepetés mátrix | DONTESI-MATRIX | `22` | P0 |
| 119 | valid vs tipikus vs környezetfüggő | értékek jelölés | `MIT-IRHATOK` | P0 |
| 120 | alternatív entitás példa kell | AUTHOR/BOOK… | `minden README` | P0 |
| 121 | nincs TERMEK megoldás | szándékos | `README` | P0 |
| 122 | 3 szint: gyors/közepes/részletes | rétegek | `README` | P0 |
| 123 | P0 max 2 katt README-ből | 00-START térkép | `00` | P0 |


| 151 | ha a user már létezik / töröld a usert | DROP USER CASCADE | `01-SEMA-USER/DROP-USER` | P0 |
| 152 | legalább N karakter / LENGTH | CHECK LENGTH | `03-CONSTRAINT/CHECK-LENGTH` | P0 |
| 153 | több különböző táblába egyszerre | INSERT ALL multi-table | `04/INSERT-ALL-TOBB-TABLABA` | P0 |
| 154 | mai nap idő nélkül / napra vágás | TRUNC(SYSDATE) | `11/DATUM-IDOPONT-NELKUL` | P0 |
| 155 | N%-kal emeld / csökkentsd | százalékos UPDATE | `12/SZAZALEKOS-MODOSITAS` | P0 |
| 156 | akiknek van kapcsolódó / ha létezik gyerek | UPDATE EXISTS | `12/UPDATE-HA-VAN…` | P0 |
| 157 | analitikus / ablak / OVER | window functions | `18-ANALITIKUS` | P1 |
| 158 | partíciónként összeg / rang | SUM/ROW_NUMBER OVER | `18` | P1 |
| 159 | COUNT jobb oldal = 0 / 0 darab gyerek | LEFT + COUNT(pk)=0 | `08/LEFT-JOIN-COUNT-NULL` | P0 |
| 160 | kis-nagy betű mindegy LIKE | UPPER/LOWER LIKE | `10/LIKE-CASE-INSENSITIVE` | P0 |
| 161 | 5 részes lekérdezés | LEFT+COUNT+GROUP+LIKE+HAVING | `00-START/OT-KOMPONENSES…` | P0 |
| 162 | komponensekre bontás | döntési út | `00-START/FELADAT-KOMPONENSEKRE…` | P0 |
| 163 | lépésről lépésre döntés | §19 fa | `00-START/00-LEPESROL-LEPESRE` | P0 |
| 164 | 3 perces gyorsút | §20 | `00-START/00-ZH-GYORS-3-PERC` | P0 |
| 165 | pót ZH minták | mintafelismerés | `23/01-pot-zh…` | P0 |
| 166 | közös eredeti+pót | változatmátrix | `23/02-KOZOS…` | P1 |
| 167 | zero-knowledge önellenőrzés | ZK tesztek | `00-START/ZERO-KNOWLEDGE-TESZTEK` | P1 |


| 168 | azokat is, amelyekhez még nem tartozik semmi | LEFT JOIN | `08-JOIN-ES-KAPCSOLAT` | P0 |
| 169 | minden rekord, függetlenül a kapcsolattól | LEFT JOIN | `08` | P0 |
| 170 | akkor is mutasd, ha nulla kapcsolódó rekordja van | LEFT JOIN (+ COUNT/IS NULL) | `08/LEFT-JOIN-COUNT-NULL` | P0 |
| 171 | kapcsolódó rekord hiányában is | LEFT JOIN | `08` | P0 |
| 172 | azokat is amelyekhez meg nem tartozik semmi (ék. nélkül) | LEFT JOIN | `08` | P0 |
| 173 | fuggetlenul a kapcsolattol (ék. nélkül) | LEFT JOIN | `08` | P0 |
| 174 | ZH-SZOVEG-FELISMERES-INDEX (nagy) | felismerő | `00-START/ZH-SZOVEG-FELISMERES-INDEX` | P0 |
| 175 | nem tudom mit keressek | UX fallback | `00-START/NEM-TUDOM-MIT-KERESSEK` | P0 |
| 176 | ismeretlen feladat 12 kérdés | UX fallback | `00-START/ISMERETLEN-FELADAT-FALLBACK` | P0 |

## Hogyan használd

1. Ctrl+F egy magyar szóra a feladatszövegből.
2. Nyisd a mappa `README.md`-jét.
3. Töltsd ki a helyőrzőket a **feladatsor** neveivel.
4. Futtasd le a 10s ellenőrzést.
5. ORA esetén `20-ORA-HIBAK`.

## Kapcsolódó

- [`MIT-KER-A-FELADAT.md`](MIT-KER-A-FELADAT.md)
- [`MIT-IRHATOK-IDE.md`](MIT-IRHATOK-IDE.md)
- [`../22-MEGLEPETES-FELADAT/DONTESI-MATRIX.md`](../22-MEGLEPETES-FELADAT/DONTESI-MATRIX.md)

## Megjegyzés

Ez index, nem megoldás. A sorok szándékosan redundánsak a szinonimák miatt.

További szinonimák: „add meg”, „készíts”, „állíts elő”, „számold meg”, „rendezd”.
Mindig a feladatsor saját tábla-/oszlopneveit írd a helyőrzőkbe.

