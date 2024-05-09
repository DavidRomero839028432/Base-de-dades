```js
//Recupera els empleats amb un salari entre 2000 i 6000
db.empleats.find({$and:[{salari:{$gte:2000}},{salari:{$lte:6000}}]})
```
