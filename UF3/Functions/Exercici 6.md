```mysql
DROP FUNCTION IF EXISTS spCategoria;
DELIMITER //
CREATE FUNCTION spCategoria(pCodiEmpleat INT) RETURNS VARCHAR(50)
NOT DETERMINISTIC READS SQL DATA
BEGIN
	DECLARE vCategoria VARCHAR(50);
    DECLARE vNumeroAnys INT;
    
    SELECT timestampdiff(YEAR, data_contractacio, CURDATE()) INTO vNumeroAnys
		from empleats
	WHERE empleat_id = pCodiEmpleat;
    
    IF vNumeroAnys BETWEEN 0 AND 1 THEN
		SET vCategoria = "Auxiliar";
	END IF;
    
	IF vNumeroAnys BETWEEN 2 AND 10 THEN
		SET vCategoria = "Oficial de segona";
	END IF;
    
	IF vNumeroAnys BETWEEN 11 AND 20 THEN
		SET vCategoria = "Oficial de primera";
	END IF;
    
	IF vNumeroAnys > 20 THEN
		SET vCategoria = "Que es jubili!";
	END IF;
    
    RETURN vCategoria;
END//
```
