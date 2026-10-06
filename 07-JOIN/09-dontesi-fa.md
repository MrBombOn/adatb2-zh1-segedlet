# JOIN döntési fa

```text
Kell több tábla adata?
├─ Nem → egy táblás SELECT
└─ Igen
   ├─ Csak ahol van pár mindkét oldalon? → INNER JOIN
   ├─ Az egyik oldal összes sora kell, pár nélkül is?
   │  ├─ A „fő” lista a bal tábla → LEFT JOIN
   │  └─ (RIGHT helyett forgasd LEFT-re)
   ├─ Mindkét oldal párosítatlanjai is? → FULL OUTER
   ├─ Minden mindennel? → CROSS (ritka, szándékos)
   └─ Ugyanaz a tábla kétszer? → SELF JOIN
```

## EMBER/KUTYA gyors választó

- Gazdik **kutyáikkal** (csak akinek van) → INNER  
- **Minden** gazdi, kutya nélkül is → LEFT ember→kutya  
- Emberek **kutyával nem rendelkezők** → LEFT + `WHERE kutya.kutya_id IS NULL`
