---
title: "#007 .cache" 
date: "2024-06-03T17:45:06.169Z"
description: "Plik lub folder do przechowywania danych tymczasowych, w celu przyspieszenia działania systemów lub aplikacji."
slug: 007-cache
---

### Czym jest .cache?
Plik lub folder o nazwie .cache to zazwyczaj miejsce, gdzie aplikacje i systemy przechowują dane tymczasowe, aby przyspieszyć swoje działanie. Może on zawierać różne rodzaje informacji, takie jak:

##### Funkcje i zastosowania .cache
1. **Szybszy dostęp do danych:** Cache przechowuje często używane dane, dzięki czemu aplikacje mogą je szybciej odczytać, zamiast generować lub pobierać je za każdym razem.
2. **Zmniejszenie obciążenia sieci:** Przechowywanie tymczasowych kopii pobranych danych zmniejsza liczbę zapytań do zdalnych serwerów.
3. **Optymalizacja wydajności:** Przykłady to cache przeglądarek internetowych, które przechowują elementy stron internetowych (obrazy, skrypty) lub cache kompilatorów, które przechowują wyniki kompilacji kodu.

##### Przykłady użycia .cache
- **Przeglądarki internetowe:** Przechowują pliki z odwiedzonych stron internetowych, aby szybciej je ładować przy kolejnych odwiedzinach.
- **Systemy operacyjne:** Mogą przechowywać różne dane systemowe, takie jak metadane plików czy wyniki wyszukiwania.
- **Aplikacje programistyczne:** Narzędzia takie jak npm, pip, czy Yarn mogą używać cache do przechowywania pobranych pakietów, co przyspiesza przyszłe instalacje.

##### Zarządzanie .cache
- **Czyszczenie:** Czasami cache może się przepełnić lub zawierać nieaktualne dane, co może prowadzić do problemów. W takich przypadkach warto go wyczyścić.
- **Konfiguracja:** Wiele aplikacji pozwala na konfigurację ustawień cache, takich jak maksymalny rozmiar czy czas przechowywania danych.

##### Przykład lokalizacji
**Linux/Unix:** Pliki cache często znajdują się w katalogu domowym użytkownika, np. *~/.cache/*.

**Windows:** Pliki cache mogą być przechowywane w różnych miejscach, w zależności od aplikacji, np. *C:\Users\[Twoja_nazwa_użytkownika]\AppData\Local*.

Cache jest bardzo przydatnym mechanizmem, ale czasami może wymagać zarządzania, aby zapewnić optymalną wydajność systemu i aplikacji.

### .cache w kontekście projektu Gatsby

W kontekście projektu Gatsby, *.cache* jest specjalnym katalogiem, który Gatsby używa do przechowywania danych i artefaktów generowanych podczas procesu budowania strony. 

##### Funkcje .cache w Gatsby
1. **Przechowywanie danych build:** Gatsby zapisuje różne informacje o procesie budowania strony w katalogu .cache. Dzięki temu kolejne budowania mogą być szybsze, ponieważ niektóre kroki mogą być pominięte lub zoptymalizowane.
2. **Przechowywanie danych GraphQL:** Wyniki zapytań GraphQL używane w trakcie budowania strony są zapisywane w .cache. Pomaga to uniknąć ponownego wykonywania tych zapytań przy każdym buildzie.
3. **Hot Reloading:** Podczas dewelopmentu, Gatsby używa .cache do przechowywania danych, co umożliwia szybkie odświeżanie zmienionych plików bez potrzeby pełnego restartu serwera deweloperskiego.

##### Zawartość .cache
- **Pliki statyczne:** Zoptymalizowane wersje plików CSS, JavaScript i inne zasoby.
- **Dane GraphQL:** Wyniki zapytań GraphQL używane przez stronę.
- **Dane konfiguracyjne:** Różne metadane i konfiguracje używane przez Gatsby do optymalizacji procesu build.

##### Zarządzanie .cache
- **Usuwanie .cache:** Czasami konieczne może być ręczne usunięcie katalogu .cache, aby wymusić pełne odbudowanie strony. Można to zrobić za pomocą komendy:

      rm -rf .cache
lub

    gatsby clean

Komenda `gatsby clean` usuwa zarówno katalog *.cache*, jak i katalog *public*, który przechowuje gotowe pliki statyczne generowane przez Gatsby.

- **Automatyczne zarządzanie:** Gatsby automatycznie zarządza zawartością *.cache*, więc zazwyczaj nie ma potrzeby ręcznej interwencji. Jednak w przypadku problemów z budowaniem strony lub gdy zmiany nie są odzwierciedlane prawidłowo, czyszczenie cache może być pomocne.
##### Przykład użycia w projekcie Gatsby Starter Blog
Jeśli pracujesz nad projektem Gatsby Starter Blog, katalog .cache będzie automatycznie tworzony i zarządzany przez Gatsby. Możesz uruchomić lokalny serwer deweloperski za pomocą:

    gatsby develop
Jeśli napotkasz problemy z budowaniem strony, możesz wyczyścić cache i zbudować projekt ponownie:

    gatsby clean
    gatsby develop

##### Przykładowy workflow:
**1. Praca nad projektem:**

    gatsby develop
**2. Czyszczenie cache (opcjonalne, jeśli napotkasz problemy):**

    gatsby clean

**3. Budowanie wersji produkcyjnej:**

    gatsby build

**4. Testowanie produkcyjnej wersji lokalnie (opcjonalne):**

    gatsby serve

**5. Wdrożenie na serwer produkcyjny:** Przekazanie zawartości katalogu public na serwer hostingowy.

Cache w Gatsby jest kluczowym elementem, który pomaga w optymalizacji procesu budowania strony, przyspiesza development i pozwala na efektywne zarządzanie danymi i zasobami projektu.