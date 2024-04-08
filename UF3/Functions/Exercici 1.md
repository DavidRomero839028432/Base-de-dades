```mysql
DROP FUNCTION IF EXISTS spData;
DELIMITER //
CREATE FUNCTION spData(pdataAConvertir DATE) RETURNS CHAR(10)
DETERMINISTIC
BEGIN
    DECLARE vRetorn CHAR(10);
    
    SET vRetorn = DATE_FORMAT(pdataAConvertir, '%d-%m-%Y');
    
    RETURN vRetorn;
END
//
```
