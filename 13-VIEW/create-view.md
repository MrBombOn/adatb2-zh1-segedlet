# CREATE VIEW

## MI EZ?
Nézet létrehozása SELECT-ből.

## MIKOR KELL?
„Hozz létre nézetet, amely…”

## HONNAN ISMEREM FEL?
VIEW AS SELECT.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
CREATE VIEW <nezet> AS
SELECT <oszlopok>
FROM   <tabla>
WHERE  <feltetel>;
```

## MIT JELENT SORONKÉNT?
A nézet lekérdezésekor a tárolt SELECT fut.

## TIPIKUS HIBA
Oszlopaliasok hiánya összetett kifejezésnél.

## HOGYAN ELLENŐRZÖM?
SELECT * FROM <nezet>;

## ZH GYORS EMLÉKEZTETŐ
Elmentett lekérdezés → VIEW.
