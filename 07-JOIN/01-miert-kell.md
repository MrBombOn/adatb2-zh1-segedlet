# Miért kell JOIN?

Az adat **normalizált**: nem mindent egy táblába rakunk.
A hallgató neve egy helyen van, a jelentkezés máshol — össze kell kapcsolni.

```text
STUDENT (student_id, full_name)
ENROLLMENT (student_id, course_id)
COURSE (course_id, title)
```

Kérdés: „Ki milyen kurzusra jár?” → JOIN lánc.
