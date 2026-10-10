# Végső ellenőrzés (beadás előtt)

- [ ] Oracle **11g** szintaxis: nincs LIMIT / FETCH FIRST / IDENTITY  
- [ ] Minden `<helyőrző>` ki van töltve a **feladat neveivel**  
- [ ] Függőségi sorrend: user → szülő → gyerek → adat → SELECT  
- [ ] FK INSERT: szülő sor létezik  
- [ ] GROUP BY teljes  
- [ ] NULL: IS NULL / NVL ahol kell  
- [ ] Dátum: TO_DATE maszk  
- [ ] Top-N: ROWNUM alkérdéses mintában  
- [ ] LEFT JOIN „nincs pár” ágnál IS NULL  
- [ ] COMMIT csak ha kell  
- [ ] Elolvastad az ORA üzenetet, ha volt hiba

## KERESÉS, HA ELAKADTAM

> **Figyelem:** Kerüld a MySQL / Postgres / SQL Server találatokat és a **12c+** megoldásokat (`FETCH FIRST`, `OFFSET … ROWS`, `IDENTITY`). Elsőbbség: hivatalos **Oracle 11g** dokumentáció.

Bemásolható keresők (5–10 mp):

```text
site:docs.oracle.com Oracle 11g SQL checklist COMMIT ROLLBACK GROUP BY syntax
```

```text
site:stackoverflow.com Oracle 11g SQL checklist COMMIT ROLLBACK GROUP BY -mysql -postgresql -sql-server
```

```text
Oracle Database 11g R2 SQL Language Reference SQL checklist COMMIT ROLLBACK GROUP BY
```

```text
"Oracle 11g" SQL checklist COMMIT ROLLBACK GROUP BY ROWNUM OR "INSERT ALL" OR MERGE -"FETCH FIRST" -mysql
```

