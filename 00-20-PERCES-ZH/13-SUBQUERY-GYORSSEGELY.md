# Subquery gyorssegély

**20 perc · GYORS réteg** · Részletes: [`04-SELECT/`](../04-SELECT/) + gyakorlás

## Magyar szinonimák (feladatszöveg)
azok akik / nagyobb mint az átlag / létezik olyan / nincs olyan

## MI KELL? (1 mondat)
SELECT a WHERE/FROM/SELECT listában másik SELECT-tel.

## Kitöltendő szintaktikai minta
> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
SELECT <oszlopok>
FROM   <tabla> t
WHERE  t.<szam> > (SELECT AVG(<szam>) FROM <tabla>)
   OR  t.<id> IN (SELECT <id> FROM <masik> WHERE <feltetel>)
   OR  EXISTS (SELECT 1 FROM <masik> m WHERE m.<fk> = t.<pk>);
```

## TIPIKUS HIBA
Több sort adó subquery `=` mellett; korreláció elrontása.

## ELLENŐRZÉS (10 mp)
Futtasd külön a belső SELECT-et.
