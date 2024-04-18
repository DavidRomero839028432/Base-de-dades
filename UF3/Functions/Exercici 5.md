```mysql
SELECT d.departament_id, d.nom, spPringat(d.departament_id) AS pringat
FROM departaments d;
```
