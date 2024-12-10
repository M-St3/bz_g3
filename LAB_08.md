# Zadanie. 1
```sql
DELIMITER //
CREATE TRIGGER kreatura_before_insert
BEFORE INSERT ON kreatura
FOR EACH ROW
BEGIN
IF NEW.waga < 0
THEN
	SET NEW.waga = 0;
END IF;
END
//
DELIMITER ;
```
