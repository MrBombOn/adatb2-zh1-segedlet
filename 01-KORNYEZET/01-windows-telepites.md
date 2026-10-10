# Windows telepítés – Oracle 11g

**Prioritás: P0**

> Tanulási útmutató – a pontos telepítőnevek változnak. Oracle **11g XE** / intézményi 11g szerver.

## Komponensek

1. Oracle Database **11g XE** (vagy intézményi 11g — akkor DB telepítés nem kell)
2. Oracle **Instant Client 64-bit**
3. **PL/SQL Developer 64-bit** (kliens)

## Ellenőrzés

```sql
SELECT * FROM dual;
SELECT banner FROM v$version;  -- jogtól függhet
```

Séma: `07-gyakorlo-schema.md`. Jogok: `00-20-PERCES-ZH/03-SEMA-USER.md`.

## Gyakori buktató

- 32/64-bit keverés (Instant Client ↔ PL/SQL Developer)
- Rossz szolgáltatásnév / port
- Listener nem fut
- Felhasználó zárolva

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.
