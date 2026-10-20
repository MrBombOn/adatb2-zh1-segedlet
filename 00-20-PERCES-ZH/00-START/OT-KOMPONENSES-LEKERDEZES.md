# 5 komponenses lekérdezés — integrált önálló quick

**P0** · 11g · 1 katt = teljes SQL-váz · LEFT+COUNT+GROUP+WHERE/LIKE+HAVING

## 5 MÁSODPERCES FELISMERÉS

Ha a szöveg egyszerre kéri: együtt listázás **akkor is ha nincs pár** + darabszám + szűrés szövegre + darabszám-küszöb.

LEFT kulcsszavak: *azokat is, amelyekhez még nem tartozik semmi* · *függetlenül a kapcsolattól* · *nulla kapcsolódó* · *hiányában is*.

## Teljes kitölthető SQL

```sql
SELECT <bal>.<pk>,
       <bal>.<nev>,
       COUNT(<jobb>.<pk>) AS db
FROM   <bal>
LEFT JOIN <jobb> ON <jobb>.<fk> = <bal>.<pk>
WHERE  UPPER(<bal>.<szoveg>) LIKE UPPER('%<minta>%')
GROUP BY <bal>.<pk>, <bal>.<nev>
HAVING COUNT(<jobb>.<pk>) <operator> <n>;
```

## HAVING operátor — válaszd a feladatszövegből (ne fix `>=`)

| Feladatszöveg | Operátor | Példa |
|---------------|----------|-------|
| kevesebb mint N | `<` | `HAVING COUNT(<jobb>.<pk>) < <n>` |
| legfeljebb N | `<=` | `HAVING COUNT(<jobb>.<pk>) <= <n>` |
| pontosan N | `=` | `HAVING COUNT(<jobb>.<pk>) = <n>` |
| legalább N | `>=` | `HAVING COUNT(<jobb>.<pk>) >= <n>` |
| több mint N | `>` | `HAVING COUNT(<jobb>.<pk>) > <n>` |
| nulla kapcsolódó / nincs pár | `= 0` | `HAVING COUNT(<jobb>.<pk>) = 0` |

> **Ne** írd mindig `>=`-t. Olvasd el a küszöb szavát, és cseréld az `<operator>` helyét.

## Placeholder — MIT ÍRJ / HONNAN VESZEM

| Helyőrző | MIT ÍRJ | HONNAN VESZEM |
|----------|---------|---------------|
| `<bal>` / `<jobb>` | Táblanevek | **feladat** |
| `<pk>` / `<fk>` | Kapcsoló kulcsok | **feladat** / séma |
| `<szoveg>` / `<minta>` | Szűrő oszlop + minta | **feladat** |
| `<n>` | Küszöb darab | **feladat** |
| `<operator>` | `<` `<=` `=` `>=` `>` | **feladat** (tábla fent) |
| `COUNT(<jobb>.<pk>)` | Jobb kulcs, nem `*` | **szabály** |

**CSAPDA:** `COUNT(*)`. Canonical ha elakadsz: [`../08-JOIN-ES-KAPCSOLAT/README.md`](../08-JOIN-ES-KAPCSOLAT/README.md)

→ [`FELADAT-KOMPONENSEKRE-BONTASA.md`](FELADAT-KOMPONENSEKRE-BONTASA.md)
