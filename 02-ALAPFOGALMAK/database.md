# Adatbázis (database)

## Egyszerű definíció
Adatok rendszerezett tárolója, amelyet adatbázis-kezelő (DBMS) szolgál ki.

## Óvodás magyarázat
Olyan nagy irattár, ahol minden papírnak megvan a fiókja, és van egy könyvtáros (Oracle), aki kiadja / visszateszi.

## Technikai magyarázat
Oracle-ben a „database” fizikai + logikai struktúrák együttese; példány (instance) memóriával és folyamatokkal fér hozzá.

## Mini példa
> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
SELECT * FROM dual; -- élő kapcsolat az adatbázissal
```

## Tipikus félreértés
Az Excel-fájl ≠ teljes Oracle database; a fájl csak egy lehetséges adattárolási forma.

## ZH-felismerés
Ha „melyik adatbázishoz csatlakozol” → kapcsolat (host/service), nem egyetlen tábla.
