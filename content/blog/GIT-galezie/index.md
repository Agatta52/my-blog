---
title: GIT - wskaźniki, gałęzie, wycofywanie zmian
date: "2024-01-20T14:41:06.169Z"
description: "Wskaźniki GIT, rewizje, gałęzie: tworzenie, scalanie i konflikty, wycofywanie zmian: resetowanie, odwracanie rewizji"
---

### Wskaźniki GIT

##### Gałąź:
Zbór rewizji.

Wskaźniki w GITcie pokazują na ostatnią rewizję danej gałęzi. Wskaźniki możemy dodawać i przesuwać. Jeśli przesuniemy wskaźnik z ostatniej na przedostatnią rewizję to ostatnia zostaje sierotą. GIT może ją usunąć po 30 dniach jeśli nikt się do niej nie odwoła. Główna gałąź to **master**.

##### Wskaźnik HEAD:
Wskaźnik, którego nie można zmienić. Pokazuje gdzie aktualnie jesteś. Jeśli wskoczysz HEADem na przedostatnią rewizję, to ostatnia wskakuje do katalogu roboczego. Może wskazywać na rewizję poprzez gałąź albo konkretnie na rewizję, co nie jest normalne. Gdy wskazuje poprzez gałąź to przy commicie utworzysz nową rewizję na danej gałęzi. Jeśli jednak wskazuje bezpośrednio na rewizję to przy commicie utworzysz rewizję poza gałęzią i wtedy może ona zostać sierotą.

##### Skok do poprzedniej rewizji:

    git checkout <commit>

Podglądamy sobie graf i wybieramy, do której rewizji chcemy wrócić. Za pomocą powyższej komendy wybieramy rewizję, co poskutkuje tym, że w przestrzeniach pokaże się dokładnie taki stan jak był przy tamtym commicie. Tak samo będziemy to widzieć w folderze. 


**UWAGA** na zmiany. Kiedy je wprowadzimy to skok do kolejnej może się udać i zmiany zostaną zapisane. Jednak, gdy skok się nie uda, to GIT wyrzuci błąd. możemy wtedy utworzyć nową gałąź z nowymi zmianami dla tej rewizji środkowej lub możemy zmusić do skoku tracąc swoje zmiany:

    git checkout --force (lub –f) <commit>

Pozostajemy wtedy w stanie detouched head co oznacza, że HEAD pokazuje bezpośrednio na rewizję, a nie poprzez gałąź. Musimy przeskoczyć na gałąź wpisując zamiast nazwy pliku nazwę gałęzi. 


**UWAGA** komenda `checkout` przy powrocie do stanu rewizji nie usuwa nieśledzonych plików. Jeśli chcemy usunąć to wpisujemy:

`git clean –nd` – pokazuje się lista plików do usunięcia

`git clean –fd` – usuwają się pliki z listy

##### Arytmetyka wskaźników:
Wskaźniki commitów pokazują na swoich rodziców. Można więc skakać po rewizjach bez podawania identyfikatora.

`git checkout head~2` – jest to skok o dwie rewizje do tyłu od wskaźnika HEAD, można skakać nie tylko przez HEAD


Do przodu nie skoczymy. Można sobie ustawić wskaźnik w miejscu, w którym chcemy, żeby móc tam skakać szybciej.


**WAŻNE** na koniec pracy zawsze wracamy na branch (gałąź).

### GAŁĘZIE

##### Tworzenie nowej gałęzi:
`git branch [nazwa_brancha] *opcjonalnie id commita`, ale jak nie to będzie head

**Nazwy gałęzi** – warto prefixować swoje gałęzie np.:

`feature/` – gałęzie, które wprowadzają do kodu nową funkcjonalność lub refaktorują istniejący kod

`bugfix/` – naprawiają błędy zgłoszone przez klientów lub testerów

Nazwa brancha powinna określać co robimy na danym branchu. Muszą być unikalne.

Teraz żeby przejść do brancha trzeba przesunąć head na nowego brancha za pomocą git checkout.

`git checkout –b [nazwa_brancha] master~` - Utworzy od razu brancha i przeniesie head tam gdzie trzeba. Master tylda pokazuje, że chcemy jeden do tyłu od mastera utworzyć tą gałąź (można dowolnie).

##### Scalanie gałęzi:

    git merge <commit>
1. Najpierw upewniamy się, że nie ma różnic w plikach w przestrzeniach. (`git status`)
2. Ustawiamy head na gałąź do której chcemy scalić. (`git checkout master`)
3. `git merge [nazwa gałęzi]`
Git szuka wspólnego rodzica i robi 3way merge’a, czyli sprawdza różnice pomiędzy trzema plikami, jeśli było więcej zmian pomiędzy mergowanymi. Jeśli plik , do którego chcemy mergować jest rodzicem to robimy Fast-forward merge.

**Ważne:** `ff merge` tworzy nowego commita na gałęzi, do której mergujemy (commit z przyłączanej gałęzi się przesuwa na aktualną). Jeśli chcemy tego uniknąć robimy `git merge --no-ff [nazwa gałęzi]`.

##### Rozwiązywanie konfliktów:
Kiedy robimy merga i nastąpi konflikt, to jesteśmy w stanie merging. Nie możemy wtedy robić niczego innego, co nie byłoby związane z tym mergem.

`git merge --abort` – przerywa merga, odblokowuje

W stanie merging możemy wycinać i przeklejać normalnie w treści pliku tak, aby zmergować ręcznie zmiany. Następnie usuwamy markery, czyli nowe znaczki ze strzałkami i znakami równości.  Na koniec zapisujemy plik i zamykamy. Następnie aby dodać zmiany: `git add <plik>` i później `git merge --continue`. Git chce utworzyć commit i pokazuje okienko na wpisanie wiadomości. Informacje są zakomentowane. warto odkomentować te o konflikcie żeby inny użytkownik mógł zobaczyć z czego powstał commit.

Kiedy wyskoczy nam konflikt, którego GIT nie może oznaczyć to w stanie merging zmieniamy dane w plikach (ewentualnie usuwamy niepotrzebne) i sprawdzamy status. Dodajemy pliki add i wtedy merge z continue.

##### Wypisywanie, usuwanie i  zmiana nazwy gałęzi:
`git branch` bez parametrów pokazuje całą listę branchy

`git branch --list` z parametrem może pokazać konkretne branche np. z wskazanym początkiem nazwy

`git branch --merged master` – pokazuje wszystkie domergowane branche

`git branch --no-merged` – pokazuje niedomergowane

`git branch –m [stara nazwa brancha] [nowa nazwa brancha]` – zmienia nazwę

`git branch –d [nazwa brancha]` – usuwa branche, usuwamy domergowane, bo inaczej znikną nam commity

`git ref log` – pokazuje wszelkie zmiany

### WYCOFYWANIE ZMIAN

##### Resetowanie gałęzi:
`git reset <commit>` - przesuwa wszystkie obecne wskaźniki, czyli HeAD i nazwę gałęzi

`git reset --hard` – przenosi zmiany do poczekalni i katalogu roboczego, podobnie jak checkout, ale kasuje obecne tam inne pliki

`git reset --mixed` – przenosi zmiany tylko do poczekalni

`git reset --soft` – nie przenosi zmian do innych przestrzeni

Możemy resetować tylko takie gałęzie, które są w naszym lokalnym repozytorium, czyli nie zostały wysłane dalej.

##### Odwracanie rewizji:
`git revert` – odwraca zmiany z wskazanych rewizji tworząc nowy commit

` git revert –n` – tworzy revers, ale nie commituje od razu. 

Jesteśmy w stannie reverting. Sprawdzamy `git status` i jak jest ok to `--continue`. Generuje się wiadomość, ale z opisem jakbyśmy revertowali tylko ostatni commit. Warto to zmienić. Żeby sobie sprawdzić info to trzeba wejść w folder i odpalić nowego git basha, wpisać `git show` i mamy dane dotyczące ostatniego commita.
Wycofujemy od najnowszych, czyli np. najpierw `head` a potem `head~`.
