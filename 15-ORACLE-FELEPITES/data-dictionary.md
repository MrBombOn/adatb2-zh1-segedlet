# Data dictionary

| Prefix | Mit látsz |
|--------|-----------|
| USER_ | amit birtokolsz |
| ALL_ | amihez van jogod |
| DBA_ | mind (DBA jog kell) |

```sql
SELECT table_name FROM user_tables;
SELECT constraint_name, constraint_type FROM user_constraints;
```

## ZH-felismerés
„Listázd a saját tábláidat / constraintjeidet” → USER_ nézetek.
