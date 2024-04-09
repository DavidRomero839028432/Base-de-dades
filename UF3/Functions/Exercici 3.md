```mysql
DROP FUNCTION IF EXISTS spIncrement;
DELIMITER //
CREATE FUNCTION spIncrement(pCodiEmpleat INT, pPercentatge INT) RETURNS FLOAT
NOT DETERMINISTIC READS SQL DATA
BEGIN
    DECLARE vRetorn FLOAT;
    DECLARE vSalari FLOAT;

    SET vSalari = (SELECT salari
                    FROM empleats
                WHERE empleat_id = pCodiEmpleat);
    
    SET vRetorn = ((vSalari / 100) * 10) + vSalari;
    RETURN vRetorn;
END 
//
DELIMITER ;
```
