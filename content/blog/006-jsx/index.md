---
title: "#006 JSX" 
date: "2024-05-21T20:02:06.169Z"
description: "JSX jest skrótem od JavaScript XML. Jest to składnia rozszerzenia JavaScript, która daje możliwość wprowadzania HTML do kodu JavaScript. "
slug: 006-jsx
---

JSX jest skrótem od JavaScript XML. Jest to składnia rozszerzenia JavaScript, która daje możliwość wprowadzania HTML do kodu JavaScript. Jest to narzędzie do tworzenia interfejsów użytkownika, szczególnie w bibliotece React.js. 

### Podstawy składni JSX: Elementy, komponenty i właściwości
Elementy JSX przypominają HTML, komponenty to samodzielne jednostki kodu mogące zawierać własną logikę, a właściwości służą do przekazywania danych do tych komponentów.

##### 1. Elementy
Podstawowe jednostki budujące interfejs użytkownika to elementy JSX. Są analogiczne do elementów HTML, jednak oprócz typowych atrybutów mogą one obsługiwać eventy, takie jak onclick czy onkeydown.

**Charakterystyka:**
- **Składnia HTML:** JSX wygląda bardzo podobnie do HTML, co sprawia, że jest intuicyjny dla osób zaznajomionych z HTML.
- **Wartości dynamiczne:** Można w nich osadzać wyrażenia JavaScript za pomocą nawiasów klamrowych {}.

**Przykład 1: Prosty element JSX**

    const element = <h1>Witaj, świecie!</h1>;

**Przykład 2: Element z wartością dynamiczną**

    const name = "Jan";
    const elementWithVariable = <h1>Witaj, {name}!</h1>;

##### 2. Komponenty
Komponenty to zdynamizowane elementy, które mogą mieć swój stan (state) i w zależności od niego, mogą mieć różne zachowanie. Są to odpowiedniki JavaScriptowe obiektów, ich budowę zaczyna się  z dużej litery. Mogą być zdefiniowane jako funkcje lub klasy.

**Charakterystyka:**
- **Funkcyjne lub klasowe:** Komponenty mogą być funkcjami zwracającymi JSX lub klasami rozszerzającymi React.Component.
- **Własne elementy i logika:** Mogą zawierać własne elementy JSX, stan i metody.

**Przykład 1: Prosty element JSX**

    function Welcome(props) {
    return <h1>Witaj, {props.name}!</h1>;
    }

**Przykład 2: Komponent klasowy**

    class Welcome extends React.Component {
    render() {
        return <h1>Witaj, {this.props.name}!</h1>;
    }

##### 3. Właściwości
Właściwości (props) mogą być przekazywane do komponentów. Pozwala to na tworzenie skomplikowanych, ale modułowych i łatwych do testowania struktur. Są one przekazywane do komponentów jako atrybuty.

**Charakterystyka:**
- **Dane wejściowe:** Props są używane do przekazywania danych do komponentów.
- **Niezmienność:** Props są niezmienne w obrębie komponentu; komponent nie powinien ich zmieniać.

**Przykład 1: Przekazywanie pojedynczej właściwości**

    function Greeting(props) {
    return <h1>Witaj, {props.name}!</h1>;
    }

    const element = <Greeting name="Jan" />;

**Przykład 2: Przekazywanie wielu właściwości**

    function User(props) {
    return (
        <div>
        <h1>Witaj, {props.name}!</h1>
        <p>Masz {props.age} lat.</p>
        </div>
    );
    }

    const element = <User name="Jan" age={30} />;

### Babel.js
Składnia JSX nie jest wspierana bezpośrednio przez przeglądarki, więc potrzebne jest narzędzie, które „przetłumaczy” tą składnię na coś zrozumiałego dla przeglądarek. 

Babel jednak automatycznie nie działa na wszystkich skryptach na stronie. Kod, który ma być przez niego obsługiwany wymaga oznaczenia przy pomocy atrybutu type. Możemy użyć wartości text/babel lub text/jsx. Dzięki temu Babel bierze kod, transpiluje i przekazuje do przeglądarki.

**Proces transpile'owania JSX przez Babel:**
1. Pisanie kodu JSX: Programista pisze kod JSX, który wygląda jak HTML w środku JavaScript.
2. Transpilacja przez Babel: Babel konwertuje kod JSX na wywołania React.createElement, które są zrozumiałe dla przeglądarek.

**Przykład transpile'owania JSX:**

Kod JSX:

    const element = <h1>Hello, world!</h1>;

Po transpilacji przez Babel:

    const element = React.createElement('h1', null, 'Hello, world!');

**Przykłady użycia Babel z JSX:**

**Przykład 1:** Prosty kod JSX

Kod JSX (plik src/App.js):

    import React from 'react';

    const App = () => {
    return <h1>Hello, world!</h1>;
    };

    export default App;

Konfiguracja .babelrc:

    {
    "presets": ["@babel/preset-env", "@babel/preset-react"]
    }

Uruchomienie transpilacji:

    npx babel src --out-dir dist

**Przykład 2:** JSX z właściwościami i komponentami

Kod JSX (plik src/Welcome.js):

    import React from 'react';

    const Welcome = (props) => {
    return <h1>Welcome, {props.name}!</h1>;
    };

    export default Welcome;

Kod JSX (plik src/App.js):

    import React from 'react';
    import Welcome from './Welcome';

    const App = () => {
    return <Welcome name="John" />;
    };

    export default App;

Konfiguracja .babelrc pozostaje taka sama:

    {
    "presets": ["@babel/preset-env", "@babel/preset-react"]
    }

Uruchomienie transpilacji: 

    npx babel src --out-dir dist

**Babel** jest kluczowym narzędziem do pracy z JSX w projektach React. Pozwala na konwersję nowoczesnego kodu JavaScript i JSX do formy zrozumiałej przez przeglądarki, które mogą nie obsługiwać tych najnowszych funkcji natywnie. Dzięki Babel programiści mogą korzystać z najnowszych możliwości języka, zachowując kompatybilność z różnymi środowiskami wykonawczymi.
