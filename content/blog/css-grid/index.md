---
title: "CSS - Grid" 
date: "2024-06-23T13:14:06.169Z"
description: "Krótki przewoodnik po GRID, czyli jak ustawić siatlkę w CSS"
slug: css-grid
---

### Podstawy CSS Grid
Aby rozpocząć, musisz zdefiniować element kontenera jako siatkę za pomocą `display: grid`, ustawić rozmiary kolumn i wierszy za pomocą  `grid-template-columns` i `grid-template-rows`, a następnie umieścić jego elementy podrzędne w siatce za pomocą `grid-column` i `grid-row`. Podobnie jak w przypadku Flexboksa, kolejność źródłowa elementów siatki nie ma znaczenia. Twój CSS może umieścić je w dowolnej kolejności, co sprawia, że ​​bardzo łatwo jest zmienić układ siatki za pomocą zapytań o media. Wyobraź sobie, że definiujesz układ całej strony, a następnie całkowicie go zmieniasz, aby dostosować się do innej szerokości ekranu, a wszystko to za pomocą zaledwie kilku linii CSS. Grid to jeden z najpotężniejszych modułów CSS, jakie kiedykolwiek wprowadzono.

**Dokładnie jest to opisanie na stronie [css-tricks](https://css-tricks.com/snippets/css/complete-guide-grid/).**

### Ważna terminologia dotycząca siatki CSS

##### Grid Container
Element, na który `display: grid` jest nakładany. Jest to bezpośredni rodzic wszystkich elementów siatki. W tym przykładzie  container jest to kontener siatki.

    <div class="container">
        <div class="item item-1"> </div>
        <div class="item item-2"> </div>
        <div class="item item-3"> </div>
    </div>

##### Grid Item
Elementy podrzędne (tj.  bezpośredni  potomkowie) kontenera siatki. Tutaj `item` są elementami siatki, ale `sub-item` już nie.

    <div class="container">
        <div class="item"> </div>
        <div class="item">
            <p class="sub-item"> </p>
        </div>
        <div class="item"> </div>
    </div>

##### Grid Line
![Grid line](grid-line.jpg)
Linie podziału tworzące strukturę siatki. Mogą być pionowe („linie siatki kolumn”) lub poziome („linie siatki wierszy”) i znajdować się po obu stronach wiersza lub kolumny. Tutaj żółta linia jest przykładem linii siatki słupów.

##### Grid Track
![Grid track](grid-track.jpg)
Przestrzeń pomiędzy dwiema sąsiadującymi liniami siatki. Można o nich myśleć jak o kolumnach lub rzędach siatki. Oto ścieżka siatki pomiędzy liniami siatki drugiego i trzeciego rzędu.

##### Grid Area
![Grid area](grid-area.jpg)
Całkowita przestrzeń otoczona czterema liniami siatki. Obszar siatki może składać się z dowolnej liczby komórek siatki. Oto obszar siatki pomiędzy liniami siatki wierszy 1 i 3 oraz liniami siatki kolumn 1 i 3.

##### Grid Cell
![Grid cell](grid-cell.jpg)
Przestrzeń pomiędzy dwoma sąsiednimi wierszami i dwiema sąsiadującymi liniami siatki kolumn. To pojedyncza „jednostka” siatki. Oto komórka siatki pomiędzy liniami siatki wierszy 1 i 2 oraz liniami siatki kolumn 2 i 3.

### Właściwości elementu nadrzędnego - rodzica (Grid Container)
Dokładny opis na stronie [css-tricks](https://css-tricks.com/snippets/css/complete-guide-grid/).
- `display` - Definiuje element jako kontener siatki i ustanawia nowy kontekst formatowania siatki dla jego zawartości.

        .container {
            display: grid | inline-grid;
        }
- `grid-template-columns`, `grid-template-rows` - Definiuje kolumny i wiersze siatki za pomocą listy wartości oddzielonych spacjami. Wartości reprezentują rozmiar ścieżki, a odstęp między nimi reprezentuje linię siatki.

        .container {
            grid-template-columns: ...  ...;
            /* e.g. 
                1fr 1fr
                minmax(10px, 1fr) 3fr
                repeat(5, 1fr)
                50px auto 100px 1fr
            */
            grid-template-rows: ... ...;
            /* e.g. 
                min-content 1fr min-content
                100px 1fr max-content
            */
        }
Liniom siatki automatycznie przypisywane są liczby dodatnie na podstawie tych przypisań (-1 oznacza alternatywę dla ostatniego wiersza).
- `grid-template-areas` - Definiuje szablon siatki, odwołując się do nazw obszarów siatki określonych za pomocą `grid-area` właściwości. Powtarzanie nazwy obszaru siatki powoduje, że zawartość rozciąga się na te komórki. Kropka oznacza pustą komórkę. Sama składnia zapewnia wizualizację struktury siatki.

        .container {
            grid-template-areas: 
            "<grid-area-name> | . | none | ..."
            "...";
        }
- `grid-template` - Skrót dla ustawienia `grid-template-rows`, ` grid-template-columns` i `grid-template-areas` w jednej deklaracji.

        .container {
            grid-template: none | <grid-template-rows> / <grid-template-columns>;
        }
- `column-gap`, `row-gap` - Określa rozmiar linii siatki. Można o tym pomyśleć jak o ustawianiu szerokości rynien pomiędzy kolumnami/wierszami.

        .container {
            column-gap: <line-size>;
            row-gap: <line-size>;
        }
- `grid-gap` - Skrót od  `row-gap` i `column-gap`

        .container {
            gap: <grid-row-gap> <grid-column-gap>;
        }
- `justify-items` - Wyrównuje elementy siatki wzdłuż osi *inline*(wiersza) (w przeciwieństwie do `align-items`, który dotyczy bloku  (kolumny)). Ta wartość dotyczy wszystkich elementów siatki wewnątrz kontenera.

        .container {
            justify-items: start | end | center | stretch;
        }
- `align-items` - Wyrównuje elementy siatki wzdłuż  osi bloku (kolumny)  (w przeciwieństwie do `justify-items` osi *inline* (wiersza)). Ta wartość dotyczy wszystkich elementów siatki wewnątrz kontenera.

        .container {
            align-items: start | end | center | stretch | baseline;
        }
- `place-items` - Ustawia  właściwości `align-items` i  `justify-items` w jednej deklaracji.

        .container {
            place-items: <align-items> / <justify-items>;
        }
- `justify-content` - Czasami całkowity rozmiar siatki może być mniejszy niż rozmiar jej kontenera siatki. Może się to zdarzyć, jeśli wszystkie elementy siatki mają wymiary nieelastyczne, takie jak `px`. W tym przypadku możesz ustawić wyrównanie siatki w kontenerze siatki. Ta właściwość wyrównuje siatkę wzdłuż osi *inline* (wiersza) (w przeciwieństwie do `align-content` tej, która wyrównuje siatkę wzdłuż osi bloku (kolumny)).

        .container {
            justify-content: start | end | center | stretch | space-around | space-between | space-evenly;    
        }
- `align-content` - Czasami całkowity rozmiar siatki może być mniejszy niż rozmiar jej kontenera siatki. Może się to zdarzyć, jeśli wszystkie elementy siatki mają wymiary nieelastyczne, takie jak  `px`. W tym przypadku możesz ustawić wyrównanie siatki w kontenerze siatki. Ta właściwość wyrównuje siatkę wzdłuż  osi bloku (kolumny)  (w przeciwieństwie do `justify-content` tej, która wyrównuje siatkę wzdłuż osi  wbudowanej (wiersza)).

        .container {
            align-content: start | end | center | stretch | space-around | space-between | space-evenly;    
        }
- `place-content` - Ustawia  właściwości align-content i  justify-content w jednej deklaracji.

        .container {
            placce-content: <align-content> / <justify-content>;
        }
- `grid-auto-columns`, `grid-auto-rows` - Określa rozmiar automatycznie generowanych ścieżek siatki (czyli *implicit grid tracks*). Niejawne ścieżki są tworzone, gdy w siatce jest więcej elementów siatki niż komórek lub gdy element siatki jest umieszczony poza jawną siatką.

        .container {
            grid-auto-columns: <track-size> ...;
            grid-auto-rows: <track-size> ...;
        }
- `grid-auto-flow` - Jeśli masz elementy siatki, których nie umieścisz bezpośrednio na siatce, włącza się *algorytm automatycznego umieszczania*, który automatycznie umieszcza te elementy.

        .container {
            grid-auto-flow: row | column | row dense | column dense;
        }
Pamiętaj, że **gęstość** zmienia jedynie wizualny porządek elementów i może powodować ich nieuporządkowanie, co negatywnie wpływa na dostępność.
- `grid` - Skrót do ustawiania wszystkich następujących właściwości w jednej deklaracji: `grid-template-rows`, `grid-template-columns`, `grid-template-areas`, `grid-auto-rows`, `grid-auto-columns` i  `grid-auto-flow`(Uwaga: W pojedynczej deklaracji siatki można określić tylko jawne lub ukryte właściwości siatki).

### Właścicwości elementu podrzędnego - dziecka (Grid Item)
- `grid-column-start`, `grid-column-end`, `grid-row-start`, `grid-row-end` - Określa lokalizację elementu siatki w siatce, odnosząc się do określonych linii siatki. `grid-column-start`/ `grid-row-start` to linia, w której element się zaczyna, a `grid-column-end`/ `grid-row-end` to linia, w której kończy się element.

        .item {
            grid-column-start: <number> | <name> | span <number> | span <name> | auto;
            grid-column-end: <number> | <name> | span <number> | span <name> | auto;
            grid-row-start: <number> | <name> | span <number> | span <name> | auto;
            grid-row-end: <number> | <name> | span <number> | span <name> | auto;
        }
- `grid-column`, `grid-row` - Skrót odpowiednio dla g`rid-column-start` + `grid-column-end` i `grid-row-start` + `grid-row-end`.

        .item {
            grid-column: <start-line> / <end-line> | <start-line> / span <value>;
            grid-row: <start-line> / <end-line> | <start-line> / span <value>;
        }
- `grid-area` - Nadaje elementowi nazwę, dzięki czemu można się do niego odwoływać za pomocą szablonu utworzonego za pomocą tej  `grid-template-areas` właściwości. Alternatywnie, tej właściwości można użyć jako jeszcze krótszego  skrótu  dla `grid-row-start` + `grid-column-start` + `grid-row-end `+ `grid-column-end`.

        .item {
            grid-area: <name> | <row-start> / <column-start> / <row-end> / <column-end>;
        }
- `justify-self` - Wyrównuje element siatki wewnątrz komórki wzdłuż osi `inline` (wiersza)  (w przeciwieństwie do `align-self` osi bloku  (kolumny)). Ta wartość dotyczy elementu siatki znajdującego się w pojedynczej komórce.

        .item {
            justify-self: start | end | center | stretch;
        }
- `align-self` - Wyrównuje element siatki wewnątrz komórki wzdłuż osi bloku (kolumny)  (w przeciwieństwie do  `justify-self` osi wbudowanej  (wiersza)). Ta wartość dotyczy zawartości pojedynczego elementu siatki.

        .item {
            align-self: start | end | center | stretch;
        }
- `place-self` - Ustawia  właściwości `align-self` i `justify-self` w jednej deklaracji.

        .item {
            place-self: auto | <align-self> / <justify-self>;
        }