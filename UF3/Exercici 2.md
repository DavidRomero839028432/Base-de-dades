# Exercici 2
```mysql
DELIMITER //
create function spPotencia(pBase INT, pExponent INT) returns INT
NOT DETERMINISTIC READS SQL DATA
BEGIN
	DECLARE vResultat INT DEFAULT 1;
    DECLARE i INT;
    IF pExponent < 0 THEN
        SET pBase = 1 / pBase;
        SET pExponent = -pExponent;
    END IF;
    SET i = 1;
    WHILE i <= pExponent DO
        SET vResultat = vResultat * pBase;
        SET i = i + 1;
    END WHILE;
    RETURN vResultat;
END//
DELIMITER ;
```
