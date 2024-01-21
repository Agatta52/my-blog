---
title: JavaScript - pętle i tablice
date: "2024-01-21T11:54:08.169Z"
description: "Pętle: for, while, do while, for of oraz tablice"
---

### Pętle

##### Pętla for
**For** – kiedy wiemy ile razy ma się wykonać

    for (let i=0; jak długo; plus jeden)
    const colors = ['green', 'blue', 'red', 'purple', 'yellow']
    for (let i=0; i < colors.length; i++) {
        console.log(colors[i]);
    }

##### Pętla while
**While** – kiedy nie wiemy ile razy ma się wykonać

    let i = 0

    while (i < 5) {
        i++
        console.log(i);
    }

Jeśli chcemy wyświetlić ostatni wynik, to console.loga dajemy poza pętle, wtedy nie wyświetla każdej iteracji.

##### Pętla do while
**Do ... while** – odwrotność pętli while

    do {
        i++
        console.log(i)
    } while (i < 3)

##### Pętla for of
**For of** – korzystamy, kiedy chcemy dotrzeć do każdego indeksu (for wtedy, gdy chcemy dotrzeć do konkretnego indeksu), lepsza opcja do tablic.

`for (stała nazwa_stałej of nazwa_tablicy)`

    const numbers = [1, 2, 3, 4, 5]
    for (const number of numbers) {
        console.log(number);
    }
 

### Tablice
    const arr = [1, ‘hdh’, 35]

##### Metody
>destrukcyjna – zmienia strukturę oryginalnego obiektu

>niedestrukcyjna – wtedy trzeba sobie utworzyć nową tablicę, żeby zachować zmianę

**Wycinanie/dodawanie elementów:**

`.unshift ()` - dodaje elementy na początku tablicy (raczej się nie używa)

`.shift ()` – usuwa pierwszy element z indexem 0 (raczej się nie używa)

`.push ()` – metoda destrukcyjna, dodaje elementy na końcu tablicy, można podać kilka parametrów

`.pop ()` – metoda destrukcyjna, usuwa ostatni element z tablicy

`.slice ()` – metoda niedestrukcyjna, wycina (pobiera) elementy, pierwszy argument – indeks elementu, od którego wycinamy (włącznie), drugi argument – indeks elementu, do którego wycinamy (ale bez tego elementu).

`splice()` – metoda destrukcyjna, pierwszy argument – indeks elementu, od którego wycinamy (włącznie),drugi argument – ilość elementów, które wycinamy,  każdy kolejny argument – nowy element, który chcemy dodać do tablicy w miejsce wyciętego.

**Łączenie tablic:**

`.concat ()` – łączy tablice, metoda niedestrukcyjna

    const numbers = [1, 2, 3, 4, 5]
    const abc = ['a', 'b', 'c']
    const newAbc = numbers.concat(abc)
    console.log(newAbc);

`...` – spread – zwraca osobne stringi (rozsmarowywuje) i łączy tak samo jak concat, jest bardziej czytelny

    const drinks = ['pepsi', 'kawa', 'sok']
    const meals = ['schabowy', 'spaghetti', 'zupa']
    const menu = [...drinks, ...meals]
    console.log(menu);

**Pozostałe metody:**

`.filter (callback)` – zwraca elementy spełniające nasze kryteria określone w funkcji 

    const numbers = [0, 23, 48, 175, 2, 34, 11]
    function number(x) {
        return x % 2 === 0
    }
    console.log(numbers.filter(number));

`.includes ()` – sprawdza, czy element zawiera się w tablicy

`.indexOf ()` – pokazuje numer indexu danego elementu, UWAGA jeśli nie ma takiego elementu to wyświetli -1

`.split ()` – oddziela elementy po znaku jaki wpiszemy

**.map vs .forEach**

`.map` – zwraca nową tablicę

`.forEach` – nie zwraca niczego, wykonuje tylko kod na danej tablicy

`.map` – działa podobnie do pętli

>*Callback* to funkcja, którą przekazujemy jako argument (odwołanie) do innej funkcji.

`.map (callback)` – działa podobnie do pętli, w nawiasie trzeba podać nazwę jakiejś funkcji, zwraca NOWĄ tablicę

    const numbers = [1, 5, 13, 26, 48]
    const newNumbers = numbers.map(number => number*5)
    console.log(newNumbers);

`.forEach` – funkcja pętli dla każdego elementu w tablicy

    const numbers = [0, 23, 48, 175, 2, 34, 11]
    numbers.forEach (number => console.log(number * 5))
