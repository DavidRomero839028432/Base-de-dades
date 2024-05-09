```js
//Recupera els empleats que van ser contractats a partir de l’1 de gener de 1985
db.empleats.find({"data_contractacio":{"$gte":new Date(1985-01-01)}})
```
