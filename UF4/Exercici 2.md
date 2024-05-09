```js
-- Mostra la quantitat de departaments que hi ha
db.departaments.find({},{departament_id:1}).count()
```
