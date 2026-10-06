# Tipikus logikai hibák (fut, de rossz)

1. **Elfelejtett WHERE** UPDATE/DELETE-nél  
2. **INNER helyett LEFT** (vagy fordítva) — hiányzó sorok  
3. **WHERE vs HAVING** keverése  
4. **`= NULL`**  
5. **Rossz JOIN kulcs** — duplikátumrobbanás  
6. **COUNT(*) vs COUNT(col)**  
7. **Dátum string összehasonlítás** maszk nélkül  
8. **Alias elírás** WHERE-ben (ott még nincs)  
9. **OR zárójel nélkül** AND mellett  
10. **SELECT *** amikor konkrét oszlop kell  

Ellenőrző kérdés: *Hány sort várok? Van NULL? Van 1:N szorzás?*
