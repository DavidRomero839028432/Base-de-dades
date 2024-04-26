```mysql
DELIMITER //
DROP PROCEDURE IF EXISTS aumentarSueldo//
CREATE PROCEDURE aumentarSueldo()
BEGIN
	DECLARE vFiBucle BOOLEAN DEFAULT FALSE;
    DECLARE vDepartament_id INT;
    DECLARE vSalari DECIMAL;
    DECLARE vEmpleat_id INT;
    
    DECLARE cursor1 CURSOR FOR SELECT departament_id, salari, empleat_id from empleats;
    
    DECLARE CONTINUE HANDLER FOR NOT FOUND SET vFiBucle = TRUE;
    
    OPEN cursor1;
    FETCH cursor1 INTO vDepartament_id, vSalari, vEmpleat_id;
		WHILE vFiBucle = FALSE DO
        UPDATE departaments
			SET salari_avg = (SELECT AVG(salari)
								FROM empleats
							WHERE departament_id = vDepartament_id)
			WHERE departament_id = vDepartament_id;
        
        FETCH cursor1 INTO vDepartament_id, vSalari, vEmpleat_id;
        END WHILE;
    CLOSE cursor1;
END //
```
