---
title: JavaScript - funkcje
date: "2024-02-06T20:41:06.169Z"
description: "Deklaracje funkcji, wyrażenie funkcyjne, funkcja z argumentami, anonimowa, strzałkowa"
slug: js-funkcje
---

### FUNKCJE

##### Deklaracja funkcji:
    function test(params) {
        console.log('cześć');
    }
    test ()
Na koniec trzeba wywołać funkcję, jak powyżej: `test ()`

Deklaracja funkcji podlega hoistingowi, czyli wypycha tą funkcję na górę, dlatego stosujemy wyrażenie funkcyjne, żeby wszystko czytane było od góry do dołu. Jeszcze lepsza opcja to funkcja strzałkowa.

##### Wyrażenie funkcyjne:
    const helloWorld = function () {
        console.log('cześć! 123');
    }
    helloWorld () 

##### Funkcja z argumentami:
**Parametr** = **argument**, ale parametr zapisujemy w funkcji, a argument przy wywoływaniu funkcji.

    function add(parametr) {
        console.log('Podany argument to:' + parametr);    
    }
    add('test')
---

    function add(x, y) {
        return(x + y);    
    }
    add(5, 3)
>UWAGA częściej zamiast console.loga używamy ‘`return`’. Tak samo jak `map()` zwraca nam nową tablicę, z którą możemy pracować, tak samo ‘`return`’ zwraca nam wartość, z której możemy w przyszłości skorzystać. Return kończy działanie funkcji.

##### Funkcja anonimowa:
    const heading = document.querySelector('h1')
    heading.addEventListener('click', function()) {
        console.log('Kliknięto mnie!');
    }

Ale lepiej zrobić o tak:

    function test() {
        console.log('Kliknięto mnie!');
    }
Lepiej nie używać funkcji anonimowych, bo nie można się później do nich odwołać.

##### Funkcja strzałkowa:
Jeżeli mamy jeden parametr, to nie trzeba pisać nawiasów. Jeżeli mamy jedno zadanie dla funkcji, nie trzeba pisać nawiasów klamrowych, chyba, że będzie `return`.

    const arrowFunction = () => {}
Jak zapisać funkcję w sposób strzałkowy:
 
    function test(name) {
        console.log(`Mam na imię ${name}`);
    }
    test ('Agata')

    const test2 = name1 => console.log(`Mam na imię ${name1}`);
    test2('Lisa')

Można wpisywać więcej parametrów:

    const test4 = (name, age) => console.log(name, age);
    test4('xxx', 25)

Na tablicach:

    const days = ['poniedziałek', 'wtorek', 'środa']
    const days2 = days.forEach(day => console.log(day))

##### Domyślne parametry funkcji:
>nfn (rozszerzenie JS ES6)– tworzy nam szablon funkcji strzałkowej

Możemy przypisać pisać takie wartości za pomocą =

    const hello = (name = 'drogi uzytkowniku') => {
        console.log(`Cześć ${name}, jak się masz?`);
    }
    hello()

##### Operator REST 
(podobny do spread, ale nie do tablic, lecz funkcji)

Można dzięki niemu utworzyć tablicę z podanych elementów i pracować na nich jak na tablicy.

    const numbers = (x, y, ...z) => {
        console.log(x, y, z)

        console.log(z.map(el => el *2))
        console.log(x+y);
    }
    numbers(13, 468, 25, 25, 654, 2, 15, 566, 54, 'ds', true)

##### Zakresy:
Są zakresy globalne i lokalne. Kiedy przypiszemy sobie do zmiennej jakąś wartość w kodzie to jest to zakres globalny. Możemy przypisywać wartości wewnątrz funkcji (nawet dla takiej samej zmiennej) i wtedy zakres jest lokalny. Z wnętrza funkcji mamy dostęp do zmiennych z zakresu globalnego, ale z poza funkcji nie dostaniemy się do zmiennej w zakresie lokalnym. Są takie poziomy.

##### Pobieranie elementów na stronie:
Stare, ale wspierają żywe kolekcje:

    const test = document.getElementsById(‘item’)
    const test = document.getElementsByTagName(‘li’)
    const test = document.getElementsByClassName(‘test’)
    console.log(test);

Nowe, ale nie wspierają żywych kolekcji:

    const ulList = document.querySelector(‘ul’)
    console.log(ulList);

skrót klawiszowy qs

    const test = document.querySelectorAll(‘#item’)
    console.log(test);

Skrót klawiszowy qsa, tutaj selektory zapisujemy jak w CSS.

Można odwołać się potem do `ulList` zamiast do `document`.
>Żywe kolekcje, czyli kiedy dodajemy np. elementy z listy już w JS na bieżąco. Nie ma ich w HTML.