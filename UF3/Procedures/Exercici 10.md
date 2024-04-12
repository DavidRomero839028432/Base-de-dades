```mysql
DELIMITER //
CREATE PROCEDURE spDadesEmpleat (pEmpleatId INT, OUT pEmpleatNom VARCHAR(20), OUT pEmpleatCognom VARCHAR(20))
BEGIN
	SELECT nom, cognoms INTO pEmpleatNom, pEmpleatCognoms
		FROM empleats
	WHERE empelat_id = pEmpleatId;
END //
```
