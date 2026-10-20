# Nincs pár — külön gyorslap

**P0** · 11g

> **Tanulási példa – ne másold be ZH-megoldásként.**

| Szöveg | Eszköz |
|--------|--------|
| X Y nélkül / nincs neki … | LEFT JOIN + `jobb.pk IS NULL` |
| akiknek 0 darab … | LEFT + `HAVING COUNT(jobb.pk)=0` |
| INNER + NOT IN | lehet NULL-csapda — EXISTS/LEFT biztonságosabb |

**NE** `COUNT(*)=0` LEFT után.

→ [`LEFT-JOIN-COUNT-NULL.md`](LEFT-JOIN-COUNT-NULL.md)
## Magyar kulcsmondatok → LEFT JOIN

- azokat is, amelyekhez még nem tartozik semmi
- minden rekord, függetlenül a kapcsolattól
- akkor is mutasd, ha nulla kapcsolódó rekordja van
- kapcsolódó rekord hiányában is

Ékezet nélkül: zokat is amelyekhez meg nem tartozik semmi · uggetlenul a kapcsolattol · 
ulla kapcsolodo · hianyaban is

Ha darabszám is kell: [LEFT-JOIN-COUNT-NULL.md](LEFT-JOIN-COUNT-NULL.md) — COUNT(jobb.pk)=0, **ne** COUNT(*).
