#### 1. Busca aquells desenvolupadors que han realitzat contribucions en OOP
```js
db.bios.find{contribs:'OOP'}
```
#### 2. Busca aquells desenvolupadors que han realitzat contribucions en OOP o Java
```js
db.bios.find({$or:[{contribs:'OOP'},{contribs:'Java'}]})
```
#### 3. Busca aquells desenvolupadors que han realitzat contribucions en OOP i Simula
```js
db.bios.find({$and:[{contribs:'OOP'},{contribs:'Simula'}]})
```
#### 4. Busca aquells desenvolupadors que siguin vius
```js
db.bios.find({deathYear:{$exists:false}})
```
#### 5. Busca aquells desenvolupadors que siguin morts
```js
db.bios.find({deathYear:{$exists:true}})
```
#### 6. Busca aquells desenvolupadors que han obtingut un premi a l’any 2002
```js
db.bios.find({"awards.year":2002})
```
#### 7. Busca aquells desenvolupadors que han obtingut exactament 3 premis
```js
db.bios.find({awards:{$size:3}})
```
