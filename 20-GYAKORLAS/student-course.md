# Gyakorlás: STUDENT / COURSE / ENROLLMENT

> **Tanulási példa – ne másold be ZH-megoldásként.** A sablonokban `<helyőrző>` jelöli, amit a feladat szerint kell kitölteni.

Séma: lásd `01-KORNYEZET/07-gyakorlo-schema.md`. Töltsd fel saját INSERT-ekkel.

## Feladatok (csak a kérdés — megoldás a MEGOLDASOK-ban)

1. Listázd az összes hallgató `full_name` és `email` mezőjét név szerint rendezve.
2. Add meg azoknak a kurzusoknak a címét, ahol a kredit legalább egy választott küszöb.
3. Kik járnak egy adott `course_id`-jú kurzusra? (név + kurzus cím)
4. Mely hallgatóknak **nincs** jelentkezésük?
5. Kurzusonként hány jelentkezés van? Csak ahol legalább 2.
6. Emeld egy hallgató emailjét (UPDATE) — előtte SELECT.
7. Vegyél fel új jelentkezést (INSERT) érvényes FK-kkal.
