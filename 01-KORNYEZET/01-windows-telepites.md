# Windows telepítés (vázlat)

> Tanulási útmutató – a pontos telepítőnevek és verziók változnak. Mindig a hivatalos Oracle oldal aktuális leírását kövesd.

## Tipikus komponensek

1. Oracle Database Free / XE (vagy intézményi szerver — akkor telepítés nem kell)
2. Oracle SQL Developer **vagy** SQLcl
3. (Opcionális) Instant Client, ha külön kliens kell

## Ellenőrzés telepítés után

```sql
SELECT * FROM dual;
SELECT user FROM dual;
```

Ha ez fut, a magod kész. A séma feltöltése: `07-gyakorlo-schema.md`.

## Gyakori buktató

- Rossz szolgáltatásnév / port a kapcsolatban
- Listener nem fut
- Felhasználó zárolva (`ACCOUNT LOCK`)
