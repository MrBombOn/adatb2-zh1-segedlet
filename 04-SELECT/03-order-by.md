# ORDER BY

## MI EZ?
Eredmény rendezése.

## MIKOR KELL?
„Növekvő / csökkenő sorrendben”, „abc szerint”.

## HONNAN ISMEREM FEL?
Rendezés, sorba, ABC, legdrágább.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT <oszlopok>
FROM   <tabla>
ORDER BY <kifejezes> [ASC|DESC];
```

## MIT JELENT SORONKÉNT?
ASC default; több oszlop: vesszővel.

## TIPIKUS HIBA
Alias ORDER BY-ban megengedett lehet; WHERE-ben nem.

## HOGYAN ELLENŐRZÖM?
Nézd az első és utolsó sort.

## ZH GYORS EMLÉKEZTETŐ
Rendezés ≠ szűrés.
