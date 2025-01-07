```
SELECT imie, nazwisko, data_urodzenia from pracownik;
SELECT imie, nazwisko, year(now()) - year(data_urodzenia) from pracownik;
SELECT dzial.nazwa, count(pracownik.dzial) as liczba_pracownikow from pracownik, dzial where id_dzialu = pracownik.dzial;
SELECT kategoria.nazwa_kategori, towar.kategoria from towar, kategoria where id_towaru = id_kategori;
SELECT kategoria.nazwa_kategori, group_concat(nazwa_towaru) as produkt
from kategoria, towar


SELECT round(avg(pracownik.pensja),2) from pracownik;
SELECT round(avg(pracownik.pensja),2), year(now())-year(data_zatrudnienia) from pracownik where ;
```
