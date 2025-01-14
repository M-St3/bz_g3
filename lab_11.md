```
#Zadanie.1
create table student(
id_studenta int auto_increment,
imie varchar(100),
nazwisko varchar(100),
rok_studiow int not null,
data_urodzenia date,
primary key(id_studenta)
);
```
```
#Zadanie.2
drop table kierunek;
create table student(
id_studenta int auto_increment,
imie varchar(100) not null,
nazwisko varchar(100) not null,
rok_studiow int unsigned,
data_urodzenia date,
primary key(id_studenta)
);
```
```
#Zadanie.3
create table kierunek(
id_kierunku int unsigned auto_increment,
nazwa_kierunku varchar(200) not null,
primary key(id_kierunku)
);
```
```
#Zadanie.4
create table student_na_kierunku(
student int, 
kierunek int unsigned,
foreign key(student) REFERENCES student(id_studenta),
foreign key(kierunek) REFERENCES kierunek(id_kierunku),
constraint id_student_na_kierunku primary key(student, kierunek)
);
```
```
#Zadanie.5
create table przedmiot(
id_przedmiotu int auto_increment primary key,
nazwa_przedmiotu varchar(200) not null,
opis text
);
```
```
#Zadanie.6
create table kierunek_has_przedmioty(
kierunek int unsigned not null,
przedmiot int not null,
obowiozkowy bool default 1,
foreign key(kierunek) references kierunek(id_kierunku),
foreign key(przedmiot) references przedmiot(id_przedmiotu),
constraint id_kierunek_has_przedmioty primary key(kierunek, przedmiot)
);
```
```
#Zadanie.7
#Student
insert into student values(	default, "Krzysztof", "Brzęczyszczykiewicz", 1, "2000-03-03");
insert into student values(	default, "Jadzia", "Bladzia", 3, "2003-12-30");
insert into student values(	default, "Grzegorz", "Gżegżółka", 1, "2001-04-01");
insert into student values(	default, "Leon", "Zawodowiec", 2, "1987-10-09");
#kierunek
insert into kierunek values(default, "Kryminologia" );
insert into kierunek values(default, "Leśnictwo" );
#student_na_kierunku
insert into student_na_kierunku values();
