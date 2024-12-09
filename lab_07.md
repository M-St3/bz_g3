#Zadanie 1
#pkt1
```sql
create table etapy_wyprawy like wikingowie.etapy_wyprawy;
insert into etapy_wyprawy select * from wikingowie.etapy_wyprawy;
insert into kreatura select * from wikingowie.kreatura;
create table uczestnicy like wikingowie.uczestnicy;
create table sektor like wikingowie.sektor;
insert into wyprawa select * from wikingowie.wyprawa;
insert into uczestnicy select * from wikingowie.uczestnicy;
insert into sektor select * from wikingowie.sektor;
create table wyprawa like wikingowie.wyprawa;
```
use wikingowie;
#Dla każdej wyprawy wypisz jej nazwę, liczbę uczestników,
# oraz nazwy tych uczestników w jednej lini
# 1.Identyfikacja niezbędnych tabel
select w.nazwa, count(k.nazwa), 
group_concat(k.nazwa SEPARATOR '|') as liczba_uczestnikow
from wyprawa w
inner join uczestnicy u on w.id_wyprawy=u.id_wyprawry
inner join kreatura k on k.idKreatury=u.id_uczestnika
group by w.id_wyprawy;
#pkt2
#outer join
#
select w.nazwa, k.nazwa
from wyprawa w 
left join uczestnicy u on w.id_wyprawy=u.id_wyprawry
left join kreatura k on k.idKreatury=u.id_uczestnika
where w.id_wyprawy is null

#pkt3
select w.nazwa, sum(e.ilosc) 
from wyprawa w
inner join uczestnicy 

#Zadanie3
#Pkt 1 ifnull
select s.nazwa, ifnull(count(ew.sektor),'brak'), s.id_sektora
from etapy_wyprawy ew
right join sektor s on ew.sektor=s.id_sektora
group by s.id_sektora
# z pełną funkcją if(warunek, wartość jeżeli true, ... false)
select s.nazwa, 
if(count(ew.sektor)=0,'nie był odwiedzany',count(distinct(ew.sektor))) as ile_odwiedzono s.id_sektora 
from etapy_wyprawy ew
right join sektor s on ew.sektor=s.id_sektora
group by s.id_sektora

#Zadanie 4
#pkt 1
select nazwa, length(nazwa) from kreatura;
#pkt2
select sum((z.waga*e.ilosc)/count(u.id_uczestnicy)), u.wyprawa
from wyprwawa w inner join uczestnicy u on w.id_wyprawy=u.id_wyprawy
group by w.id_wyprawy;
