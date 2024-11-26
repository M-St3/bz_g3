'''
select * from wikingowie.zasoby where rodzaj='';

-- pkt 2
-- funkcja concat()
-- select concat('Kreatura z i', id_kreatury/ ' to ' , nazwa)
select concat('Kreatura z id',idKreatury, ' to ', nazwa) from wikingowie.kreatura;

-- from wikingowie.kreatura
-- pkt 3
Select * from wikingowie.zasoby 
-- zad 5
select * from wikingowie.zasob where rodzaj is null;
select * from wikingowie.zasob where rodzaj != null;
#Zadanie 1, pkt2
#Wyświetl średnią wagę oraz liczbę kreatur dla każdego rodzaju
select rodzaj, avg(waga), count(*) from kreatura group by rodzaj;
#dwa sposoby na wyświetlenie średniej wieku dla każdego rodzaju kreatury
select 2024 - year(dataUrodzenia) from kreatura;
select year(now()) - year(dataUrodzenia) as wiek from kreatura;
# + funkcja avg + grupowanie
#Zadanie 2
select rodzaj, sum(waga * ilosc) from zasob group by rodzaj;
#pkt2
# HAVING to where z wartości agregującej
# select rodzaj, sum(waga * ilosc) from zasob
# having sum(waga*ilosc) > 100 group by rodzaj;
'''
