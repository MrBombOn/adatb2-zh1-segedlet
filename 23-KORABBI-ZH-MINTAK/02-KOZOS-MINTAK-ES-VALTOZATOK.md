# Közös minták és változatok (eredeti + pót)

**P1** · NEM megoldás · közös metszet

| Közös mag | Eredeti ZH jelleg | Pót jelleg | Változat figyelmeztetés |
|-----------|-------------------|------------|-------------------------|
| USER / GRANT | CREATE USER | + DROP CASCADE | nincs IF EXISTS |
| CONSTRAINT | PK/FK | + LENGTH CHECK | named CK |
| INSERT | INSERT ALL 1 tábla | + több tábla | FK sorrend |
| Dátum | TO_DATE | + TRUNC(SYSDATE) | időcsapda |
| DML | egyszerű UPDATE | + % és EXISTS | WHERE kötelező gyakorlat |
| JOIN | INNER/LEFT IS NULL | + COUNT(right)=0 | COUNT(*) csapda |
| GROUP | HAVING COUNT | ugyanaz + 5 komponens | WHERE vs HAVING |
| Analitikus | ritkább / Top-N | OVER / PARTITION hangsúly | ≠ GROUP BY |
| LIKE | LIKE | UPPER/LOWER LIKE | mindkét oldal |

Meglepetés: ha a szöveg **egyik listában sincs** → [`../00-20-PERCES-ZH/22-MEGLEPETES-FELADAT/DONTESI-MATRIX.md`](../00-20-PERCES-ZH/22-MEGLEPETES-FELADAT/DONTESI-MATRIX.md).

→ [`00-mit-tesztelt-a-korabbi-zh.md`](00-mit-tesztelt-a-korabbi-zh.md) · [`01-pot-zh-mit-tesztelt.md`](01-pot-zh-mit-tesztelt.md)
