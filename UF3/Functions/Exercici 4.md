```mysql
DROP FUNCTION IF EXISTS spPringat;
DELIMITER //
CREATE FUNCTION spPringat(pCodiDep INT) RETURNS INT
NOT DETERMINISTIC READS SQL DATA
BEGIN
	DECLARE vRetorn INT;

	SET vRetorn = (SELECT MIN(salari)
                  FROM empleats
              WHERE departament_id = pCodiDep);

	RETURN vRetorn;
END
//
```
