# VARCHAR2 és CHAR

## MI EZ?
Szöveges adattípusok.

## MIKOR KELL?
Név, email, kód tárolásakor.

## HONNAN ISMEREM FEL?
CREATE TABLE-ben szövegoszlop; összehasonlítás / LIKE.

## ALAP SZINTAXIS
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
CREATE TABLE <tabla> (
  <szoveg_oszlop> VARCHAR2(<max_hossz>),
  <fix_oszlop>   CHAR(<hossz>)
);
```

## MIT JELENT SORONKÉNT?
- VARCHAR2(n): max n byte/char (beállítástól függően)
- CHAR(n): mindig n hosszúra paddingelhet

## TIPIKUS HIBA
VARCHAR2 túl rövid → ORA-12899. CHAR és VARCHAR2 keverése szóközös meglepetéseket okozhat.

## HOGYAN ELLENŐRZÖM?
DESC <tabla>; vagy data dictionary nézetek.

## ZH GYORS EMLÉKEZTETŐ
Általában VARCHAR2; CHAR csak ha tényleg fix szélesség kell.
