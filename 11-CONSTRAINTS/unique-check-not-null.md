# UNIQUE, CHECK, NOT NULL

## MI EZ?
Egyediség; feltételes szabály; kötelező kitöltés.

## MIKOR KELL?
Egyedi email; pozitív kredit; kötelező név.

## HONNAN ISMEREM FEL?
UNIQUE / CHECK / NOT NULL kulcsszavak.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
<oszlop> NOT NULL
CONSTRAINT <nev> UNIQUE (<oszlop>)
CONSTRAINT <nev> CHECK (<feltetel>)
```

## MIT JELENT SORONKÉNT?
UNIQUE engedi a NULL-t (Oracle-ben több NULL-t is — tanuld a tárgy szerinti elvárást).

## TIPIKUS HIBA
CHECK túl bonyolult üzleti szabállyal.

## HOGYAN ELLENŐRZÖM?
Sértő INSERT → várt ORA hiba.

## ZH GYORS EMLÉKEZTETŐ
„Egyedi” → UNIQUE; „legyen igaz rá” → CHECK; „kötelező” → NOT NULL.
