```mysql
DELIMITER //
CREATE PROCEDURE spSwapSous (IN pEmpleatId1 INT, IN pEmpleatId2 INT)
BEGIN
    DECLARE vSalariTmp DECIMAL (8,2);

    IF (SELECT salari INTO vSalariTmp
        FROM empleats
    WHERE empleat_id = pEmpleatId1) IS NOT NULL
    AND
    IF (SELECT salari INTO vSalariTmp
        FROM empleats
    WHERE empleat_id = pEmpleatId2) IS NOT NULL 
    THEN

    SELECT salari INTO vSalariTmp
        FROM empleats
    WHERE empleat_id = pEmpleatId1;

    UPDATE empleats
        SET salari = (SELECT salari
                        FROM empleats
                    WHERE empleat_id = pEmpleatId2)
    WHERE empleat_id = pEmpleatId1;

    UPDATE empleats
        SET salari = pEmpleatId1
    WHERE empleat_id = pEmpleatId2;
END //
```
