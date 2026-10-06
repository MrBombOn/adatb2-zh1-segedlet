# SQL Developer és SQLcl

## SQL Developer (GUI)

- Új kapcsolat: user, jelszó, host, port, service name / SID  
- Worksheet: SQL futtatás  
- Explain plan / leírás: tanuláshoz hasznos  

## SQLcl / SQL*Plus (CLI)

```text
sql <user>/<password>@<host>:<port>/<service>
```

```sql
SELECT * FROM dual;
EXIT;
```

## Melyiket?

| Szituáció | Ajánlás |
|-----------|---------|
| Böngészés, kattintás | SQL Developer |
| Gyors script, ZH-szerű fegyelem | SQLcl |
| Automatizálás | SQLcl + fájl |
