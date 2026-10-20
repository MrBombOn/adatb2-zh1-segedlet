# ZH gyors — 3 perc (§20 fő) + UX

**P0** · Oracle 11g · 1 katt = önálló quick SQL-vázzal

> Placeholder minták. Ne másold be ZH-válaszként.

## 5 MÁSODPERCES — LEFT JOIN?

Ha ezt látod → [`../08-JOIN-ES-KAPCSOLAT/00-ZH-GYORS-3-PERC.md`](../08-JOIN-ES-KAPCSOLAT/00-ZH-GYORS-3-PERC.md):

- azokat is, amelyekhez még nem tartozik semmi
- minden rekord, függetlenül a kapcsolattól
- akkor is mutasd, ha nulla kapcsolódó rekordja van
- kapcsolódó rekord hiányában is

Ékezet nélkül: `fuggetlenul` · `hianyaban` · `kapcsolodo` · `meg nem tartozik`.

## 3 perc – mit nyiss

| Ha ezt látod | Nyisd (≤3 perc, önálló SQL) |
|--------------|------------------------------|
| DROP USER ha van | [`../01-SEMA-USER/DROP-USER.md`](../01-SEMA-USER/DROP-USER.md) |
| LENGTH / legalább N karakter | [`../03-CONSTRAINT/CHECK-LENGTH.md`](../03-CONSTRAINT/CHECK-LENGTH.md) |
| INSERT több táblába | [`../04-ADATFELTOLTES/INSERT-ALL-TOBB-TABLABA.md`](../04-ADATFELTOLTES/INSERT-ALL-TOBB-TABLABA.md) |
| mai nap / idő nélkül | [`../11-DATUM/DATUM-IDOPONT-NELKUL.md`](../11-DATUM/DATUM-IDOPONT-NELKUL.md) |
| N% emelés/csökkentés | [`../12-DML/SZAZALEKOS-MODOSITAS.md`](../12-DML/SZAZALEKOS-MODOSITAS.md) |
| UPDATE ha van gyerek | [`../12-DML/UPDATE-HA-VAN-KAPCSOLODO-REKORD.md`](../12-DML/UPDATE-HA-VAN-KAPCSOLODO-REKORD.md) |
| rang / partíció összeg | [`../18-ANALITIKUS/INTEGRATED-SUM-ROW-NUMBER.md`](../18-ANALITIKUS/INTEGRATED-SUM-ROW-NUMBER.md) |
| LEFT / nincs pár / COUNT=0 | [`../08-JOIN-ES-KAPCSOLAT/00-ZH-GYORS-3-PERC.md`](../08-JOIN-ES-KAPCSOLAT/00-ZH-GYORS-3-PERC.md) |
| LIKE kis/nagy | [`../10-WHERE-ES-SZURES/LIKE-CASE-INSENSITIVE.md`](../10-WHERE-ES-SZURES/LIKE-CASE-INSENSITIVE.md) |
| HAVING COUNT | [`../07-VIEW-ES-CSOPORTOSITAS/HAVING-COUNT.md`](../07-VIEW-ES-CSOPORTOSITAS/HAVING-COUNT.md) |
| 5 komponens | [`OT-KOMPONENSES-LEKERDEZES.md`](OT-KOMPONENSES-LEKERDEZES.md) |
| nem tudom mit keressek | [`NEM-TUDOM-MIT-KERESSEK.md`](NEM-TUDOM-MIT-KERESSEK.md) |
| ismeretlen feladat | [`ISMERETLEN-FELADAT-FALLBACK.md`](ISMERETLEN-FELADAT-FALLBACK.md) |
| nagy felismerő index | [`ZH-SZOVEG-FELISMERES-INDEX.md`](ZH-SZOVEG-FELISMERES-INDEX.md) |

**TILOS reflex:** FETCH FIRST, LIMIT, IDENTITY, DROP IF EXISTS (user).

→ [`00-LEPESROL-LEPESRE.md`](00-LEPESROL-LEPESRE.md)
