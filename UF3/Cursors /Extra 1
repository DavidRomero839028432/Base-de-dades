```mysql
DELIMITER //
DROP PROCEDURE IF EXISTS salariAVG//
CREATE PROCEDURE salariAVG()
BEGIN
	DECLARE vDepartament_id INT;
    DECLARE vSalari DECIMAL;
    DECLARE vFiBucle INT DEFAULT 0;
    
    DECLARE cursor1 CURSOR FOR SELECT departament_id, salari FROM empleats;
    
    DECLARE CONTINUE HANDLER FOR NOT FOUND SET vFiBucle = 1;
    
    OPEN cursor1;
    
    FETCH cursor1 INTO vDepartament_id, vSalari;

		bucle: LOOP
			IF vFiBucle = 1 THEN
				LEAVE bucle;
			END IF;
            
		UPDATE departaments
			SET salari_avg  = (SELECT AVG(salari)
								FROM empleats
							WHERE departament_id = vDepartament_id);
            
		END LOOP;
    CLOSE cursor1;
    
END //
```
