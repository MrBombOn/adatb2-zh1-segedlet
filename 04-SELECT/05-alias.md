# Alias (oszlop / tábla)

## MI EZ?
Átmeneti név a lekérdezésben.

## MIKOR KELL?
Olvasható fejléc; rövid táblanév JOIN-nál.

## HONNAN ISMEREM FEL?
AS kulcsszó (oszlopnál opcionális).

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT <oszlop> AS <oszlop_alias>
FROM   <tabla> <tabla_alias>;
```

## MIT JELENT SORONKÉNT?
Táblaalias kötelezően hasznos többtáblás lekérdezésnél.

## TIPIKUS HIBA
Alias idézőjelezése érzékennyé teszi a kis/nagybetűt.

## HOGYAN ELLENŐRZÖM?
Olvasd vissza a SELECT listát magyarul.

## ZH GYORS EMLÉKEZTETŐ
JOIN-nál adj táblaalast, és azzal kvalifikáld az oszlopokat.
