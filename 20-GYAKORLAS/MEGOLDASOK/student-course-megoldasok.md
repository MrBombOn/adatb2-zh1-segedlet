# STUDENT / COURSE — tanulási megoldások

> **TANULÁSI MEGOLDÁS – ZH alatt ne másold be.** Ezek a megoldások gyakorláshoz vannak; a ZH-n saját fejjel dolgozz.

## 1. Hallgatók listája

```sql
SELECT full_name, email
FROM   student
ORDER BY full_name;
```

## 2. Kredit küszöb

```sql
SELECT title
FROM   course
WHERE  credits >= <kuszob>;
```

## 3. Kik járnak a kurzusra

```sql
SELECT s.full_name, c.title
FROM   student s
JOIN   enrollment e ON e.student_id = s.student_id
JOIN   course c ON c.course_id = e.course_id
WHERE  c.course_id = <course_id>;
```

## 4. Nincs jelentkezés

```sql
SELECT s.full_name
FROM   student s
LEFT JOIN enrollment e ON e.student_id = s.student_id
WHERE  e.student_id IS NULL;
```

## 5. Kurzusonkénti darab

```sql
SELECT c.title, COUNT(*) AS jelentkezesek
FROM   course c
JOIN   enrollment e ON e.course_id = c.course_id
GROUP BY c.title
HAVING COUNT(*) >= 2;
```

## 6–7. UPDATE / INSERT

```sql
SELECT student_id, email FROM student WHERE student_id = <id>;
UPDATE student SET email = <uj_email> WHERE student_id = <id>;

INSERT INTO enrollment (student_id, course_id, enrolled_on, grade)
VALUES (<student_id>, <course_id>, SYSDATE, NULL);
```
