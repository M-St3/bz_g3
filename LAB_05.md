# Zadanie 1
```
//baza.tabela.kolumna

wikingowie.kreatura.id_kreatury
select * from wikingowie.kreatura;
Create table zasob as select wikingowie;
Create table kreatura as select wikingowie;
Create table ekwipunek as select wikingowie;
Select * from zasob;
select * from zasob where typ='jedzenie';
/*in określa zbiór wartości
*/
select * from wikingowie.ekwipunek where idKreatury in (1,3,5);
```
-- zadanie2
```
select * from wikingowie.kreatury where rodzaj
select * from wikingowie.zasob where waga > 2 and waga < 5;
select * from wikingowie.zasob where waga between 2 and 5;
select * from wikingowie.kreatury where nazwa like '%or%' and udzwig between 30 and 70;
```
-- zadanie 3
```
select * from wikingowie.zasoby where month between 6 and 9;
select * from wikingowie.zasoby where rodzaj is not null order by waga desc; 
//order by 5 desc limit 3, 2; (bierze z 3 elementu i pobiera 2 elementy) 
select * from wikingowie.kreatura order by dataur desc;

//select distinct rodzaj, waga from wikingowie.zasob;
//select distinct(rodzaj), waga from wikingowie.zasob;
select * from kreatura where dataUr is not null order by dataUr asc limit 5;
```
-- zad 4
```
select distinct rodzaj from zasob;

//funkcja concat()
-- select concat('Kreatura z i', id_kreatury/ ' to ' , nazwa)
select concat(nazwa,' ',rodzaj) as jedna_kolumna from kreatura where rodzaj like 'w%';

select ilosc*waga from zasob where 2000<year(dataPozyskania) and year(datapozyskania)<2007;
```
-- zad 5
```
select waga*0.7 from zasob where rodzaj='jedzenie';
select * from wikingowie.zasob where rodzaj is null;
select * from wikingowie.zasob where rodzaj != null;
select distinct rodzaj from zasob where nazwa like 'Ba%' or '%os' order by rodzaj;
```
