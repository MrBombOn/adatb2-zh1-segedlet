# GROUP BY vs PARTITION BY

**P1 · GYORS** · 11g

| | GROUP BY | PARTITION BY (OVER) |
|--|----------|---------------------|
| Sorok | összeolvadnak | megmaradnak |
| Hol | aggregáló lekérdezés | analitikus |
| Tipikus szöveg | „csoportonként hány / összeg” | „minden sor mellett a csoport összege / rang” |

Ha a feladat **minden sort** akar + mellé összesítőt → OVER.  
Ha **egy sor / csoport** → GROUP BY.

→ [`README.md`](README.md)
