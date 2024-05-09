```js
Recupera els empleats que el seu número de telèfon comença per 515
db.empleats.find({telefon:{$regex:/^515/}})
```
