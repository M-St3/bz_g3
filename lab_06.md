
```
#Zadanie 1
#pkt.1
select avg(waga) from wikingowie where rodzaj='wiking'; 
#Wyświetl średnią wagę oraz liczbę kreatur dla każdego rodzaju
#pkt.2
select rodzaj, avg(waga), count(*) from kreatura group by rodzaj;
#dwa sposoby na wyświetlenie średniej wieku dla każdego rodzaju kreatury
#pkt.3
select 2024 - year(dataUr) from kreatura;
select year(now()) - year(dataUr) as wiek from kreatura;
# + funkcja avg + grupowanie
```
```
#Zadanie 2
#pkt1
select rodzaj, sum(waga * ilosc) from zasob group by rodzaj;
#pkt2
# HAVING - to where z wartości agregującej
# select rodzaj, sum(waga * ilosc) from zasob
# having sum(waga*ilosc) > 100 group by rodzaj;
select rodzaj, sum(waga * ilosc) as sum_waga from zasob 
group by rodzaj having sum_waga > 100;
#pkt 2
select nazwa, avg(waga) from zasob where ilosc >= 4
group by nazwa having sum(waga) > 10;
#pkt3
#select count(nazwa) from zasob;
#select count(distinct nazwa) from zasob;
#select count(distinct (nazwa)) from zasob; #to nie ma sensu (ale jest poprawnie zapisane)
#select nazwa, rodzaj from zasob order by rodzaj;
select rodzaj, count(distinct nazwa) from zasob group by rodzaj
having sum(ilosc) > 1;
```
```
#zadanie 3
#select idKreatury, nazwa from kreatura where idKreatury =1;
#select* from ekwipunek where idKreatury = 1;
kreatura.idKreatury, nazwa, ekwipunek.idKreatury,
idZasobu, ilosc from kreatura, ekwipunek where
ekwipunek.idKreatury=kreatura.idKreatury;
#pkt.1
select kreatura.idKreatury, nazwa, ekwipunek.idKreatury,
idZasobu, ilosc from kreatura inner join ekwipunek on
ekwipunek.idKreatury=kreatura.idKreatury;
#pkt.2
select kreatura.idKreatury, zasob.nazwa, ekwipunek.idKreatury, kreatura.nazwa from kreatura
inner join ekwipunek on ekwipunek.idKreatury=kreatura.idKreatury
inner join zasob on zasob.idZasobu = ekwipunek.idZasobu;

#select idKreatury from Kreatura;
#select distinct idKreatury from ekwipunek;
#podzapytanie
#select idKreatury from Kreatura where idLreatury not in 
#(select idKreatury from ekwipunek where idKreatury is not null); #tylko wtedygdy id #kreatury is not null
#left join
#pkt.3
select k.idKreatury, k.nazwa, e.idKreatury from kreatura k
left join ekwipunek on k.idKreatury=e.idKreatury where e.idKreatury is null;
```
```
#zadanie4
#pkt1(nautral join)
#select * from kreatura natural join ekwipunek;

select kreatura.nazwa, zasob.idZasobu from kreatura
natural join ekwipunek
inner join zasob on ekwipunek.idZasobu = zasob.idZasobu
where kreatura.rodzaj='wiking' and dataUr between '1670.01.01' and '1680.01.01';

#pkt2 złączanie: kreatura, ekwipunek, zasob
#where na zasob (bo tylko jedzenie)
#posortować (order by) + przyciąć wyniki (limit)

select kreatura.nazwa, kreatura.dataUr, zasob.rodzaj from kreatura
natural join ekwipunek
inner join zasob on ekwipunek.idZasobu = zasob.idZasobu
where zasob.rodzaj is not null
order by kreatura.dataUr desc limit 5;

#pkt 3 połązenie 
select k1.idKreatury, k2.idKreatury, k1.nazwa, k2.nazwa 
from kreatura k1
where = 'k1.idKreatury' and 'k2.idKreatury' > 5
inner join kreatura k2 in k1.idKreatury=k2.idKreatury;
```
```
#zadanie 5 group by rodzaj ilosc ekwipunku (sum(ilosc))
#pkt1
select kreatura.rodzaj, avg(zasob.waga) from kreatura
natural join ekwipunek
inner join zasob on ekwipunek.idZasobu = zasob.idZasobu
where not kreatura.rodzaj='malpa' and not 'waz'
and ekwipunek.ilosc < 30
group by kreatura.rodzaj;
#pkt2
select rodzaj, max(dataUr), min(dataUr) from kreatura group by rodzaj;
```
