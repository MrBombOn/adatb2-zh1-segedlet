# PL/SQL Developer (kliens)

**Oracle 11g** gyakorláshoz a javasolt GUI kliens: **PL/SQL Developer** (64-bit).

> A korábbi „SQL Developer / SQLcl” utalások helyett ebben a repóban **PL/SQL Developer** a fő út.

## Telepítés (vázlat)

1. Oracle Instant Client **64-bit** (a PL/SQL Developer bitességével egyezzen)
2. PL/SQL Developer **64-bit**
3. Oracle 11g XE fut (natív / Docker / WSL2) **vagy** intézményi szerver

## Új kapcsolat

1. File → New → Command Window / SQL Window  
2. Logon: Username, Password, Database (TNS alias **vagy** `host:port/service` a környezeted szerint)  
3. Teszt:

```sql
SELECT * FROM dual;
SELECT user FROM dual;
```

## Gyakorló checklist

- [ ] Csatlakozás sikerül  
- [ ] `user_tables` listázható  
- [ ] Saját séma / jogosultság rendben (lásd `00-20-PERCES-ZH/03-SEMA-USER.md`)

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.
