# WHERE

## MI EZ?
Sorok szűrése feltétel alapján.

## MIKOR KELL?
„Csak azok, akik…”, „ahol az ár nagyobb…”

## HONNAN ISMEREM FEL?
Feltétel, szűrés, „csak ha”.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT <oszlopok>
FROM   <tabla>
WHERE  <feltetel>;
```

## MIT JELENT SORONKÉNT?
WHERE a GROUP BY előtt szűri a sorokat (egyesével).

## TIPIKUS HIBA
WHERE-ben aggregátum → tipikus hiba; arra HAVING kell.

## HOGYAN ELLENŐRZÖM?
Ismert mintasorral ellenőrizd, benne van-e / ki van-e zárva.

## ZH GYORS EMLÉKEZTETŐ
Szűrés = WHERE; csoport-szűrés = HAVING.
