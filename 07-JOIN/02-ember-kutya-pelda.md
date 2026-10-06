# EMBER / KUTYA tanulási példa

> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

## Séma

```sql
CREATE TABLE ember (
  ember_id NUMBER PRIMARY KEY,
  nev      VARCHAR2(100) NOT NULL
);

CREATE TABLE kutya (
  kutya_id NUMBER PRIMARY KEY,
  nev      VARCHAR2(100) NOT NULL,
  gazdi_id NUMBER REFERENCES ember(ember_id)  -- FK: ki a gazdi?
);
```

## Kérdések

| Kérdés | JOIN típus |
|--------|------------|
| Emberek kutyáikkal (csak akinek van kutyája) | INNER |
| Minden ember, kutya nélkül is | LEFT (ember bal) |
| Kutyák gazdi nélkül (adatbaj) is | LEFT kutya felől / FK NULL |

```sql
SELECT e.nev AS gazdi, k.nev AS kutya
FROM   ember e
JOIN   kutya k ON k.gazdi_id = e.ember_id;
```

```sql
SELECT e.nev AS gazdi, k.nev AS kutya
FROM   ember e
LEFT JOIN kutya k ON k.gazdi_id = e.ember_id;
```
