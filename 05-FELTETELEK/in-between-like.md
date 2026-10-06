# IN, BETWEEN, LIKE

## MI EZ?
Halmaz, tartomány, mintaillesztés.

## MIKOR KELL?
„Ezek közül”, „közötte”, „így kezdődik”.

## HONNAN ISMEREM FEL?
Lista, intervallum, % és _ jokerek.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
WHERE <oszlop> IN (<e1>, <e2>)
WHERE <oszlop> BETWEEN <a> AND <b>
WHERE <oszlop> LIKE '<minta>'
```

## MIT JELENT SORONKÉNT?
BETWEEN inkluzív. LIKE: % = bármi, _ = egy karakter.

## TIPIKUS HIBA
LIKE nagy/kisbetű: NLS_UPPER/LOWER vagy ILIKE nincs standard Oracle-ben.

## HOGYAN ELLENŐRZÖM?
Próbálj ismert illeszkedő és nem illeszkedő értéket.

## ZH GYORS EMLÉKEZTETŐ
Lista → IN; tartomány → BETWEEN; minta → LIKE.
