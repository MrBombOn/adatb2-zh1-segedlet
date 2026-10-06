# FOREIGN KEY constraint

## MI EZ?
Hivatkozási épség másik táblára.

## MIKOR KELL?
„Hivatkozzon a … táblára”.

## HONNAN ISMEREM FEL?
Kapcsolat két tábla között.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
CONSTRAINT <nev> FOREIGN KEY (<oszlop>)
  REFERENCES <szulo>(<oszlop>)
```

## MIT JELENT SORONKÉNT?
Gyerek értékének léteznie kell a szülőben (vagy NULL, ha engedi).

## TIPIKUS HIBA
Szülő törlése gyerekek mellett → ORA-02292.

## HOGYAN ELLENŐRZÖM?
Próbálj érvénytelen FK INSERT-et — el kell hasalnia.

## ZH GYORS EMLÉKEZTETŐ
Kapcsolat kényszerítése → FK.
