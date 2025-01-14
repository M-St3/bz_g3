```
#Zadanie 1.1
Select imie, nazwisko, data_urodzenia from pracownik;
```
```
#Zadanie1.2
Select imie, nazwisko, year(now())-year(data_urodzenia) as wiek from pracownik;
```
```
#Zadanie1.3
Select dzial.nazwa, count(pracownik.dzial) as liczba_pracownikow from pracownik, dzial where dzial.id_dzialu=pracownik.dzial group by nazwa;
```
```
#Zadanie1.4
Select kategoria.nazwa_kategori, count(stan_magazynowy.ilosc) as liczba_produktow
from kategoria, stan_magazynowy, towar 
where towar.id_towaru=stan_magazynowy.towar 
and towar.kategoria=kategoria.id_kategori 
group by nazwa_kategori;
```
```
#Zadanie1.5
select kategoria.nazwa_kategori, group_concat(towar.nazwa_towaru) as produkty
from kategoria, towar, stan_magazynowy 
where towar.id_towaru=stan_magazynowy.towar 
and towar.kategoria=kategoria.id_kategori group by nazwa_kategori;
```
```
#Zadanie1.6
Select round(avg(pensja)) as srednia_pensja from pracownik;
```
```
#Zadanie1.7
Select round(avg(pensja)) as srednia_pensja from pracownik where year(now())-year(data_zatrudnienia) >=5;
```
