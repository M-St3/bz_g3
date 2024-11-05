# LAB_03

### Zadanie.4

```
create table przetwory (
id_przetworu int not null auto_increment,
rok_produkcji smallint unsigned,
id_wykonawcy int,
zawartosc varchar(50),
dodatek varchar(50) default 'papryczka chilli',
id_konsumenta int,
primary key (id_przetworu),
foreign key (id_wykonawcy) references postac(id_postaci),
foreign key (id_konsumenta) references postac(id_postaci)
);
SELECT * FROM infs_stepczykm.przetwory;
alter table przetwory alter rok_produkcji set default '1654';
insert into przetwory values (default, default, '1', 'bigos', default, '1');
delete from przetwory where id_przetworu= '1';
update przetwory SET id_przetworu= '1' WHERE id_przetworu='2';
```
