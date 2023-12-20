---
title: Angielski - 2. Databases
date: "2023-12-13T17:07:03.284Z"
description: "What is a database and DBMS?"
---
### What is a database and DBMS?

Database can be defined as a repository for storing data or information which is interrelated. It means that parts of data within the databases associated with other parts in it. For example data unpurchased products must be related to customers who bought them. 

**Organized.** It means that data is usually arranged on the basis of application requirements. Data with the same properties is for example grouped together. 

**Accessible and exploitable.** It means that data must be available for quick data retrieval by third party applications using a variety of programming languages such as Java. It is the role of database administrator DBA to operate, secure, monitor and maintain the database whereas data administrator is a none technical position responsible for defining and implementing consistent principles connected with data such as Setting data standards and data definitions that apply to all the databases in an organization. 

The simplest type of database is the set of flat files stored on a computer disc. A simple database usually consist of tables that are managed by a database management system DBMS used as an interface between a database and its users another programs which access the data base. DBMS helps to define, create, query, update and administrate database. All database files are integrated into one system. So there are less redundancies and data management is more efficient. The DBMS can be accessed by the database administrator for example through the web into face or graphical user interface GUI. DBMS vendors such as Oracle, Microsoft or PostgreSQL provide various drivers for different programming languages and platforms which enable access to database engine. The main functionalities and objectives for DBMS are the following: 
- Data availability – it refers to making data available to multiple or concurrent users. Such access is controlled by the DBMS to avoid conflicts and deadlocks.
- Data manipulation – this includes altereration of stored data and retrieval of data.
- Data integrity – it refers to the assumption that data available in the database is reliable and correct without any inconsistences in data types, legal values, format key uniqueness and referential integrity.
- Data security – it is connected with preventing an authorized users from accessing the database 

In order to ensure security for the database DBMS uses: 
- Encryption – it refers to converting data in the database to format which cannot be deciphered  by the users who make an attempt to view data
- Authentication – it refers to identification of a user trying to access the database by verifying his username and password.
- Authorization – this is a set of rules that DBAs set up to specify access levels that individuals or group of users can have.
- Data backup  and recovery – this means that DBMS provides ways to recover a database if there is a risk of data loss. The easiest way to do this is to make regular backups of data or replicate database from master server to slave server.

#### Słowniczek pojęć
|      |      |
| :--- | :--- |
access control mechanism | mechanizm kontroli dostępu
access level | poziom dostępu
accessible | dostępny
accessible remotely |  dostępny zdalnie
accuracy | dokładność, precyzyjność, trafność
to administer data base | administrować bazą danych
autoration| zmiana 
to apply to something | odnosić się do czegoś, dotyczyć czegoś, mieć zastosowanie do czegoś
to arrange | organizować, porządkować
associativeentity | encje asocjacyjna
assumption | założenie
attribute | atrybut
authentication | uwierzytelnienie, poświadczenie
authorization | upoważnienie, uprawnienie, autoryzacja
backup | kopia zapasowa
by and large | ogólnie rzecz biorąc
central processing units(CPU) | procesor
cloud computing platform | platforma oparta a chmurze obliczeniowej
cloudbased DBMS | system zarządzania baza danych w chmurze
collection of requirements | zbiór wymagań
column | kolumna
conceptual data      base model | konceptualny model bazy danych
concurrent access | równoczesny dostęp
consistency | spójność
consistent | spójny
constrate | ograniczenie
constrates | więzy
to convert something to something | przekształcać coś w coś
crow’s foot | kurza stopka
data administrator | administrator danych
data availability | dostępność danych
data backup | kopia zapasowa danych
data integrity  | integralność danych
data loading | ładowanie danych
data loss | utrata danych
data management | zarządzanie danymi
data manipulation | operowanie, manipulowanie danymi
data migration | migracja danych
data model | model danych
data need | zapotrzebowanie na dane
data recovery | odzyskiwanie danych
data retrieval | wyszukiwanie danych
data security | bezpieczeństwo danych
data standards | standardy związane z bazami danych
data storage | przechowywanie danych
data type | typ danych, kopia zapasowa danych
database administrator (DBA) | administrator baz danych
database as a service DMAAS | baza danych jako usługa
database design | projekt bazy danych
database designer | projektant bazy danych
data base engine | silnik bazy danych
database management system DBMS | system zarządzania bazą danych
data base object | obiekt bazodanowy
data base query language | język zapytań do bazy danych
deadlock | zakleszczenie, blokada wzajemna
to decipher|rozszyfrować, odcyfrować
disk space | przestrzeń dyskowa
distributed DBMS | system zarządzania rozproszoną bazą danych
domain integrity constrains | więzy integralności domeny
driver | sterownik
embeddedts DBMS | system zarządzania wbudowaną bazą danych
to enable | umożliwiać
encryption | szyfrowanie
end user | użytkownik końcowy
to ensure | zapewniać
entity integrity constrains | więzy integralności encji
entityrelationship diagram ERD | diagram związków encji
entity | encja
ETL ExtractTransformLoadprocess | proces ETL ekstrakcji, transformacji ładowania
evaluation | ocean
executiontime | czas wykonania
exploitable | nadający się do wykorzystania
field | pole
flat file | plik płaski
foreign key | klucz obcy
graphical user interface (GUI) | graficzny interfejs użytkownika
inconsistency | niespójność
information need | potrzeba informacyjna
inhurant | nieodłączny
in memory DBMS | system zarządzania bazą danych inmemory
integrity | integralność
integrity constreins | więzy integralności
interface| interfejs
interrelated | wzajemnie powiązany
intra query paralelism | wykonanie pojedynczego zapytania przy równoległym użyciu kilku procesów
to involve | dotyczyć obejmować
key uniqeness | unikalność na poziomie kluczy
to lease | wydzierżawić
legal value | dozwolona wartość
logical database model | logiczny model bazy danych
to maintain | utrzymywać
maintenance | utrzymanie
to make an attempt | podjąćpróbę
manycore central processingunits CPU | procesor wielordzeniowy
many to many relationship | relacja wiele do wielu
master server | serwer główny
multimedia format | format multimedialny
multiple concurrent users | wielu równoczesnych użytkowników
normalized | znormalizowany
notation | notacja
object oriented database management system OODBMS | obiektowy system zarządzania bazą danych
object oriented programming language | ojetkowyjezyk programowania
object relational database management system | ORDBMS | obiektowo relacyjny system zarządzania bazą danych
one to many relationship | relacja jeden do wielu
one to one relationship | relacja jeden do jednego
to operate | obsługiwać
performance tuning |dostrajanie wydajności
performance | wydajność
physical database model | fizyczny model bazy danych
to prevent someone from doing something | powstrzymywać kogoś przed czymś
primary key | klucz główny
principle | zasada
programming language | język programowania
to provide | dostarczać, zapewniać
to purchase | nabyć, zakupić
query | zapytanie
to querydatabase | odpytywać bazę danych
query language | język zapytań
RAM random access memory | pamięć o dostępie swobodnych, pamięć RAM
record | rekord, zapis
redundancy | nadmiarowość, redundancja 
referential integrity contrains | więzy integralności referencyjnej
referential integrity | integralność referencyjna
relational database management system RDBMS | system zarządzania relacyjną bazą danych
relational model | model relacyjny
relationship | relacja, związek
release to production environment | uruchomienie w środowisku produkcyjnym
to replicate | powielać, replikować
repository | repozytorium
requirements analsis | analiza wymagań
to resolve into something | rozkładać na coś
retrieval of information | wyszukiwanie informacji
row | wiersz
security constrains | ograniczenie ze względów bezpieczeństwa
service provider | dostawca usługi
slave server |serwer zapasowy
to set standards | wyznaczać standardy
sequel  structure query language | strukturalny język zapytań
SSD solid stagedrive | dysk SSD półprzewodnikowy
to store| przechowywać, składować
stored data | przechowywany, składowane dane
tablespace | obszar tabeli
third party application | aplikacja producenta zewnętrznego (dostawcy)
triple | krotka
UML unified modeling language | zunifikowany język modelowania
unauthorized user | nieautoryzowany, nieuprawniony użytkownik
unique identifier | unikalny identyfikator
upgrade | aktualizacja
vendor | dostawca
web interface | interfejs WWW
whereas | podczas, gdy
with respect to something | odnośnie do czegoś