# Csatlakozás ellenőrzőlista

1. Listener / konténer fut?  
2. Host, port, service name helyes?  
3. User/jelszó helyes? Nincs lock?  
4. `SELECT * FROM dual;` sikerül?  
5. `SELECT table_name FROM user_tables;` — látod a saját tábláidat?

## Kapcsolati helyőrző

```text
User:     <user>
Password: <password>
Host:     <host>
Port:     <port>
Service:  <service_name>
```

**Ne commitolj jelszót** ebbe a repóba. Használj lokális jegyzetet / jelszókezelőt.
