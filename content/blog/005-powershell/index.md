---
title: "#005 PowerShell" 
date: "2024-03-15T21:37:06.169Z"
description: "PowerShell to zaawansowane narzędzie wiersza poleceń i język skryptowy opracowany przez firmę Microsoft."
slug: 005-powershell
---

### Co to jest PowerShell?
PowerShell to zaawansowane narzędzie wiersza poleceń i język skryptowy opracowany przez firmę Microsoft. Został wprowadzony w 2006 roku jako część systemu Windows i jest znacznie bardziej rozbudowany niż tradycyjny Command Prompt (cmd.exe).

PowerShell oferuje bogate funkcje i możliwości, które umożliwiają użytkownikom zarządzanie systemem operacyjnym, aplikacjami, siecią, usługami, procesami, plikami i wieloma innymi aspektami systemu Windows. Jest również silnym narzędziem do automatyzacji zadań, dzięki czemu można wykonywać skomplikowane operacje i procedury za pomocą prostych skryptów.

##### Główne cechy PowerShell to:

1. **Obiektowość:** PowerShell operuje na obiektach, co oznacza, że dane są przekazywane w postaci obiektów, a nie tylko jako tekst. Dzięki temu można bardziej elastycznie manipulować danymi i wykonywać zaawansowane operacje.

2. **Wsparcie dla .NET Framework:** PowerShell wykorzystuje platformę .NET Framework, co oznacza, że można korzystać z szerokiej gamy funkcji i bibliotek dostępnych w tej platformie podczas pisania skryptów.

3. **Moduły:** PowerShell obsługuje moduły, które są paczkami zawierającymi funkcje, komendy, i inne zasoby. Można łatwo importować moduły do sesji PowerShell, co pozwala na rozszerzenie funkcjonalności programu.

4. **Skryptowanie:** PowerShell jest pełnoprawnym językiem skryptowym, co oznacza, że można pisać skrypty do automatyzacji zadań, wykonywania rutynowych operacji, zarządzania systemem itp.

5. **Interfejs użytkownika:** PowerShell oferuje graficzny interfejs użytkownika (GUI) w postaci programu Windows PowerShell ISE (Integrated Scripting Environment), który ułatwia pisanie, testowanie i debugowanie skryptów.

PowerShell jest coraz częściej wykorzystywany przez profesjonalistów IT, administratorów systemów, programistów i innych użytkowników do zarządzania systemami Windows, tworzenia automatyzacji, monitorowania, analizy danych i wielu innych zastosowań.

##### Jak korzystać z PowerShell?

1. **Uruchomienie PowerShell:**

W systemie Windows możesz uruchomić PowerShell w następujący sposób:
- Wyszukaj "PowerShell" w menu Start i wybierz aplikację "Windows PowerShell" lub "Windows PowerShell ISE".
- Wciśnij kombinację klawiszy Win + R, wpisz "powershell" i naciśnij Enter.
Możesz również uruchomić PowerShell z poziomu **Command Prompt**, wpisując polecenie `powershell` i naciskając Enter.

2. **Korzystanie z poleceń:**
Po uruchomieniu PowerShell możesz wpisywać i wykonywać polecenia. Na przykład, możesz wpisać `Get-Process`, aby wyświetlić listę działających procesów na komputerze, a następnie nacisnąć Enter, aby wykonać to polecenie.

3. **Pisanie skryptów:**
Możesz również pisać skrypty PowerShell, które wykonają sekwencję poleceń. Otwórz PowerShell ISE lub użyj ulubionego edytora tekstu do pisania skryptów. Zapisz plik z rozszerzeniem `.ps1`. Następnie wykonaj skrypt, wpisując jego nazwę w PowerShell i naciskając Enter.

4. **Zarządzanie modułami:**
PowerShell obsługuje moduły, które dodają funkcje i komendy do środowiska PowerShell. Możesz użyć poleceń, takich jak `Import-Module` lub `Install-Module`, aby zaimportować lub zainstalować moduły.

5. **Dokumentacja:**
Aby uzyskać pomoc dotyczącą dostępnych poleceń, funkcji, czy składni języka PowerShell, możesz użyć poleceń `Get-Help`, np. `Get-Help Get-Process`, aby uzyskać informacje o poleceniu `Get-Process`.

##### Przykładowy skrypt PowerShell

Wyświetla listę plików w określonym katalogu i zapisuje tę listę do pliku tekstowego:

    # Ścieżka do katalogu, którego zawartość chcemy wyświetlić
    $folderPath = "C:\Users\NazwaUżytkownika\Pulpit"

    # Pobranie listy plików w katalogu
    $fileList = Get-ChildItem -Path $folderPath

    # Wyświetlenie nazw plików w konsoli
    foreach ($file in $fileList) {
        Write-Host $file.FullName
    }

    # Zapisanie listy plików do pliku tekstowego
    $fileList | Out-File -FilePath "C:\Users\NazwaUżytkownika\Pulpit\ListaPlików.txt"

W tym skrypcie:

- Zmienna `$folderPath` zawiera ścieżkę do katalogu, którego zawartość chcemy wyświetlić.
- Za pomocą funkcji `Get-ChildItem` pobieramy listę plików znajdujących się w podanym katalogu.
- Następnie wyświetlamy nazwy plików w konsoli za pomocą pętli `foreach`.
- Na końcu używamy funkcji `Out-File`, aby zapisać listę plików do pliku tekstowego o nazwie "ListaPlików.txt" na pulpicie.
Ten przykładowy skrypt demonstruje podstawową funkcjonalność PowerShell, taką jak operacje na plikach, pętle i obsługę zmiennych.