```mysql
DELIMITER //
CREATE PROCEDURE spModificarDadesEmpleat (IN pEmpleatId INT, IN pEmpleatNom VARCHAR(20), IN pEmpleatCognom VARCHAR(20))
BEGIN
	UPDATE empleats
		SET nom = pEmpleatNom, 
			cognoms = pEmpleatCognom
		WHERE empleat_id = pEmpleatId;
END //
DELIMITER ;
```
