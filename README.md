kruliczynotes
=============
--Imię i nazwisko:Anna Król-Lewczuk
--Data i godzina: 21.12.2014
--Grupa laboratoryjna: 11.02
--Obowiązująca baza danych: sklep, http://fidytek.pl/bazy_danych/bd_skrypt_sql/sklep_mssql 

--Napisać instrukcje SQL (dla MS SQL Server) realizujące poniższe zadania.

--CCC1 [3 pkt]
--Znajdź klientów (nazwisko, imie, telefon), których nazwiska
--rozpoczynają się od spółgłoski.
--Wynik posortuj leksykograficznie po nazwie nazwisku i imieniu klienta.
--Rozwiązanie:

use sklep 

select nazwisko,imie,telefon from klient
where (select left(nazwisko,1) as inic ('A''E''I''O''U''Y') from klient)
order by nazwisko,imie asc;



--CCC2 [3 pkt]
--Dla każdego producenta (tabela producent kolumna nazwa), wyświetl informację 
--ile znajduje się jego produktów w tabeli produkt.
--Uwzględnij też tych producentów, którzy nie posiadają żadnego produktu 
--w tabeli produkt.
--Wynik posortuj malejąco po obliczonej ilości, a dla takiej samej 
--ilości posortuj leksykograficznie po nazwie producenta.
--Rozwiązanie:
use sklep

select a.nazwa, COUNT(b.id_producent) as ilosc
from producent a left join produkt b on a.id_producent=b.id_producent
group by a.nazwa
order by ilosc desc, nazwa asc


--CCC3 [4 pkt]
--Znajdź zamówienie (jedno lub kilka, wystarczy wyświetlić zawartości kolumn: 
--id_zamowienie, data_zamowienia), które posiada najwięcej pozycji w tabeli koszyk.
--Proszę nie używać konstrukcji TOP 1 WITH TIES.
--Rozwiązanie:

select z.id_zamowienie,z.data_zamowienia, count(k.id_produkt)as ilosc
from zamowienie z join koszyk k on z.id_zamowienie=k.id_zamowienie
group by z.id_zamowienie,z.data_zamowienia
having count(k.id_produkt)=
(
select top 1 COUNT(k.id_produkt) as ilosc
from koszyk k
group by k.id_zamowienie
order by ilosc desc)
smętne wynurzenia słuchaczki pspi


--Imię i nazwisko:
--Data i godzina:
--Grupa laboratoryjna:
--Obowiązująca baza danych: sklep, http://fidytek.pl/bazy_danych/bd_skrypt_sql/sklep_mssql 

--Napisać instrukcje SQL (dla MS SQL Server) realizujące poniższe zadania.

--DDD1 [3 pkt]
--Znajdź producentów (nazwa producenta, identfikator producenta), dla których
--nazwa nie zaczyna się od spółgłowski.
--Wynik posortuj leksykograficznie po nazwie producenta.

--Rozwiązanie:
--DDD2 [3 pkt]
--Dla każdego statusu (tabela status kolumna nazwa), wyświetl informację 
--ile razy został on przyjęty (zobacz tabela zamowienie_status).
--Uwzględnij też te statusy, które ani razu nie zostały przyjęte.
--Wynik posortuj malejąco po oblicznej ilości, a dla takiej samej 
--ilości posortuj leksykograficznie po nazwie statusu.
--Rozwiązanie:



--DDD3 [4 pkt]
--Znajdź producenta (jednego lub kilku, wystaczy wyświetlić nazwę prodcenta), 
--który posiada największą ilość produktów w tabeli produkt.
--Proszę nie używać konstrukcji TOP 1 WITH TIES.
--Rozwiązanie:


