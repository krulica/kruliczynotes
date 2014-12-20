####1.1
```SELECT * FROM pracownik```
####1.2
```SELECT imie FROM pracownik```
####1.3
```SELECT imie, nazwisko, dzial FROM pracownik```
####2.1
```SELECT imie, nazwisko, pensja FROM pracownik ORDER BY pensja DESC```
####2.2
```SELECT imie, nazwisko, pensja FROM pracownik ORDER BY nazwisko ASC, imie ASC```
####2.3
```SELECT nazwisko, dzial, stanowisko FROM pracownik ORDER BY dzial ASC, stanowisko DESC```

####3.1
```SELECT DISTINCT dzial FROM pracownik```
####3.2
```SELECT DISTINCT dzial, stanowisko FROM pracownik```
####3.3
```SELECT DISTINCT dzial, stanowisko FROM pracownik ORDER BY dzial DESC, stanowisko DESC```

####4.1
```
SELECT imie, nazwisko
FROM pracownik
WHERE imie='Jan';
```
####4.2
```
SELECT imie, nazwisko
FROM pracownik
WHERE stanowisko='sprzedawca'
```
####4.3
```
SELECT imie, nazwisko, pensja
FROM pracownik
WHERE pensja>1500
ORDER BY pensja DESC;
```
####5.1
```
SELECT imie,nazwisko,dzial,stanowisko
FROM pracownik
WHERE dzial='obsługa klienta' AND stanowisko='sprzedawca'
```
####5.2
```
SELECT imie, nazwisko, dzial, stanowisko
FROM pracownik
WHERE dzial='techniczny' AND (stanowisko='kierownik' OR stanowisko='sprzedawca')
```
####5.3
```
SELECT *
FROM samochod
WHERE marka!='fiat' AND marka!='ford'
```
####6.1
```
SELECT *
FROM samochod
WHERE marka IN ('mercedes', 'seat', 'opel')
```
####6.2
```
SELECT imie, nazwisko, data_zatr
FROM pracownik
WHERE imie IN ('Anna', 'Marzena', 'Alicja')
```
####6.3
```
SELECT imie, nazwisko, miasto
FROM klient
WHERE miasto NOT IN ('Warszawa', 'Wrocław')
```
####7.1
```
SELECT imie, nazwisko
FROM klient
WHERE nazwisko LIKE '%k%'
```
####7.2
```
SELECT imie, nazwisko
FROM klient
WHERE nazwisko LIKE 'D%ski'
```
####7.3
```
SELECT imie, nazwisko
FROM klient
WHERE nazwisko LIKE '_o%' OR nazwisko LIKE '_a%'
```
####8.1
```
SELECT *
FROM samochod
WHERE poj_silnika BETWEEN 1100 AND 1600
```
####8.2
```
SELECT *
FROM pracownik
WHERE data_zatr BETWEEN '1997-01-01' AND '1997-12-31'
```
####8.3
```
SELECT *
FROM samochod
WHERE (przebieg BETWEEN 10000 AND 20000) OR (przebieg BETWEEN 30000 AND 40000)
```
####9.1
```
SELECT *
FROM pracownik
WHERE dodatek IS NULL
```
####9.2
```
SELECT *
FROM klient
WHERE nr_karty_kredyt IS NOT NULL
```
####9.3
```
SELECT imie, nazwisko, COALESCE(dodatek, '0') AS dodatek
FROM pracownik
```
####10.1
```
SELECT imie, nazwisko, pensja, COALESCE(dodatek, '0') AS dodatek, COALESCE (dodatek, '0')+pensja AS do_zaplaty
FROM pracownik
```
####10.2
```
SELECT imie, nazwisko, pensja*1.5 AS pensja
FROM pracownik
```
####10.3
```
SELECT imie, nazwisko, COALESCE (dodatek, '0')+pensja AS do_zaplaty, ((COALESCE (dodatek, '0')+pensja)*0.01) AS procent
FROM pracownik
```
####11.1
```
SELECT TOP 1 imie, nazwisko 
FROM pracownik
ORDER BY data_zatr ASC
```
####11.2
```
SELECT TOP 5 imie, nazwisko
FROM pracownik
ORDER BY nazwisko,imie ASC
```
####11.3
```
SELECT TOP 1 *
FROM wypozyczenie
ORDER BY data_wyp DESC
```
####12.1
```
SELECT imie, nazwisko, data_zatr
FROM pracownik
WHERE (MONTH(data_zatr)=5)
ORDER BY nazwisko, imie ASC 
```
####12.2
```
SELECT imie, nazwisko, GETDATE() AS data, DATEDIFF(d, data_zatr,GETDATE()) AS liczba_dni
FROM pracownik
ORDER BY liczba_dni DESC
```
####12.3
```
SELECT marka,typ, DATEDIFF(yy, data_prod, GETDATE()) AS wiek
FROM samochod
ORDER BY wiek DESC
```
####13.1
```
SELECT LEFT(imie,1)+'.'+LEFT(nazwisko,1)+'.' AS inic, imie,nazwisko
FROM pracownik
ORDER BY inic, imie, nazwisko ASC 
```
####13.2
```
SELECT UPPER(LEFT(imie,1))+LOWER(RIGHT(imie,LEN(imie)-1)) AS imie, UPPER(LEFT(nazwisko,1))+LOWER(RIGHT(nazwisko,LEN(nazwisko)-1)) AS nazwisko
FROM pracownik  
```
####13.3
```
SELECT imie, nazwisko, STUFF(nr_karty_kredyt,LEN(nr_karty_kredyt)-5,6,'xxxxxx') AS nr_kraty_kredyt
FROM klient  
```
####14.1
```
UPDATE pracownik
SET dodatek=50
WHERE dodatek IS NULL
```
####14.2
```
UPDATE klient
SET imie='Jerzy', nazwisko='Nowak'
WHERE id_klient=10
```
####14.3
```
UPDATE pracownik
SET dodatek=dodatek+100
WHERE pensja<1500
```
####15.1
```
delete from klient
where id_klient=17
```
####15.2
delete from wypozyczenie
where id_klient=17
```
####15.3
delete from samochod
where przebieg>60000
```
####16.1
```
insert into klient(id_klient,imie,nazwisko,ulica,numer,miasto,kod,telefon)
values (121,'Adam','Cichy','Korzenna','12','Warszawa',00-950,'123-456-321')
```
####16.2
```
insert into samochod (id_samochod,marka,typ,data_prod,kolor,poj_silnika,przebieg)
values (50,'Skoda','Octavia','2012-09-01','srebrny',1986,5000)
```
####17.1
```
SELECT s.id_samochod, s.marka, s.typ, w.data_wyp, w.data_odd
from samochod s inner join wypozyczenie w on s.id_samochod=w.id_samochod
where w.data_odd is Null
```
####17.2
```
select k.imie,k.nazwisko,w.id_samochod,w.data_wyp
from klient k inner join wypozyczenie w on k.id_klient=w.id_klient
where w.data_odd is null
order by k.nazwisko,k.imie asc
```
####17.3
```
select k.imie,k.nazwisko,w.data_wyp,w.kaucja
from klient k inner join wypozyczenie w on k.id_klient=w.id_klient
where w.kaucja is not null
```
####18.1
```
select k.imie,k.nazwisko,w.data_wyp,s.marka,s.typ
from klient k inner join wypozyczenie w on k.id_klient=w.id_klient inner join samochod s on w.id_samochod=s.id_samochod
order by k.nazwisko,k.imie,s.marka,s.typ asc
```
####18.2
```
select m.ulica,m.numer,s.marka,s.typ
from miejsce m inner join wypozyczenie w on m.id_miejsce=w.id_miejsca_wyp inner join samochod s on w.id_samochod=s.id_samochod
order by m.ulica,m.numer,s.marka,s.typ asc
```
####18.3
```
select s.id_samochod,s.marka,s.typ,k.imie,k.nazwisko
from samochod s inner join wypozyczenie w on s.id_samochod=w.id_samochod inner join klient k on w.id_klient=k.id_klient
order by s.id_samochod,k.nazwisko,k.imie asc
```
####19.1
```select MAX(pensja) from pracownik```
####19.2
```select AVG(pensja) from pracownik```
####19.3
```select MIN(data_prod) from samochod```
####20.1
```
select k.imie,k.nazwisko, COUNT (w.id_wypozyczenie) as ilosc_wyp
from klient k left join wypozyczenie w on k.id_klient=w.id_klient
group by k.imie,k.nazwisko,k.id_klient
order by ilosc_wyp desc
```
####20.2
```
select s.id_samochod,s.marka,s.typ, COUNT(w.id_wypozyczenie) as ilosc_wyp
from samochod s left join wypozyczenie w on s.id_samochod=w.id_samochod
group by s.id_samochod,s.marka,s.typ
order by ilosc_wyp asc
```
####20.3
```
select p.imie,p.nazwisko, COUNT(w.id_wypozyczenie) as ilosc_wyp
from pracownik p left join wypozyczenie w  on p.id_pracownik=w.id_pracow_wyp
group by p.imie,p.nazwisko
order by ilosc_wyp desc
```
####21.1
```
select k.imie,k.nazwisko, COUNT(w.id_wypozyczenie) as ilosc_wyp
from klient k join wypozyczenie w on k.id_klient=w.id_klient
group by k.imie,k.nazwisko
having COUNT(w.id_wypozyczenie)>=2
order by k.nazwisko,k.imie
```
####21.2
```
select s.id_samochod,s.marka,s.typ, COUNT(w.id_wypozyczenie) as ilosc_wyp
from samochod s join wypozyczenie w on s.id_samochod=w.id_samochod
group by s.id_samochod,s.marka,s.typ
having COUNT(w.id_wypozyczenie)>=5
order by s.marka,s.typ
```
####21.3
```
select p.imie,p.nazwisko, COUNT(w.id_wypozyczenie) as ilosc_wyp
from pracownik p join wypozyczenie w on p.id_pracownik=w.id_pracow_wyp
group by p.nazwisko,p.imie
having count(w.id_wypozyczenie)>=20
order by COUNT(w.id_wypozyczenie),p.nazwisko,p.imie
```

####22.1
```
select imie,nazwisko,pensja
from pracownik
where pensja=(select MAX(pensja) from pracownik)
```
####22.2
```
select imie,nazwisko,pensja
from pracownik
where pensja>(select AVG(pensja) from pracownik)
```
####22.3
```
select marka,typ,data_prod from samochod
where data_prod=(select MIN(data_prod) from samochod)
```
####23.1
```
select marka,typ,data_prod from samochod
where id_samochod not in (select distinct id_samochod from wypozyczenie)
```
####23.2
```
select imie,nazwisko from klient
where id_klient not in (select distinct id_klient from wypozyczenie)
order by nazwisko,imie asc
```
####23.3
```
select imie,nazwisko from pracownik
where id_pracownik not in (select distinct id_pracow_wyp from wypozyczenie)
```
####24.1
```
select s.id_samochod,s.marka,s.typ
from samochod s inner join wypozyczenie w on s.id_samochod=w.id_samochod
group by s.id_samochod,s.marka,s.typ
having COUNT(w.id_samochod)=
(
select top 1 COUNT(w.id_samochod) as il_wyp
from wypozyczenie w 
group by w.id_samochod
order by il_wyp desc
)
order by s.marka,s.typ asc
```
####24.2
```
select imie,nazwisko from pracownik
where id_pracownik not in (select distinct id_pracow_wyp from wypozyczenie)

select k.id_klient,k.nazwisko,k.imie
from klient k right join wypozyczenie w on k.id_klient=w.id_klient
group by k.id_klient,k.nazwisko,k.imie
having COUNT(w.id_klient)=
(
select top 1 COUNT(w.id_klient) as il_wyp
from wypozyczenie w
group by w.id_klient
order by il_wyp asc
)
order by k.id_klient,k.nazwisko,k.imie asc
```
####24.3
```
select p.id_pracownik,p.nazwisko,p.imie
from pracownik p inner join wypozyczenie w on p.id_pracownik=w.id_pracow_wyp
group by p.id_pracownik,p.nazwisko,p.imie
having COUNT(w.id_pracow_wyp)=
(
select TOp 1 count(w.id_pracow_wyp) as il_wyp
from wypozyczenie w
group by w.id_pracow_wyp
order by il_wyp asc
)
order by p.nazwisko,p.imie
```
####25.1
```
UPDATE pracownik
set pensja=pensja*1.1
where pensja<(select AVG(pensja) from pracownik)
```
####25.2
```
update pracownik
set dodatek=dodatek+10
where id_pracownik in
(select distinct id_pracow_wyp from wypozyczenie where (MONTH(data_wyp)=5))
```
####25.3
```
update pracownik
set pensja=0.95*pensja
where id_pracownik not in
(select distinct id_pracow_wyp from wypozyczenie where(YEAR(data_wyp)=1999))
```
####26.1
```
delete from klient
where id_klient not in
(select distinct id_klient from wypozyczenie)
```
####26.2
```
delete from samochod
where id_samochod not in
(select distinct id_samochod from wypozyczenie)
```
####26.3
```
delete from pracownik 
where id_pracownik not in (select distinct id_pracow_wyp from wypozyczenie)
```
####27.1a
```
select nazwisko,imie from klient
union
select nazwisko,imie from pracownik
order by nazwisko,imie
```
####27.1b
```
select nazwisko,imie from klient
union all
select nazwisko,imie from pracownik
order by nazwisko,imie
```
####27.2
```
select imie,nazwisko from klient
intersect
select imie,nazwisko from pracownik
order by nazwisko,imie
```

####27.3
```
select imie,nazwisko from klient
except
select imie,nazwisko from pracownik
order by nazwisko,imie
```
