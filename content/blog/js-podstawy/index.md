---
title: JavaScript - podstawy
date: "2024-01-21T11:17:32.169Z"
description: "JS - zmienne, typy danych, operatory"
---

### Wstęp
Kod JS umieszczamy zawsze na końcu znacznika body.

    <script src=”./script.js”></script>
    

> Aby używać **JavaScript Code Snippets**, trzeba wpisać skrót i kliknąć tab.

##### Komentarz
    ctrl + /

`//  ...`  lub jak w CSS `/* ... */`

##### Konsola 
F12

`clg`  -> `console.log ();`

Sprawdza skrypt, pokazuje czy jest błąd.

### Zmienne

`const` – zmienna, której nie można już zmienić (stała)

    const name = ‘Lisa’

`let` – zmienna, która może się zmienniać

    let age = 23

`let color` – tutaj utworzyliśmy zmienną bez wartości. Później będziemy mogli sobie tą wartość przypisać.

`var` (stara opcja, lepiej nie używać)

##### Template string
`console.log (‘blabla ’ + zmienna + ‘blabla’)` – tak nie robimy

`console.log {'blabla ${zmienna} blabla'}` – samo dodaje spacje, tutaj zamiast apostrofu jest to co przy falce pod esc - grawis

### Typy danych
`console.log (typeof zmienna)` – powie nam jaki to typ

##### String
string – tekst, zawsze w " ",  ' ' ` ` lub grawis (grawisa używamy tylko kiedy chcemy wprowadzić zmienną)

> Metody w google: JavaScript MDN string

`zmienna.length` – pokazuje ile jest znaków

`zmienna.toUpperCase()`

można przypisywać metody do zmiennych np.

    const msg  ‘test’
    const newMsg = msg.toUpperCase()
`zmienna.toLocal.....` - można lokalnie dla danego języka/kraju przypisać wartości np. wyświetlanie daty

`zmienna.charAt(index)` – odwołanie do konkretnego znaku

można łączyć metody:

`zmienna.charAt(0).toUpperCase().slice(1)` – te metody zrobią nam stringa z wielkiej litery,

dla tablicy:

    ${colors[i].charAt(0).toUpperCase() + colors[i].slice(1)}

##### Number
`.toFixed()` – zaokrągla do () miejsc po przecinku

`parseInt(zmienna)` – przeistacza stringa w number

##### Boolean

true or false – do if else

Uwaga! zawsze zwracają false: false, undefined, null, 0, NaN, ‘’(pusty string, bez znaku spacji)

`Null` i `undefined` oznacza to samo. Null przypisujemy sami, undefined zwraca nam konsola.

### Operatory 
##### Operatory arytmetyczne
`+, -, *, /`

`%`- modulo, reszta z dzielenia

`++` - inkrementacja, podbija wartość o jeden 

`--` - dekrementacja, zmniejsza o jeden

##### Operatory przypisania
`=` - przypisujemy to co jest po prawej do tego co jest po lewej

`+= , -=, *=, /=` - zapis skrócony

np. `x = x+y` to to samo co `x+=y`

##### Operatory porównania
`==` - porównuje zawartość

`===` - porównuje zawartość i typ danych

`!=` - odwrócenie, odpowiednik `==`

`!==` - odwrócenie, odpowiednik `===`

`>, <, >=, <=`

wynik: `true` or `false`

##### Operatory logiczne
`&&` - i

`||` - lub

`!` – zaprzeczenie 
