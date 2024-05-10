#### 1. Busca els estudiants de gènere masculí
```js
db.students.find({gender:"H"})
```
#### 2. Digues quina és la quantitat d’estudiants de gènere femení
```js
db.students.find({gender:"M"},{}).count()
```
