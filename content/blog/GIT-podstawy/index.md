---
title: GIT - podstawy
date: "2024-01-08T21:23:06.169Z"
description: "Podstawy GITa - Systemu Kontroli Wersji"
---

### Podstawy

##### UWAGA
Jak wejdziemy do VI (edytor) to klikamy esc i wpisujemy q!

Warto sobie wpisać:

    git config --global core.editor nano

##### Poziomy GITa:
1) System  –  dla maszyny
2) Global – dla użytkownika
3) Local – dla projektu

##### Konfiguracja danych:
    git config --global user.name „...”
    git config --global user.email „...”
    git config -- global --list – pokazuje wszystkie zmiany

###### Inicjalizacja repozytorium:
    git init

##### Przestrzenie GIT

![przestrzenie GIT](GIT.jpg)


##### Status:
    git status
...pokazuje różnice pomiędzy przestrzeniami

##### Dodawanie zmian:
    git add [nazwa pliku] 
...dodaje do katalogu roboczego

Dodajemy po nazwie. Można wpisać pierwszą literę i git podpowiada. Kiedy nie jest pewien trzeba dopisać i podpowie końcówkę. Kilku plików nie oddzielamy przecinkiem ani niczym tylko spacja. Jeśli kilka plików zaczyna się na tą samą literę (np. M), można wpisać M*. * to ciąg dowolnych znaków. Działa to do wszystkich untracked, ale nie zadziała dla usuniętych plików. Jeśli chcemy wszystko dodać to wtedy git add –A, gdzie A oznacza all.


##### Nowa rewizja:
    git commit –m „tu piszemy wiadomość”

Pierwszy commit to initial commit.

##### Rewizja:
    git show
bez podania identyfikatora (skrótu) wyświetli aktualną rewizję
    Clear
czyszczenie terminala

##### Katalogi w GITcie:
    git status [nazwa katalogu]/ - pokazuje pliki w danym katalogu
    git add [nazwa katalogu]/* - dodaje wszystkie pliki
    git commit [nazwa katalogu]

##### Usuwanie plików:
Najpierw usuwamy plik z katalogu i wtedy przy statusie widać, że zniknęło. Wtedy robimy `add` i dodaje się usunięcie do poczekalni. Następnie `commit` i zacommitowaliśmy usunięcie pliku co tworzy nam kolejną rewizję.

##### Podgląd grafu rewizji:
`git log` – pokazuje listę rewizji (jeśli mamy jedną gałąź) i opisy

`git log --graph` – pokazuje listę rewizji i opisy

`git log --graph --oneline` – pokazuje skrócone identyfikatory i wiadomości

Powyższe pokazują tylko aktualne gałęzie.

`git log --graph --oneline --all` – pokazuje wszystko

>Uwaga! Zazwyczaj piszemy parametr z jedną kreseczką przed jeśli jest skrócony do jednej literki. Nie każdy parametr można skrócić do jednej literki – wtedy piszemy przed słówkiem dwie kreseczki --.

##### Tworzenie aliasu dla polecenia:
    git config [poziom] alias.[nazwa] „[nazwa polecenia]”
    np. git config --global alias.gr „log --graph --oneline –all”
Potem piszemy po prostu `git gr` i działa.

##### Podgląd różnic w plikach:
`git diff` – porównanie pomiędzy katalogiem roboczym i poczekalnią

`git diff --staged` – porównanie pomiędzy poczekalnią i aktualnym commitem

`git diff <commit>` – porównanie pomiędzy katalogiem roboczym i wskazanym commitem. Teoretycznie można wpisać git diff HEAD, żeby wzięło aktualną rewizję

##### Wycofywanie zmian z poczekalni:
`git reset <plik>` - resetuje plik w poczekalni do aktualnej rewizji

##### Przywracanie pliku:
`git checkout <commit> <file>` - jako commit można wpisać head, jest to aktualna rewizja

Przywracanie pliku polega na przywróceniu do katalogu roboczego jakiejś rewizji. Uwaga! Skasuje wersję pliku, którą trzymasz w poczekalni i w katalogu roboczym.

##### Dodawanie części zmian:
    git add --patch (lub –p) <plik>
Polecenie pokaże jakie zmiany wystąpiły w kodzie. Zapyta co z nimi zrobić: stage this hunk. Gdy klikniemy „?”, to pokaże co oznaczają skróty. 

Gdy klikniemy edit odpali się edytor. Możemy usunąć linijki, których nie chcemy zacommitować.

##### Plik .gitignore:
Jest to taki plik, którego nie chcemy śledzić. Musimy usunąć go z untracked.

Tworzymy więc plik za pomocą touch .gitignore . Taki pusty plik pojawia nam się w folderze. Następnie do pustego pliku wklejamy wszystkie ścieżki do plików, które chcemy ignorować. Jeśli chcemy ignorować wszystkie pliki z danym rozszerzeniem to możemy wpisać *.cdr/*.pdf itd. Pliki wpisujemy w kolejnych linijkach. Jeśli chcemy ignorować całą zawartość jakiegoś folderu to wpisujemy [nazwa folderu]/ . Dodajemy plik .gitignore za pomocą add, potem commitujemy i działa.

Gotowy plik .gitignore można pobrać z internetu. Wystarczy przekopiować zawartość do naszego pliku.
