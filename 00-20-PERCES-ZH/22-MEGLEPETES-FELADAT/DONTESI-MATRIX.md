# Döntési mátrix – feladatszöveg → eszköz

| Ha a szöveg… | Eszköz | Mappa | P |
|--------------|--------|-------|---|
| user / séma / kvóta | CREATE USER / GRANT / QUOTA | 01-SEMA-USER | P0 |
| hozz létre táblát | CREATE TABLE | 02-TABLA-LETREHOZAS | P0 |
| PK/FK/UK/CK/NN | CONSTRAINT | 03-CONSTRAINT | P0 |
| vegyél fel sorokat | INSERT / INSERT ALL | 04-ADATFELTOLTES | P0 |
| üres másolat | CTAS 1=0 | 05-MASOLAT-ES-MERGE | P0 |
| ha van/ha nincs | MERGE | 05-MASOLAT-ES-MERGE | P0 |
| szétválogatás | INSERT FIRST/ALL | 06-SZETVALOGATAS | P0 |
| nézet / csoportonként | VIEW / GROUP / LISTAGG | 07-VIEW-ES-CSOPORTOSITAS | P0 |
| együtt / pár nélkül | JOIN / LEFT | 08-JOIN-ES-KAPCSOLAT | P0 |
| leg… / azok akik | ROWNUM / subquery | 09-TOP1-ES-SUBQUERY | P0 |
| csak azok ahol | WHERE | 10-WHERE-ES-SZURES | P0 |
| dátum / formátum | TO_DATE/TO_CHAR | 11-DATUM | P0 |
| módosíts / törölj sor | UPDATE/DELETE | 12-DML | P1 |
| adj oszlopot / drop tábla | ALTER/DROP | 13-DDL | P1 |
| adj jogot | GRANT | 14-JOGOSULTSAG | P1 |
| véglegesíts | COMMIT | 15-TRANZAKCIO | P1 |
| álnév | SYNONYM | 16-SYNONYM | P2 |
| NVL / UPPER | függvény | 17-FUGGVENYEK | P1 |
| sorszám / rang | ROW_NUMBER | 18-ANALITIKUS | P2 |
| unió / metszet | UNION/… | 19-HALMAZMUVELETEK | P2 |
| ORA-xxxxx | hibakód | 20-ORA-HIBAK | P0 |
| ha már létezik user / töröld | DROP USER CASCADE | 01/DROP-USER | P0 |
| legalább N karakter | CHECK LENGTH | 03/CHECK-LENGTH | P0 |
| több táblába egyszerre | INSERT ALL multi | 04/INSERT-ALL-TOBB | P0 |
| mai nap idő nélkül | TRUNC(SYSDATE) | 11/DATUM-IDOPONT | P0 |
| N%-kal módosíts | * (1±n/100) | 12/SZAZALEKOS | P0 |
| akiknek van … frissítsd | UPDATE EXISTS | 12/UPDATE-EXISTS | P0 |
| ablak / OVER / rang / partíció összeg | analitikus | 18-ANALITIKUS | P1 |
| 0 darab / COUNT jobb = 0 | LEFT COUNT | 08/NINCS-PAR | P0 |
| kis-nagy LIKE | UPPER LIKE | 10/LIKE-CASE | P0 |
| 5 komponenses SELECT | OT-KOMPONENSES | 00-START | P0 |
