# MERGE

## MI EZ?
UPSERT: ha van, UPDATE; ha nincs, INSERT.

## MIKOR KELL?
„Ha létezik frissítsd, különben vedd fel”.

## HONNAN ISMEREM FEL?
Egyesítés forrásból célba.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
MERGE INTO <cel> c
USING <forras> f ON (<c.kulcs> = <f.kulcs>)
WHEN MATCHED THEN UPDATE SET c.<oszlop> = f.<oszlop>
WHEN NOT MATCHED THEN INSERT (<oszlopok>) VALUES (<ertekek>);
```

## MIT JELENT SORONKÉNT?
ON feltétel határozza meg az egyezést.

## TIPIKUS HIBA
Több találat az ON-on → hiba.

## HOGYAN ELLENŐRZÖM?
Kis mintán MATCHED és NOT MATCHED ág.

## ZH GYORS EMLÉKEZTETŐ
„Frissíts vagy beszúrj” → MERGE.
