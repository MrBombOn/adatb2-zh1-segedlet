# Környezeti hibaelhárítás

| Tünet | Lehetséges ok | Mit nézz |
|-------|---------------|----------|
| Nem csatlakozik | Listener / konténer leállt | szolgáltatás, `docker ps` |
| ORA-01017 | rossz user/jelszó | credential |
| ORA-12154 | TNS / service név | kapcsolatleíró |
| ORA-12541 | nincs listener | port, listener |
| ORA-00942 | nincs tábla / nincs jog | séma, GRANT |
| Lassú első start | Oracle image épp inicializál | log, várj |

Részletes SQL hibák: `18-HIBAK/`.
