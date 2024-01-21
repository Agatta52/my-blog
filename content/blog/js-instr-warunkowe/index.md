---
title: JavaScript - instrukcje warunkowe
date: "2024-01-21T11:19:56.169Z"
description: "If , else if &  else, switch, operator warunkowy"
---
### Instrukcje warunkowe
##### If, else if & else
    const pass = ’ss5v15v1vfvf4ffss’

    if (pass.length > 10) {
        console.log (‘Masz dobre hasło’);
    } else {
        console.log (‘masz za krótkie hasło’);
    }

Można zagnieżdżać ify.

    if (pass.length > 10 && pass.includes('!')) {
        console.log ('Masz rewelacyjne hasło');
    } else if (pass.length > 10) {
        console.log ('masz dobre hasło');
    } else {
        console.log ('masz za krótkie hasło');
    }

##### Switch
> Switch szukać MDN w google.

    const day = 'środa'
    switch (day) {
        case 'poniedziałek' :
            console.log('Dziś jest poniedziałek');
            break
        case 'wtorek' :
            console.log('Dziś jest wtorek');
            break
        case 'środa' :
            console.log('Dziś jest środa');
            break
        case 'czwartek' :
            console.log('Dziś jest czwartek');
            break
        case 'piątek' :
            console.log('Dziś jest piątek');
            break
        default:
            console.log('Weekend!');
    }

`break` - kończy działanie

`default` - domyślna odpowiedź, gdy input nie pasuje do przewidywanych

##### Operator warunkowy
wartość ? TRUE : FALSE

np.:

    const x = '5'

    const newX = x > 20 ? `${x} > 20` : `${x} < 20`
    console.log(newX);

    -------

    newCars.length > 3 ? console.log('Jest OK') : console.log('Nie jest OK')

    -------

    const isLoggedIn = true
    function loggedIn() {
        console.log('Użytkownik jest zalogowany!');
    }
    function loggedOut() {
        console.log('Użytkownik nie jest zalogowany!');
    }
    isLoggedIn ? loggedIn() : loggedOut()
