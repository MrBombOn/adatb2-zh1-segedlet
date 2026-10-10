# SELECT – áttekintés

**Prioritás: P0** — P0=20 perces ZH kritikus · P1=fontos · P2=háttér

A SELECT **olvas** az adatbázisból. Nem módosít (önmagában).

Útvonal: alap → WHERE → ORDER BY → DISTINCT → alias → DUAL.