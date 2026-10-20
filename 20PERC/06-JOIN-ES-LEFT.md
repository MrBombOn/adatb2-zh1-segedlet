# JOIN / LEFT / nincs pár

**P0** · COUNT(*) csapda

Kulcsszavak: *azokat is… semmi* · *függetlenül a kapcsolattól* · *nulla kapcsolódó* · *hiányában is*

```sql
SELECT <bal>.*
FROM <bal>
LEFT JOIN <jobb> ON <jobb>.<fk> = <bal>.<pk>
WHERE <jobb>.<pk> IS NULL;

SELECT <bal>.<pk>, COUNT(<jobb>.<pk>) AS db
FROM <bal>
LEFT JOIN <jobb> ON <jobb>.<fk> = <bal>.<pk>
GROUP BY <bal>.<pk>
HAVING COUNT(<jobb>.<pk>) = 0;
```

**RÉSZLETESEN:** [`../00-20-PERCES-ZH/08-JOIN-ES-KAPCSOLAT/LEFT-JOIN-COUNT-NULL.md`](../00-20-PERCES-ZH/08-JOIN-ES-KAPCSOLAT/LEFT-JOIN-COUNT-NULL.md)
