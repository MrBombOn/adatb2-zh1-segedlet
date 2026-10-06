# User és séma (Oracle)

Oracle-ben a **user** és a **schema** szorosan összekapcsolódik: a user objektumai alkotják a sémáját.

## Gyakorlati következmény

```sql
SELECT table_name FROM user_tables;
SELECT table_name FROM all_tables WHERE owner = <masik_schema>;
```

Más séma objektuma: `<schema>.<tabla>` — ha van jogod.

## ZH-felismerés

Ha a feladat „a HR sémában…” → más owner táblái; kellhet prefix vagy synonym.
