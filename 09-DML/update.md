# UPDATE

## MI EZ?
Meglévő sorok módosítása.

## MIKOR KELL?
„Állítsd át”, „növeld”.

## HONNAN ISMEREM FEL?
Módosítás feltétellel.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
UPDATE <tabla>
SET    <oszlop> = <ertek>
WHERE  <feltetel>;
```

## MIT JELENT SORONKÉNT?
**WHERE kötelezően átgondolt** — nélküle az egész tábla.

## TIPIKUS HIBA
Elfelejtett WHERE.

## HOGYAN ELLENŐRZÖM?
Előtte: SELECT ugyanazzal a WHERE-rel.

## ZH GYORS EMLÉKEZTETŐ
Először SELECT, aztán UPDATE.
