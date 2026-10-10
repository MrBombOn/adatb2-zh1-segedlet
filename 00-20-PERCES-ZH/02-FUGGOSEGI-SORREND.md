# Függőségi sorrend

**20 perc · GYORS**

## ASCII lánc (általános ZH)

```text
[USER / SCHEMA / QUOTA / GRANT]
            |
            v
    [CREATE TABLE szulo] -- PK
            |
            v
    [CREATE TABLE gyerek] -- FK → szulo
            |
            v
    [SEQUENCE] (ha kell ID)
            |
            v
    [INSERT szulo]  -->  [INSERT gyerek]
            |
            v
    [VIEW / MERGE / UPDATE]
            |
            v
    [SELECT / JOIN / GROUP BY / Top-N]
            |
            v
    [COMMIT] (ha a feladat / környezet kéri)
```

## Szabály

1. Amit más hivatkozik, **előbb** létezzen (szülő tábla, user, jog).  
2. FK-s INSERT előtt legyen szülő sor.  
3. VIEW a SELECT-képes táblák után.  
4. Lekérdezés legvégén — de ha elakadsz, előbb `SELECT` teszt kis lépésekben.

## Gyors ellenőrző

- [ ] User/jog kész?  
- [ ] Szülő tábla + PK?  
- [ ] Gyerek + FK?  
- [ ] Adat szülő→gyerek?  
- [ ] Lekérdezés?
