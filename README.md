# Adatbázisok 2 – Oracle / SQL ZH1 segédlet

Saját tanulási és **szintaktikai** segédlet kezdőknek. Oracle SQL fókusz.
Nem megoldásbank: a példák placeholder sablonok és tanulási mini-példák.

**Repo:** https://github.com/MrBombOn/adatb2-zh1-segedlet

---

## ZH szabályok (olvasd el először)

1. **Saját munka.** A ZH alatt csak azt írd, amit magad értessz.
2. **Ne másold be** a repo példáit megoldásként. A sablonokban `<helyőrző>` van szándékosan.
3. **Tanulási példa** jelzésű blokkokat ne vidd be a ZH-ra kész válaszba.
4. **Oracle szintaxis.** Ne MySQL/Postgres dialektust használj (pl. `LIMIT` helyett `FETCH FIRST` / `ROWNUM`).
5. **NULL** nem egyenlő semmivel: `IS NULL` / `IS NOT NULL`, ne `= NULL`.
6. **DML után** gondolj tranzakcióra: `COMMIT` / `ROLLBACK` (ha a feladat kéri / a környezet elvárja).
7. **JOIN előtt** azonosítsd a kapcsoló kulcsot (FK → PK).
8. **GROUP BY:** minden nem aggregált SELECT-oszlop szerepeljen a GROUP BY-ban.
9. **Constraint** hiba ≠ „rossz SELECT”: olvasd az ORA-üzenetet.
10. **Időkorlát:** előbb a biztos pontokat (SELECT + WHERE), aztán JOIN/GROUP BY.
11. **Névadás:** a ZH-n a megadott tábla-/oszlopneveket használd, ne a gyakorló STUDENT/COURSE-t.
12. **Teszteld fejben:** hány sort vársz? Van-e duplikátum? Mi van NULL-lal?

Részletek: [`22-ZH/`](22-ZH/) · Gyorssegély: [`19-GYORSSEGELY/`](19-GYORSSEGELY/)

---

## Hol kezdjem?

1. [`00-START-HERE/`](00-START-HERE/) — mi ez, hogyan olvasd, tanulási terv  
2. [`01-KORNYEZET/`](01-KORNYEZET/) — Windows / Docker / WSL2 telepítés  
3. [`02-ALAPFOGALMAK/`](02-ALAPFOGALMAK/) → [`04-SELECT/`](04-SELECT/) → [`07-JOIN/`](07-JOIN/)  
4. Gyakorlás: [`20-GYAKORLAS/`](20-GYAKORLAS/) (előbb magad, aztán `MEGOLDASOK/`)

## Mappaáttekintés

| Mappa | Tartalom |
|-------|----------|
| `00-START-HERE/` | Bevezető, ZH szabályok, útvonal |
| `01-KORNYEZET/` | Telepítés, csatlakozás, gyakorló séma |
| `02-ALAPFOGALMAK/` | Database…stored procedure fogalmak |
| `03-ADATTIPUSOK/` | VARCHAR2, NUMBER, DATE, NULL |
| `04-SELECT/` … `14-JOGOSULTSAGOK/` | SQL témakörök |
| `15-ORACLE-FELEPITES/` | Instance, tablespace, dictionary |
| `16-SZINTAKTIKAI-SABLONOK/` | Másolható (tanulási) sablonok |
| `17-FELADAT-FELISMERES/` | Melyik SQL kell a szöveghez? |
| `18-HIBAK/` | ORA hibák, logikai hibák |
| `19-GYORSSEGELY/` | Cheatsheet, checklist |
| `20-GYAKORLAS/` | Feladatok + tanulási megoldások |
| `21-FOGALOMTAR/` | ABC fogalomtár |
| `22-ZH/` | Stratégia, mit ne csinálj |

## Gyors példa (placeholder)

```sql
SELECT <oszlopok>
FROM   <tabla>
WHERE  <feltetel>;
```

## Licenc

MIT – saját tartalomra. Lásd `LICENSE` és `REFERENCES.md`.
