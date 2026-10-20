# DROP USER — önálló quick

**P0** · 11g · **nincs IF EXISTS**

## 5 MÁSODPERCES FELISMERÉS

„Ha a user **már létezik**, töröld” → `DROP USER … CASCADE` majd CREATE.

## Teljes SQL

```sql
DROP USER <user_nev> CASCADE;

CREATE USER <user_nev> IDENTIFIED BY <jelszo>;
ALTER USER <user_nev> QUOTA <meret> ON <tablespace_nev>;  -- ha kell
GRANT CREATE SESSION, CREATE TABLE TO <user_nev>;
```

## Placeholder — MIT ÍRJ / HONNAN VESZEM

| Helyőrző | MIT ÍRJ | HONNAN VESZEM |
|----------|---------|---------------|
| `<user_nev>` / `<jelszo>` | User + jelszó | **feladat** |
| `<tablespace_nev>` | Gyakran USERS | **környezet** — ne vak kötelező |
| `CASCADE` | Objektumokkal együtt | **tipikus** ha séma nem üres |
| `IF EXISTS` | — | **TILOS** 11g-n |

Canonical: [`README.md`](README.md)
