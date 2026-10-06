# Constraint döntési fa

```text
Mi a szabály?
├─ Egyértelmű azonosító a sorhoz → PRIMARY KEY
├─ Értéknek léteznie kell másik táblában → FOREIGN KEY
├─ Egyedi legyen, de nem feltétlen PK → UNIQUE
├─ Mező ne lehessen üres → NOT NULL
└─ Értéktartomány / feltétel ugyanabban a sorban → CHECK
```

## FK vs JOIN

- **FK:** szabály (nem engedi a szemetet)  
- **JOIN:** lekérdezéskor összekapcsolás  

Mindkettő kellhet, de nem ugyanaz.
