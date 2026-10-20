# INSERT ALL több táblába — önálló quick

**P0** · 11g

## 5 MÁSODPERCES FELISMERÉS

„Vegyél fel **több különböző táblába** egyszerre” (nem csak 5 sor egy táblába).

## Teljes SQL

```sql
INSERT ALL
  INTO <tabla1> (<o1>, <o2>) VALUES (<e1a>, <e2a>)
  INTO <tabla2> (<p1>, <p2>) VALUES (<f1a>, <f2a>)
  INTO <tabla1> (<o1>, <o2>) VALUES (<e1b>, <e2b>)
SELECT 1 FROM dual;
```

## Placeholder — MIT ÍRJ / HONNAN VESZEM

| Helyőrző | MIT ÍRJ | HONNAN VESZEM |
|----------|---------|---------------|
| `<tabla1/2>` | Céltáblák | **feladat** |
| oszlopok/értékek | Literálok / seq | **feladat** |
| FK sorrend | Szülő előbb ha kell | **szabály**/docs — biztosabb külön INSERT szülőre |

Canonical: [`README.md`](README.md)
