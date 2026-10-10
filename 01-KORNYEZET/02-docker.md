# Docker útvonal – Oracle 11g

**Prioritás: P1**

## Előfeltétel

- Docker Desktop fut
- Elég RAM a 11g XE image-hez

## Általános lépések (helyőrző)

```text
docker pull <oracle-11g-xe-image>
docker run --name <kontener> -p <host-port>:1521 -e <env-valtozok> <oracle-11g-xe-image>
```

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

## Csatlakozás PL/SQL Developerrel

Host: `localhost`, port: a `-p` mapping, service/SID: az image docs szerint (gyakran `XE`).

```sql
SELECT * FROM dual;
```
