---
title: HTML - formularze
date: "2023-12-10T15:17:32.169Z"
description: "Jak zrobić formularz? Login i hasło, radio, checkbox, data i czas. Przykładowe atrybuty do formularzy."
slug: html-formularze
---

### Login i hasło

#### Kod
    <form action="login.php" method="post">
        <fieldset>
            login: <input type="text" name="login"><br>
            hasło: <input type="text" name="haslo"><br>
            <input type="submit" value="Zaloguj się">
        </fieldset>
    </form>

> `method="post"`- ukrywa zawartość formularza w linku

> `<fieldset>`- tworzy pole formularza

> `name="login"` - dzięki temu mamy informację, co przesyłamy dalej

#### Wynik
<form action="login.php" method="post">
    <fieldset>
        login: <input type="text" name="login"><br>
        hasło: <input type="text" name="haslo"><br>
        <input type="submit" value="Zaloguj się">
    </fieldset>
</form>


### Radio

#### Kod
    <form action="ankieta.php">
        <fieldset>
            <legend>Ile masz lat?</legend>
            <input type="radio" name="kat_wiek" id="kat_wiek1" value="7-18"><label for="kat_wiek1">7-18</label><br>
            <input type="radio" name="kat_wiek" id="kat_wiek2" value="18-40"><label for="kat_wiek2">18-40</label><br>
            <input type="radio" name="kat_wiek" id="kat_wiek3" value="41-75"><label for="kat_wiek3">41-75</label><br>
        </fieldset>
    <input type="submit" value="Wyślij">
    </form>

> `<legend>`- tytuł formularza

> `id=...`- dzięki temu można zrobić label

> `label for=...` - dzięki temu można kliknąć w napis

#### Wynik
<form action="ankieta.php">
        <fieldset>
            <legend>Ile masz lat?</legend>
            <input type="radio" name="kat_wiek" id="kat_wiek1" value="7-18"><label for="kat_wiek1">7-18</label><br>
            <input type="radio" name="kat_wiek" id="kat_wiek2" value="18-40"><label for="kat_wiek2">18-40</label><br>
            <input type="radio" name="kat_wiek" id="kat_wiek3" value="41-75"><label for="kat_wiek3">41-75</label><br>
        </fieldset>
    <input type="submit" value="Wyślij">
</form>


### Checkbox

#### Kod
    <form action="ankieta.php">
    <fieldset>
        <legend>Jakie jest Twoje hobby?</legend>
        <input type="checkbox" name="hobby" id="plywanie" value="plywanie"><label for="plywanie">pływanie</label>
        <input type="checkbox" name="hobby" id="taniec" value="taniec"><label for="taniec">taniec</label>
        <input type="checkbox" name="hobby" id="jazda_konna" value="jazda_konna"><label for="jazda_konna">jazda konna</label>
        <input type="checkbox" name="hobby" id="gry" value="gry"><label for="gry">gry</label>
    </fieldset>
    <input type="submit" value="Wyślij">
    </form>

#### Wynik
<form action="ankieta.php">
    <fieldset>
        <legend>Jakie jest Twoje hobby?</legend>
        <input type="checkbox" name="hobby" id="plywanie" value="plywanie"><label for="plywanie">pływanie</label>
        <input type="checkbox" name="hobby" id="taniec" value="taniec"><label for="taniec">taniec</label>
        <input type="checkbox" name="hobby" id="jazda_konna" value="jazda_konna"><label for="jazda_konna">jazda konna</label>
        <input type="checkbox" name="hobby" id="gry" value="gry"><label for="gry">gry</label>
    </fieldset>
    <input type="submit" value="Wyślij">
</form>


### Data i czas

#### Kod
    <form action="ankieta.php">
    <fieldset>
        Podaj dzień: <input type="date" min="2020-01-20" max="2022-01-20"><br>
        Podaj godzinę: <input type="time">
    </fieldset>
    <input type="submit" value="Wyślij">
    </form>

#### Wynik
<form action="ankieta.php">
    <fieldset>
        Podaj dzień: <input type="date" min="2020-01-20" max="2022-01-20"><br>
        Podaj godzinę: <input type="time">
    </fieldset>
    <input type="submit" value="Wyślij">
</form>


#### Atrybuty
- `checked` - domyślnie zaznaczone
- `required` - wymagany
- `autofocus` - automatyczne skupienie - myszka od razu pojawia się w wybranym oknie
- `autocomplete="off"` - wyłączenie autouzupełniania
- `size=""` - rozmiar okienka
- `maxlenght=""` - ilość znaków
- `placeholder=""` - szary tekst w polu
- `value=""` - domyślna wartość
>Przykład: `<input type="text" required>`