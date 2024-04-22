```mysql
DROP TRIGGER IF EXISTS trg_salari_empleats;
DELIMITER //
CREATE TRIGGER trg_salari_empleats BEFORE UPDATE ON empleats FOR EACH ROW
BEGIN
        IF((NEW.salari < (SELECT salari_min FROM feines WHERE feina_codi = NEW.feina_codi)) OR (NEW.salari > (SELECT salari_max FROM feines WHERE feina_codi = NEW.feina_codi))) THEN
                SET NEW.salari = OLD.salari;
    END IF;
END //

CREATE TRIGGER trg_salari_empleats_Insert BEFORE INSERT ON empleats FOR EACH ROW
BEGIN
        IF((NEW.salari < (SELECT salari_min FROM feines WHERE feina_codi = NEW.feina_codi)) OR (NEW.salari > (SELECT salari_max FROM feines WHERE feina_codi = NEW.feina_codi))) THEN
                SET NEW.salari = (SELECT salari_min FROM feines WHERE feina_codi = NEW.feina_codi);
    END IF;
END //
DELIMITER ;
```
