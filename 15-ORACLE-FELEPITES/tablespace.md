# Tablespace

Logikai tárterület, amelyhez datafile-ok tartoznak.
Táblák / indexek szegmenseket foglalnak tablespace-ben.

```sql
-- Tanulási példa – jogtól függ
SELECT tablespace_name FROM user_tablespaces;
```

## Félreértés
Tablespace ≠ séma. A séma tulajdonos; a tablespace hely.
