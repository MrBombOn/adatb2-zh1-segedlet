# INSERT – több rekord egyszerre

**20 perc · GYORS réteg** · Részletes: [`09-DML/insert.md`](../09-DML/insert.md)

## Magyar szinonimák (feladatszöveg)
vegyél fel több sort / egyszerre / tömeges beszúrás

## MI KELL? (1 mondat)
Oracle 11g: `INSERT ALL` … `SELECT … FROM dual`.

## Kitöltendő szintaktikai minta
> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
INSERT ALL
  INTO <tabla> (<o1>, <o2>) VALUES (<e1a>, <e2a>)
  INTO <tabla> (<o1>, <o2>) VALUES (<e1b>, <e2b>)
  INTO <tabla> (<o1>, <o2>) VALUES (<e1c>, <e2c>)
  INTO <tabla> (<o1>, <o2>) VALUES (<e1d>, <e2d>)
  INTO <tabla> (<o1>, <o2>) VALUES (<e1e>, <e2e>)
SELECT 1 FROM dual;
```

## TIPIKUS HIBA
MySQL-es multi-VALUES reflex; FK sértés; elírt oszlopszám.

## ELLENŐRZÉS (10 mp)
SELECT COUNT(*) WHERE …; öt sor megvan-e?
