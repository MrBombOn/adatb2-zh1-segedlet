# DDL / constraint sablonok

> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
CREATE TABLE <tabla> (
  <id>    NUMBER PRIMARY KEY,
  <nev>   VARCHAR2(<n>) NOT NULL,
  <szulo> NUMBER,
  CONSTRAINT <fk_nev> FOREIGN KEY (<szulo>) REFERENCES <szulo_tabla>(<id>),
  CONSTRAINT <chk_nev> CHECK (<feltetel>)
);
```

```sql
ALTER TABLE <tabla> ADD CONSTRAINT <nev> UNIQUE (<oszlop>);
```

```sql
CREATE VIEW <nezet> AS
SELECT <oszlopok> FROM <tabla> WHERE <feltetel>;
```

```sql
CREATE SEQUENCE <seq_nev> START WITH <n> INCREMENT BY 1;
```
