# NUMBER

## MI EZ?
Numerikus típus tetszőleges pontossággal (határokon belül).

## MIKOR KELL?
Ár, kredit, darabszám.

## HONNAN ISMEREM FEL?
NUMBER vagy NUMBER(p,s).

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
<oszlop> NUMBER
<oszlop> NUMBER(<precision>, <scale>)
```

## MIT JELENT SORONKÉNT?
- precision: jelentős számjegyek
- scale: tizedes jegyek

## TIPIKUS HIBA
Stringet számhoz hasonlítasz idézőjel nélkül / rosszul → implicit konverzió bajok.

## HOGYAN ELLENŐRZÖM?
WHERE <szam_oszlop> BETWEEN <a> AND <b>;

## ZH GYORS EMLÉKEZTETŐ
Pénznél gondold meg a scale-t; ID-hez gyakran egész NUMBER.
