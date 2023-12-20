---
title: Emmet
date: "2023-12-14T12:02:03.284Z"
description: "Przydatne skróty"
---

### Skróty klawiaturowe

- `! + enter` lub `! + tab`  - tworzy cały **układ strony**
Żeby zmienić ustawienia wchodzimy w koło zębate po lewej na dole w VSC, następnie settings. W search wpisujemy „emmet var”. Dodajemy item, klikamy lang i wybieramy język pl. Wtedy z automtu idzie już zawsze na polski.

- `CTRL + /` - tworzy **komentarz**

##### Zaznaczanie

- `SHIFT + strzałki góra i dół` - zaznaczenie całej linii
- `SHIFT + strzałki lewa/prawa` - zaznaczenie literki w lewo i w prawo
- `CTRL + SHIFT + strzałki lewa/prawa` - zaznaczenie lewa/prawa całego słowa
- `CTRL + SHIFT + HOME` - zaznaczenie całej treści od zaznaczenie do jego początku
- `CTRL + SHIFT + END` - zaznaczenie całej treści od zaznaczenie do końca
- `CTRL + D` - zaznacza następny taki sam zaznaczony ciąg znaków

##### Poruszanie się

- `SHIFT + ALT + strzałka w górę/dół` – kopiowanie **linijki** w górę/dół
- `ALT + strzałka w górę/dół` – przesuwanie bieżącej **linijki** w górę/dół (można zaznaczyć kilka linijek)

- `CTRL + HOME` - przeskoczenie na początek **pliku**
- `CTRL + END` - przeskoczenie na koniec **pliku**

- `ALT` - kilka **kursorów**
- `SHIFT + CTRL + ALT + strzałka góra/dół` - też kilka **kursorów**
- `CTRL + H` - zamienianie 
- `ALT + TAB` – przeskakiwanie pomiędzy programami

##### Usuwanie

- `CTRL + Delete` - usuwa pojedyncze słowo PO kursorze
- `CTRL + Backspace` - usuwa pojedyncze słowo PRZED kursorem
- `SHIFT + Delete` - usuwa całą linię

### Kombinatory 

- `>` – odpowiada za dzieci
- `+` – odwołuje się do braci
- `^` – cofa się o jeden poziom; można zamiast liczenia daszków wpisać część w nawiasie, jak na matmie
- `~`

### Klasy, ID, atrybuty

- `.test` – tworzy diva z klasą „test”
- `#test` – tworzy diva z ID „test”
- `p.test` – tworzy paragraf z taką klasą; można wpisać dowolną nazwę tagu przed znakiem
- `td[colspan=”5”]` – tworzy atrybut
- `a{test}` – tworzy tag „a” z napisem w środku „test”
- `$` – liczenie
- `$@5` – liczenie zaczęte od 5
- `input:password` – tworzy inputa z wybranym typem

### Lorem

- `lorem` – tworzy akapit lorem
- `lorem5` – tworzy lorem z 5 słowami
- `lorem*3` – tworzy 3 akapity lorem
- `p*3>lorem3` – utworzy 3 paragrafy z loremami po 3 słowa

### CSS

- `m10` – margin: 10px;
- `m10-20` – margin: 10px 20px;
- `p-10` – padding: -10px;
- `p-10—20` – padding: -10px -20px;
- `m10p` – margin: 10%;
- `fz20` – font-size: 20px;
- `fz20r` – font-size: 20rem;
- `c#f` – color: #fff;
- `bgc#123` – background-color: #123;
