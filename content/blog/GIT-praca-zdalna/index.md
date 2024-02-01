---
title: GIT - praca zdalna
date: "2024-01-20T16:49:06.169Z"
description: "Zdalne repozytoria i gałęzie. Pobieranie i wysyłanie zmian, gałęzie śledzące."
slug: GIT-praca-zdalna
---

### Wstęp do pracy zdalnej

Są trzy style pracy:
1. Scentralizowane Systemy Kontroli wersji
`svn commit` – dodaje zmiany

`svn checkout` – pobiera zmiany

2. Rozproszone Systemy Kontroli Wersji
`git push` – dodaje zmiany

`git fetch` – pobiera zmiany

3. Rozproszony styl pracy (GitHub)

Gdy wrzucimy swoje repozytorium na GitHuba, ktoś może sobie je skopiować (fork). Zostaje ono w chmurze. Żeby miał je u siebie wykonuje git clone. Tutaj też może pushować i fetchować do swojego sklonowanego, ale może też fetchować z oryginalnego. Jeśli chciałby dodać swoje zmiany do oryginalnego repozytorium może wysłać pull request. Jeśli założyciel oryginalnego repo uzna, że kod jest spoko, to może go zmergować do projektu.

### Praca zdalna
Najpierw trzeba uwierzytelnić swój komputer przez SSH. [Tutaj.](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

Aby połączyć repozytoria wpisujemy:

    git remote add origin <link ze strony>

Aby sklonować repozytorium z GitHuba, musimy otrzymać link ze strony GitHub. W terminalu wpisujemy:

    git clone <link ze strony>

Jeśli chcemy pracować na tym repo, musimy w terminalu wpisać

    cd [katalog]

Jeśli na danym repo chcemy zmienić nazwę użytkownika lub email to piszemy:

    git config --local user.name „...”

##### Zdalne repozytoria i gałęzie:
`git remote –v` – można podejrzeć dane repo

`git branch` – pokaże nam jakie są gałęzie. Wskaźnik HEAD pokazuje na master

`git fetch` – pobiera gałęzie ze zdalnego repo (checkout czy reset nie zadziała)

Jedyny sposób, żeby zmienić coś na gałęziach zdalnych to działania na lokalnych gałęziach i pushowanie tego do repo zdalnego.

##### Wypychanie zmian:

    git push [nazwa repo (origin)] [nazwa brancha, którego wypychamy]

Każdego brancha wypychamy osobno. 

##### Pobieranie zmian:

    git fetch [nazwa repo (origin)]
Zawsze warto najpierw sprawdzić graph. Pobiera wszystkie gałęzie. Po pobraniu sprawdzić status. Trzeba zmergować zmiany i gałąź główną. Będzie to ff.

Czas na mergowanie pozostałych gałęzi:

    git checkout –b [nazwa nowego brancha] [nazwa zdalnego brancha]
Najważniejsze żeby zawsze mieć na bieżąco główną gałąź projektu.

`git pull [nazwa repo, z którego pobieramy] [nazwa gałęzi z repo zdalnego, którą mergujemy]`– pobiera i merguje na raz, trzeba jednak stać na gałęzi, do ktorej chcemy mergować, bo dodaje tylko tą konkretną.

Przez `pull` może się pokazać problem z mergowaniem, bo zmiany się ze sobią kłócą i jesteśmy w stanie merging.

Można skonfigurować sobie parametr:

    git config --global pull.ff only
`pull.ff` może przyjąć trzy wartości:
1. true – zrobi merga zawsze
2. false – nie zrobi ff, nawet jeśli jest to możliwe, utworzy commita
3. only – zrobi merga tylko, jeśli jest to możliwe

##### Gałęzie śledzące:
`tracking` - informacja o tym, że jedna gałąź ma być zsynchronizowana z drugą. Dzięki temu wiemy, czy nasza gałąź jest aktualna, a także komendy `push` i `pull` możemy wykonywać bez żadnych parametrów.

`git branch -lavv` *(l – list, a – all, v – verbose, v – bardziej verbose)* – pokazuje listę branchy i ich połączeń ze zdalnym repo

**Jak włączyć tracking?**
1.  Przy pierwszym push
`git push –u [nazwa repo (origin)] [nazwa brancha, którego wypychamy]` – literka u od razu zapisze informacje o trackingu.

`git branch –u [nazwa bracha zdalnego] [nazwa nowego brancha]` – tracking po utworzeniu brancha

`git branch --unset-upstream [nazwa brancha, dla której usuwamy tracking]` – usuwanie śledzenia

2. Tworząc lokalną gałąź ze zdalnej gałęzi:
`git checkout –t [nazwa brancha, który chcemy trackować]` (t jak tracking)

**PORUSZANIE SIĘ W TERMINALU**

`cd` – otwórz folder

`cd ..` – do tyłu

`pwd` – ścieżka, gdzie jesteś

`ls` – wyświetli listę

`ls –la` – wyświetli dokładniej

`mkdir` – tworzy nowy folder

`git restore` – wraca poprzednią wersję plik