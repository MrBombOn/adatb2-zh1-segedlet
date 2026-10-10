# Környezet – áttekintés

**Prioritás: P0** (csatlakozás nélkül nincs gyakorlás)

Oracle **11g / 11g R2** tanuláshoz tipikus út:

1. **Windows** – Oracle 11g XE + Instant Client 64-bit + **PL/SQL Developer** 64-bit  
2. **Docker Desktop** – 11g XE image konténerben  
3. **WSL2** – Linux + Docker, kliens Windowson (PL/SQL Developer → localhost port)

Cél: `SELECT * FROM dual;` fusson, és legyen saját gyakorló sémád.

| Fájl | Tartalom |
|------|----------|
| `01-windows-telepites.md` | Windows + 11g XE |
| `02-docker.md` | Docker |
| `03-wsl2.md` | WSL2 |
| `04-plsql-developer.md` | PL/SQL Developer |
| `05-csatlakozas.md` | Kapcsolat checklist |
| `06-schema-user.md` | User / séma |
| `07-gyakorlo-schema.md` | Gyakorló táblák |
| `08-hibaelharias.md` | Környezeti hibák |

> Megjegyzés: a régi `04-sqldeveloper-sqlcl.md` helyett használd a `04-plsql-developer.md` fájlt.
