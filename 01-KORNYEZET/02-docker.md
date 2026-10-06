# Docker útvonal

## Előfeltétel

- Docker Desktop (Windows) fut
- Elég RAM a konténernek (Oracle image igényes)

## Általános lépések (helyőrző)

```text
docker pull <oracle-image>
docker run --name <kontener> -p <host-port>:1521 -e <env-valtozok> <oracle-image>
```

> **Tanulási példa – ne másold be ZH-megoldásként.** Az image név, jelszó és port a te környezetedé.

## Csatlakozás

Host: `localhost`, port: amit `-p`-nél megadtál, service/SID: az image dokumentációja szerint.

```sql
SELECT banner FROM v$version;
```

(Jogosultságtól függően `v$version` nem mindig elérhető gyakorló usernek — `dual` elég smoke testnek.)
