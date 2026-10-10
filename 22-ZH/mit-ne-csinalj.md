# Mit NE csinálj ZH-n

1. Ne másold be a repo tanulási példáit vakon.  
2. Ne használj `LIMIT`-et / `FETCH FIRST`-et (MySQL / 12c+ reflex) — Oracle 11g: `ROWNUM`.  
3. Ne írj `= NULL`-t.  
4. Ne UPDATE/DELETE WHERE nélkül.  
5. Ne hagyd ki a GROUP BY kötelező oszlopait.  
6. Ne keverd a WHERE-t a HAVING-gel.  
7. Ne tippelj JOIN kulcsot — keresd az FK-t.  
8. Ne hagyatkozz implicit dátumkonverzióra.  
9. Ne commitolj jelszót / secretet semmilyen fájlba.  
10. Ne pánikolj ORA hibánál: olvasd, javítsd, menj tovább.
