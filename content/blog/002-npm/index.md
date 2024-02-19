---
title: "#002 NPM vs NPX" 
date: "2024-02-19T18:42:06.169Z"
description: "Czym jest NPM i czym różni się od NPX?"
slug: 002-npm
---

### NPM (node package manager)
> [npmjs.com](https://www.npmjs.com/)
Narzędzie, które umożliwia instalację, usuwanie i aktualizację bibliotek w projektach. To repozytorium online dla open-source’owych projektów node.js, menadżer paczek. Nie tylko do Reacta. Do plików jsowych, ale i innych bibliotek jsowych jak np. Angular. Paczki można instalować globalnie lub lokalnie.

`npm init` – tworzy plik o nazwie *package.json* – plik konfiguracyjny

Jak odpalić komendę? W pliku *package.json* są skrypty, których można używać. Wystarczy w terminalu wpisać npm run nazwa_komendy.

`npm install nazwa_biblioteki` – pobiera moduł

`npm install nazwa_biblioteki@wersja` – pobiera moduł z wybraną wersją

Wtedy tworzy się katalog lokalny *node_modules*. Są tu niezbędne pliki do uruchomienia modułu.

Inne komendy:
`npm update`
`npm remove`

##### Zależności
Możemy dopisać zależności do naszego pliku package.json za pomocą:

`npm install nazwa_biblioteki --save` - zależności **produkcyjne**, niezbędne do działania aplikacji po stronie użytkownika

`npm install nazwa_biblioteki --save-dev` - zależności **deweloperskie**, przyspieszają lub ułatwiają pracę programisty, ale przy użyciu komendy `mpn run build` te paczki nie będą brane pod uwagę

W *package.json* mamy informację z jakich modułów korzystaliśmy. Jest to istotne w momencie, gdy ktoś pobierze program. Nie będzie pobierał go wraz z plikiem n*ode_modules*, bo jest on za ciężki. Ale po pobraniu wystarczy, że wpisze `npm install` i odpowiednie moduły pobiorą się same.

##### Odpalanie paczki

Żeby odpalić skrypt używamy:
   
    npm run nazwa_biblioteki

Tworzymy plik *app.js*, w którym będziemy korzystać z zainstalowanego modułu. Żeby skorzystać z tego modułu należy wpisać w pliku:

    var hw = require(‘nazwa modułu’);
    console.log(hw());

I program uruchamia się.

### NPX 
- Umożliwia uruchomienie biblioteki bez jej wcześniejszej instalacji. przydaje się kiedy jednorazowo chcemy skorzystać z biblioteki. 
- Można też odpalić bibliotekę, która jest już zainstalowana lokalnie.

        npx nazwa_paczki

- Umożliwia odpalenie repozytyria priosto z GitHub.

        npx https://gist.github.com/..../.......

- Za pomocą npx można również przetestować różne wersje paczek.
