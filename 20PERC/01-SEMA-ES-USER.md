# Séma / USER / DROP

**P0** · 11g · **nincs IF EXISTS** · USERS tablespace **nem kötelező** (KÖRNYEZETFÜGGŐ)

## HA EZT LÁTOD
hozz létre usert · ha már létezik töröld · kvóta · jogok

## ÍRD EZT
```sql
SELECT username FROM all_users WHERE username = UPPER('<user_nev>');
DROP USER <user_nev> CASCADE;  -- csak ha létezik
CREATE USER <user_nev> IDENTIFIED BY <jelszo>;
ALTER USER <user_nev> QUOTA <meret> ON <tablespace_nev>;
GRANT CREATE SESSION, CREATE TABLE TO <user_nev>;
```

**RÉSZLETESEN:** [`../00-20-PERCES-ZH/01-SEMA-USER/DROP-USER.md`](../00-20-PERCES-ZH/01-SEMA-USER/DROP-USER.md) · [`../00-20-PERCES-ZH/01-SEMA-USER/README.md`](../00-20-PERCES-ZH/01-SEMA-USER/README.md)
