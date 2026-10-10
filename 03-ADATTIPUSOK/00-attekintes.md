# Adattípusok – áttekintés

**Prioritás: P0** — P0=20 perces ZH kritikus · P1=fontos · P2=háttér

Oracle gyakori skalár típusok tanuláshoz:

| Típus | Mire |
|-------|------|
| VARCHAR2(n) | változó hosszú szöveg |
| CHAR(n) | rögzített hosszú szöveg (ritkábban kell) |
| NUMBER | szám (egész / tört) |
| DATE | dátum + idő (másodpercig) |
| TIMESTAMP | finomabb időbélyeg |

NULL minden típusnál megjelenhet (ha nincs NOT NULL).

Következő fájlok: részletek + konverziók.