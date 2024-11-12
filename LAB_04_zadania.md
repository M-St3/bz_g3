SELECT * FROM infs_stepczykm.postac;
alter table postac add pesel CHAR(11) first;
alter table postac add primary key(pesel);
update postac set pesel=12345678912 where nazwa='Bjorn';
update postac set pesel=21372137213 where nazwa='Drozd';
update postac set pesel=22222222222 where nazwa='Tesciowa';
update postac set pesel=12121212121 where nazwa='Horn';
alter table postac modify rodzaj enum('wiking', 'kobieta','ptak','syrena');
insert into postac (32323232323, default, Gertruda Nieszczera, syrena, default, default);
select nazwa from postac where nazwa like '%a%';
# % - dowolny ciąg znakówith
# _ - dokl
update postac set state




# pkt c
alter table postac add check(wiek <= 1000);
# check (warunek na kolumnie lub kolumnach) 
# zad 4 b
# sposób 1
#krok 1 - kopia struktury
create table marynarz like postac;
# krok 2 - kopia danych
insert into marynarz select*from postac where statek is not null; # lub <> roóżny od
#sposób 2 - create table as select
create table marynarz as select*from postac;\



SELECT * FROM infs_stepczykm.postac;
# Lab 4 zad.1

#krok 1- usunięcie klucza głównego
alter table postac drop primary key;
#krok 2- 1 się nie powiódł tym razem
alter table postac modify id_postaci int;

#krok 2 - krok 1 się nie powiódł tym razem 
alter table walizka drop foreign key
alter table izba drop foreign key izba
#krok 3 - krok 2 tym razem się nie powiódł
show create table przetwory
#zad.2
alter table postac add pesel CHAR(11) first;
select * from postac;
update postac set pesel=12345678912 where nazwa='Bjorn';


