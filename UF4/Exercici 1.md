```mysql
-- Obtenir de tots els empleats, el nom, cognoms i salari. Mostrar només 4 registres
db.empleats.find({},{nom:1, cognom:1, salari:1}).limit(4)
```
