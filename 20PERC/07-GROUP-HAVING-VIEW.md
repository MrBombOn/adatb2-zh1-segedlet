# GROUP / HAVING / VIEW

**P0** · operátor a szövegből

| szöveg | op |
|--------|-----|
| kevesebb mint | `<` |
| legfeljebb | `<=` |
| pontosan | `=` |
| legalább | `>=` |
| több mint | `>` |

```sql
SELECT <c>, COUNT(*) AS db
FROM <t>
GROUP BY <c>
HAVING COUNT(*) <operator> <n>;
```

WHERE = sor; HAVING = csoport.

**RÉSZLETESEN:** [`../00-20-PERCES-ZH/07-VIEW-ES-CSOPORTOSITAS/HAVING-COUNT.md`](../00-20-PERCES-ZH/07-VIEW-ES-CSOPORTOSITAS/HAVING-COUNT.md)
