# Séma / USER gyorslap

**20 perc · GYORS** · Részletes: [`01-KORNYEZET/06-schema-user.md`](../01-KORNYEZET/06-schema-user.md)

## Magyar szinonimák
user / felhasználó / séma / jog / kvóta / tablespace / „tudjon csatlakozni”

## Alapelv
Oracle-ben **USER ≈ SCHEMA**: a user objektumai a sémája.

## Kitöltendő minták
> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

```sql
CREATE USER <user_nev> IDENTIFIED BY <jelszo>;

ALTER USER <user_nev> QUOTA <meret> ON <tablespace_nev>;
-- pl. QUOTA UNLIMITED ON USERS  (ha a környezet engedi)

GRANT CREATE SESSION TO <user_nev>;
GRANT CREATE TABLE TO <user_nev>;
GRANT CREATE VIEW TO <user_nev>;
-- további jogok a feladat szerint
```

## PL/SQL Developer lépések
1. Privileged userrel (pl. rendszeruser a lab szerint) futtasd a CREATE USER / GRANT utasításokat  
2. Új kapcsolat: Username=`<user_nev>`  
3. `SELECT user FROM dual;`  
4. Próbálj `CREATE TABLE` — ha ORA-01950 → kvóta; ORA-01031 → jog

## ORA gyors
| Kód | Jelentés | Mit adj |
|-----|----------|---------|
| ORA-01950 | no privileges on tablespace | QUOTA |
| ORA-01031 | insufficient privileges | GRANT megfelelő jog |
| ORA-01017 | bad username/password | credential |
