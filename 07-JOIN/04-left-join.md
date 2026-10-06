# LEFT JOIN

## MI EZ?
Bal tábla minden sora + jobb egyezés vagy NULL.

## MIKOR KELL?
„Akkor is listázd, ha nincs pár.”

## HONNAN ISMEREM FEL?
„minden X, Y ha van”.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT <oszlopok>
FROM   <bal>  <b>
LEFT JOIN <jobb> <j> ON <j>.<fk> = <b>.<pk>;
```

## MIT JELENT SORONKÉNT?
Nincs egyezés → jobb oldali oszlopok NULL.

## TIPIKUS HIBA
WHERE jobb.pk IS NULL → „nincs pár” szűrés.

## HOGYAN ELLENŐRZÖM?
Van-e NULL a jobb oldalon, ahol vártad?

## ZH GYORS EMLÉKEZTETŐ
„Hiányzó kapcsolat is kell” → LEFT.
