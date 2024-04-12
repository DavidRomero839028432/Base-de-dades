```mysql
DELIMITER //
DROP PROCEDURE IF EXISTS spDeleteDepartment;
CREATE PROCEDURE spDeleteDepartment (pDepId INT)
BEGIN

	IF pDepId IS NOT NULL THEN
	DELETE FROM departaments
		WHERE departament_id = pDepId;
	
    CALL registres_logs('Departaments', 'DELETE', pDepId);
    END IF;

END //
```
