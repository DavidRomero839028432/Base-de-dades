```mysql
CREATE TABLE logs_usuaris(
	usuari VARCHAR(50),
    data	DATETIME,
    taula	VARCHAR(50),
    accio	VARCHAR(50),
    valor_pk VARCHAR(50)
);
DELIMITER ;

DELIMITER //
DROP PROCEDURE IF EXISTS registres_logs;
CREATE PROCEDURE registres_logs (pTaula VARCHAR(50), pAccio VARCHAR(50), pValorPK VARCHAR(50))
BEGIN
	INSERT INTO logs_usuaris (usuari, data, taula, accio, valor_pk)
		VALUES(CURRENT_USER, NOW(), pTaula, pAccio, pValorPK);
END //
```
