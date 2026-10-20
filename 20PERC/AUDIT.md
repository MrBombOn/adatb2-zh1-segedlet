# 20PERC AUDIT

| Check | Elvárás | Státusz |
|-------|---------|---------|
| Oracle 11g ONLY | nincs FETCH FIRST / LIMIT / IDENTITY megoldásként | lásd README TILOS |
| DROP USER | all_users → CASCADE; nincs IF EXISTS | §1.1 / 01 |
| HAVING operátorok | `<` `<=` `=` `>=` `>` | §1.7 / OT-KOMPONENSES |
| Analitikus MÓD A/B | A: nincs rn=1 · B: van | §1.12 / INTEGRATED |
| USERS | nem kötelező | KÖRNYEZETFÜGGŐ |
| Solution bank | nincs TERMEK/KATEGORIA / KONYV/KOLCSONZES | README |
| Canonical érintetlen | 00-20-PERCES-ZH megmarad | ADDITÍV |
| NUL linkek | README-k tiszták | build script |
