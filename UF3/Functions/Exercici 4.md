```mysql
DELIMITER //
DROP FUNCTION IF EXISTS spPringat;
CREATE FUNCTION spPringat(dept_id INT) RETURNS INT
BEGIN
    DECLARE min_salary INT;
    DECLARE min_salary_emp_id INT;

    -- Trobar el salari mínim per al departament
    SELECT MIN(salari) INTO min_salary
    FROM empleats
    WHERE departament_id = dept_id;

    -- Trobar l'identificador de l'empleat amb el salari mínim
    SELECT empleat_id INTO min_salary_emp_id
    FROM empleats
    WHERE departament_id = dept_id AND salari = min_salary
    LIMIT 1;

    RETURN min_salary_emp_id;
END//

```
