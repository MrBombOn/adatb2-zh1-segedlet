# Keresősegéd (Oracle 11g)

**P1** · Minden témánál van KERESÉS blokk; itt a közös szabály.

## Szabály

1. Első: `site:docs.oracle.com Oracle 11g …`
2. Második: SO `Oracle 11g … -mysql -postgresql -sql-server`
3. Kerüld: FETCH FIRST, OFFSET ROWS, IDENTITY mint megoldás
4. Kliens: PL/SQL Developer tippek OK, de dialektus = 11g SQL

## Gyors sablon

```text
site:docs.oracle.com Oracle Database 11g R2 SQL Language Reference <téma>
```

```text
"Oracle 11g" <téma> ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```

## HOL TOVÁBB

- Feladatszöveg → [`../00-START/FELADATSZOVEG-INDEX.md`](../00-START/FELADATSZOVEG-INDEX.md)
- Meglepetés → [`../22-MEGLEPETES-FELADAT/`](../22-MEGLEPETES-FELADAT/)

## ORACLE 11g VALIDÁCIÓ

| Kérdés | Válasz |
|--------|--------|
| Van FETCH FIRST / OFFSET ROWS / LIMIT a megoldásban? | **NO** (csak TILOS figyelmeztetésben OK) |
| Van IDENTITY / AUTO_INCREMENT? | **NO** → SEQUENCE |
| Top-N ROWNUM / ROW_NUMBER? | **YES** ha kell Top-N |
| Placeholder kitöltve a feladatsor neveivel? | **YES** kell |
| USER ≈ SCHEMA tudatos? | **YES** (nincs vak CREATE SCHEMA) |
