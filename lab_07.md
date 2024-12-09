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
#pkt2
```sql
select wyprawa.nazwa, kreatura.nazwa
from wyprawa  
right join uczestnicy on wyprawa.id_wyprawy=uczestnicy.id_wyprawy
right join kreatura on kreatura.idKreatury=uczestnicy.id_uczestnika
where wyprawa.id_wyprawy is null;
```
#pkt3
```sql
select wyprawa.nazwa, sum(ekwipunek.ilosc)
from wyprawa 
inner join uczestnicy on wyprawa.id_wyprawy=uczestnicy.id_wyprawy
inner join kreatura on kreatura.idKreatury=uczestnicy.id_uczestnika
inner join ekwipunek on ekwipunek.idKreatury=ekwipunek.idEkwipunku
group by wyprawa.nazwa;
```
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
