```js
//Recupera els empleats que no treballin de Vice President. Utilitza el codi de la feina "AD_VP"
db.empleats.find({"feina.codi":{$ne:"AD_VP"}})
```
