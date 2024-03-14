---
title: "#004 Command Prompt" 
date: "2024-03-14T19:45:06.169Z"
description: "Command Prompt to interaktywna linia poleceń dostępna w systemach operacyjnych z rodziny Windows."
slug: 004-cmd
---

### Co to jest Command Prompt?

**Command Prompt**, znany również jako **cmd.exe** lub w skrócie **cmd**, to interaktywna linia poleceń dostępna w systemach operacyjnych z rodziny Windows. Pozwala użytkownikom na wydawanie poleceń do zarządzania systemem operacyjnym oraz uruchamianie programów za pomocą tekstowych poleceń.

##### Niektóre podstawowe funkcje i operacje

1. **Wykonywanie poleceń systemowych:** Możesz używać poleceń systemowych, takich jak `dir` (wyświetlanie zawartości katalogu), `cd` (zmiana katalogu), `mkdir` (tworzenie nowego katalogu), `del` (usuwanie plików) i wiele innych, aby zarządzać plikami i katalogami.

2. **Uruchamianie programów:** Możesz uruchamiać programy za pomocą Command Prompt, podając ścieżkę do pliku wykonywalnego lub używając poleceń, które są skrótem do programów lub poleceń systemowych.

3. **Wykonywanie poleceń administracyjnych:** W trybie administratora możesz wykonywać polecenia, które wymagają uprawnień administracyjnych, takie jak instalacja oprogramowania, zarządzanie usługami systemowymi, konfiguracja sieci, itp.

4. **Tworzenie skryptów:** Możesz tworzyć skrypty batch (pliki z rozszerzeniem *.bat*), które zawierają zestaw poleceń, które wykonają się sekwencyjnie po uruchomieniu pliku skryptu.

5. **Diagnostyka i debugowanie:** Command Prompt może być również używany do diagnostyki systemu, sprawdzania połączeń sieciowych, wykonywania poleceń konserwacyjnych i debugowania.

6. **Rozwiązywanie problemów z uruchamianiem:** Command Prompt pozwala na wykonywanie różnych poleceń przywracania systemu, naprawy sektora rozruchowego, tworzenia kopii zapasowych i przywracania systemu do poprzedniego stanu.

7. **Programowanie i rozwój oprogramowania:** Programiści często korzystają z Command Prompt do kompilacji kodu źródłowego, zarządzania repozytoriami kodu za pomocą narzędzi takich jak Git, oraz do wykonywania różnych czynności związanych z rozwijaniem oprogramowania.

Warto zaznaczyć, że w nowszych wersjach systemu Windows wprowadzono również Windows PowerShell, bardziej rozbudowane narzędzie linii poleceń, które oferuje większe możliwości niż tradycyjny Command Prompt.

##### Command Prompt dla programisty
Command Prompt może być przydatnym narzędziem dla programistów, szczególnie w kontekście programowania w językach skryptowych, kompilacji kodu źródłowego, zarządzania repozytoriami kodu i innych zadań związanych z rozwojem oprogramowania.

1. **Kompilacja kodu źródłowego:** Jeśli pracujesz w językach programowania, które wymagają kompilacji, takich jak C, C++, C#, czy Java, możesz skompilować swoje programy za pomocą odpowiednich poleceń w Command Prompt. Na przykład, w przypadku języka C, możesz użyć poleceń `gcc` lub `clang` do kompilacji kodu.

2. **Uruchamianie skryptów:** Jeśli pracujesz w językach skryptowych, takich jak Python, Ruby, Perl, PowerShell, itp., możesz uruchamiać swoje skrypty za pomocą Command Prompt. Wystarczy wpisać nazwę skryptu w wierszu poleceń, aby uruchomić go w odpowiednim środowisku.

3. **Zarządzanie repozytoriami kodu:** Command Prompt pozwala na korzystanie z narzędzi kontroli wersji, takich jak Git, SVN (Subversion), czy Mercurial, do zarządzania repozytoriami kodu. Możesz klonować repozytoria, wykonywać operacje na branchach, commitować zmiany, przeglądać historię commitów, itp., za pomocą poleceń w Command Prompt.

4. **Instalacja i zarządzanie zależnościami:** W niektórych przypadkach, podczas pracy z różnymi środowiskami programistycznymi, może być konieczne instalowanie i zarządzanie różnymi narzędziami i bibliotekami. Command Prompt umożliwia instalowanie, aktualizowanie i usuwanie pakietów, bibliotek, czy narzędzi za pomocą odpowiednich poleceń, np. `npm`, `pip`, `gem`, `composer`, itp.

5. **Debugowanie i analiza:** Możesz użyć Command Prompt do debugowania i analizy kodu za pomocą odpowiednich narzędzi wiersza poleceń, takich jak `gdb` (GNU Debugger) dla języka C/C++, czy narzędzia do analizy kodu, takie jak grep, awk, sed, itp.

6. **Tworzenie i zarządzanie środowiskami wirtualnymi:** Jeśli pracujesz z różnymi wersjami języków programowania lub różnymi zestawami zależności, możesz użyć Command Prompt do tworzenia i zarządzania środowiskami wirtualnymi za pomocą narzędzi takich jak virtualenv dla Pythona, czy venv dla języka Java.

##### Jak używać podstawowych poleceń?

- Wpisz **dir** i naciśnij Enter.
- Zostanie wyświetlona lista plików i katalogów w bieżącym katalogu.
--------
- Wpisz **cd** ścieżka_do_katalogu i naciśnij Enter.
- Zostanie zmieniony bieżący katalog na określony katalog.
--------
- Wpisz **mkdir** nazwa_nowego_katalogu i naciśnij Enter.
- Zostanie utworzony nowy katalog o podanej nazwie.
--------
- Wpisz **del** nazwa_pliku i naciśnij Enter.
- Zostanie usunięty plik o podanej nazwie.
--------
- Wpisz **copy** ścieżka_do_pliku_docelowego ścieżka_do_docelowej_lokalizacji i naciśnij Enter.
- Zostanie skopiowany plik z jednej lokalizacji do drugiej.
--------
- Wpisz **move** ścieżka_do_pliku_docelowego ścieżka_do_docelowej_lokalizacji i naciśnij Enter.
- Zostanie przeniesiony plik do nowej lokalizacji.
--------
- Wpisz **ren** stara_nazwa_pliku nowa_nazwa_pliku i naciśnij Enter.
- Zostanie zmieniona nazwa pliku.
--------
- Wpisz **cls** i naciśnij Enter.
- Ekran Command Prompt zostanie wyczyszczony.