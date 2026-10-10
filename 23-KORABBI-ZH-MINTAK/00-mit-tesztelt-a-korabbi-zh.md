# Mit szokott tesztelni egy korábbi jellegű ZH? (mintafelismerés)

**Prioritás: P0**

> **NEM** szó szerinti feladatsor. **NEM** kész megoldás.  
> Nincs TERMEK/KATEGORIA (vagy bármely konkrét régi ZH) kidolgozott válasza.  
> Cél: felismerni a **típust**, és a `00-20-PERCES-ZH/` megfelelő lapjára ugrani.

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

## 8 feladattípus – felismerés

| # | Típus (általános) | Szövegjelek | Merre menj |
|---|-------------------|-------------|------------|
| 1 | User / séma / jog | hozz létre usert, adj jogot, kvóta | `03-SEMA-USER` |
| 2 | Tábla + constraint | CREATE TABLE, PK, FK, CHECK | `04` + `05` |
| 3 | Tömeges adat | több rekord, egyszerre | `06-INSERT ALL` |
| 4 | Üres másolat | struktúra adat nélkül | `07-CTAS` |
| 5 | Feltételes szétválogatás | dátum szerint más táblába | `09` |
| 6 | MERGE / upsert | ha még nincs / ha van | `08` |
| 7 | Nézet + aggregálás | VIEW, GROUP, lista | `10` |
| 8 | Lekérdezés / JOIN / Top-N | listázd, pár nélkül, leg… | `11`–`13` |

## Hogyan gyakorolj rájuk
1. Fogalmazz **saját** mini-feladatot a fenti típusokra (STUDENT/AUTHOR világban).  
2. Oldd meg placeholder mintákkal.  
3. Nézd a `20-GYAKORLAS/PROBA-ZH/` csomagokat.

## Amit tilos
- Régi feladatsor szó szerinti bemásolása  
- „Megoldásbank” készítése kurzusobjektumokra
