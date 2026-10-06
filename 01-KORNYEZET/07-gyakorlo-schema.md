# Gyakorló séma (STUDENT / COURSE / ENROLLMENT)

> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

```sql
-- Tanulási példa – ne másold be ZH-megoldásként.
CREATE TABLE student (
  student_id   NUMBER PRIMARY KEY,
  full_name    VARCHAR2(100) NOT NULL,
  email        VARCHAR2(120) UNIQUE,
  birth_date   DATE
);

CREATE TABLE course (
  course_id    NUMBER PRIMARY KEY,
  title        VARCHAR2(120) NOT NULL,
  credits      NUMBER(2) CHECK (credits > 0)
);

CREATE TABLE enrollment (
  student_id   NUMBER REFERENCES student(student_id),
  course_id    NUMBER REFERENCES course(course_id),
  enrolled_on  DATE DEFAULT SYSDATE,
  grade        VARCHAR2(2),
  PRIMARY KEY (student_id, course_id)
);
```

Alternatíva: AUTHOR / BOOK / LOAN — lásd `20-GYAKORLAS/`.

Feltöltés: saját `INSERT` placeholder értékekkel (`09-DML/`).
