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
```sql
create table archiwum_wypraw(
id_wyprawy int not null auto_increment,
nazwa varchar(50),
data_rozpoczecia date,
data_zakonczenia date,
kierownik varchar(50),
primary key(id_wyprawy)
);

DELIMITER //
CREATE TRIGGER id_kreatury_before_delete
BEFORE DELETE kreatura.id_kreatury
FOR EACH ROW
BEGIN
insert INTO archiwum_wypraw.kierownik 
END IF;
END

DELIMITER ;


DELIMITER //
CREATE PROCEDURE elikisir_sily(IN id_kreatura int)
BEGIN
Update kreatura.udzwig set udzwig = 1.2 * udzwig where kreatura = id_kreatury;
END
//
DELIMITER ;

```
