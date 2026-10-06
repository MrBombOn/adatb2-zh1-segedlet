# RIGHT JOIN

## MI EZ?
Jobb tábla minden sora + bal egyezés vagy NULL.

## MIKOR KELL?
Ritkábban írjuk; gyakran LEFT-re forgatjuk.

## HONNAN ISMEREM FEL?
Jobb oldal a „minden”.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT <oszlopok>
FROM   <bal> <b>
RIGHT JOIN <jobb> <j> ON <j>.<fk> = <b>.<pk>;
```

## MIT JELENT SORONKÉNT?
Szimmetrikus a LEFT-hez, fordított oldallal.

## TIPIKUS HIBA
Keveredés LEFT/RIGHT között.

## HOGYAN ELLENŐRZÖM?
Írd át LEFT-re fejben ellenőrzéshez.

## ZH GYORS EMLÉKEZTETŐ
Ha RIGHT zavaró: cseréld a táblák sorrendjét + LEFT.
