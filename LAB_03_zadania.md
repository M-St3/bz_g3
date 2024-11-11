# LAB_03
### Zadanie.1
```
create table postac (
id_postaci int not null auto_increment,
nazwa varchar(40),
rodzaj ENUM(wiking, ptak, kobieta),
data_ur date default,
wiek smallint unsigned
primary key (id_postaci)
);
insert into postac values ( 1,'Bjorn', 'wiking', 1580, 444);
insert into postac values ( default,'Drozd', 'ptak', 2020, 4 );
insert into postac values ( 3,'Tesciowa', 'kobieta', 1936, 84);
update postac set wiek = 88 where id_postaci=3;
```
### Zadanie.2
```
create table walizka (
id_walizki int not null auto_increment,
pojemnosc varchar(40),
kolor ENUM(rowy, czerwony, teczowy, zolty),
id_wlasciciela CASCADE DELETE,
primary key (id_walizki),
foreign key (id_wlasciciela) 
);
 alter table walizka alter kolor set default 'rozowy';
insert into walizka values (default,'5 litrow szesciennych', default, 1);
insert into walizka values (default,'5 litrow szesciennych', default, 3);


```

### Zadanie.3
```
create table izba (
adres_budynku varchar(40),
nazwa_izby varchar(40)
metraz smallint unasigned,
wlasciciel int,
primary key (adres_budynku, nazwa_izby)
foreign key (wlasciciel) references postac(id_postac) on delete SET null
);
alter table izba add kolor_izby varchar(40) after metraz;
alter table izba alter kolor set default 'czarny';
insert into izba values( 'psychiatryczna 18', 'spiżarnia', '5m2', 'tesciowa');
```

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
### Zadanie.5
##### .1
```
insert into postac values ( 1,'Jorn', 'wiking', 1580, 444);
insert into postac values ( 2,'Horn', 'wiking', default, default );
insert into postac values ( 3,'Worn', 'wiking', 1544, 480);
insert into postac values ( 4,'Torn', 'wiking', 1590, 434);
insert into postac values ( 5,'Wladek', 'wiking', 1680, 344);
```
##### .2
```
create table statek (
nazwa_statku varchar(40),
rodzaj_statku ENUM(lodka, motorowka, lodz podwodna, statek),
data_wodowania date default,
max_ladownosc smallint unsigned,
pirmary key(nazwa_statku)
);
```
##### .3
```
insert into statek values('statek1', 'statek', default, 5);
insert into statek values('statek2', 'statek', default, 10);
```
##### .4
```
alter table postac add fukcja varchar(40);
```
##### .5
```
update tbale postac set funkcja= 'kapitan' where id_postaci ='1';
```
##### .6
```
ALTER TABLE postac
ADD FOREIGN KEY (statki) REFERENCES statek(nazwa_statku);
```
##### .7
```

```
##### .8
```
delete from Izba where nazwa_izby = 'spizarnia';
```
##### .9
```
drop table izba;
```
