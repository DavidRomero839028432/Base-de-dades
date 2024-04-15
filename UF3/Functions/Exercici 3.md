```mysql
DELIMITER //
DROP FUNCTION IF EXISTS spIncrement();
CREATE FUNCTION spIncrement(pEmpleatID INT, pIncrement INT) RETURNS INT
NOT DETERMINISTIC READS SQL DATA
BEGIN
	DECLARE vSalari INT;
    
    SELECT salari INTO vSalari
		FROM empleats
	WHERE empleat_id = pEmpleatID;
    
    SET vSalari = ((vSalari * pIncrement) / 100) + vSalari;
    
    return vSalari;
END //
```
