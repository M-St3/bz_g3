
# LAB 4
## Zadanie 1
```
 a)
delete from postac where id_postaci=6 or id_postaci=4;
 b)
alter table przetwory drop foreign key przetwory_ibfk_1;
alter table przetwory drop foreign key przetwory_ibfk_2;
alter table walizka drop foreign key walizka_ibfk_1;
alter table postac change id_postaci id_postaci int;
alter table postac drop primary key;
```

## zadanie 2
```
 a)
alter table postac add pesel char(11) first;
update postac set pesel='11111111111' where id_postaci=1;
update postac set pesel='22222222222' where id_postaci=2;
update postac set pesel='33333333333' where id_postaci=3;
update postac set pesel='55555555555' where id_postaci=5;
update postac set pesel='77777777777' where id_postaci=7;
update postac set pesel='88888888888' where id_postaci=8;
alter table postac add primary key (pesel);
 b)
alter table postac modify rodzaj enum('viking','ptak','tesciowa','syrena');
 c)
insert into postac value('99999999999', 9, 'Gertruda Nieszczera', 'syrena', '1652-05-09', 62,null ,null);
```
## zadanie 3
```
 a)
update postac set statek='statek1' where nazwa like '%a%';
update postac set statek=null where nazwa='tesciowa';
 b)
update statek set max_ladownosc=max_ladownosc*0.7 where data_wod >1900;
 c)
alter table postac add check(wiek<='1000');
```
## zadanie 4
```
 a)
insert into postac values(1010101010101,10,'Loko','waz','1000-01-01','99',null,null);
 b)
create table marynarz like postac;
insert into marynarz select * from postac where statek is not null;
 c)
% klucze w table "marynarz" są takie jak w tabeli "postac"
```
## zadanie 5
```
 a)
update postac set statek=null where statek is not null;
 b) 
delete from postac where id_postaci=7;
 c)
delete from statek;
 d)
alter table postac drop foreign key postac_ibfk_1;
drop table statek;
 e)
create table zwierz(
id int  auto_increment,
nazwa varchar(45),
wiek int,
primary key(id)
);
 f)
INSERT INTO zwierz (nazwa, wiek) SELECT nazwa, wiek FROM postac WHERE rodzaj = 'ptak' OR rodzaj = 'waz';

```
