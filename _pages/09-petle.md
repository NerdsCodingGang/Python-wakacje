---
title: 9. Pętle
layout: post
---

Załóżmy, że chcemy coś zrobić kilka razy, np. wysłać 5 takich samych wiadomości, albo nadać identyfikator 30 kolejnym książkom w naszym księgozbiorze. Robienie kilkukrotnie tej samej rzeczy jest... nuuuudne i mało optymalne. 

Dlatego możemy wykorzystać pętle. 

Żeby powtórzyć coś kilkukrotnie potrzebujemy licznika - by wiedzieć, w którym momencie jesteśmy i czy powinnyśmy już skończyć, czy nadal powtarzać dany skrypt.

Załóżmy, że chcemy w konsoli napisać pięć razy wiadomość "Cześć! Miło nam Cię powitać na kursie Pythona!". Możemy to zrobić w ten sposób:

```python
print("Cześć! Miło nam Cię powitać na kursie Pythona!")
print("Cześć! Miło nam Cię powitać na kursie Pythona!")
print("Cześć! Miło nam Cię powitać na kursie Pythona!")
print("Cześć! Miło nam Cię powitać na kursie Pythona!")
print("Cześć! Miło nam Cię powitać na kursie Pythona!")
```

Trochę dużo pisania, prawda? Możemy ten kod uprościć!

### Pętla for z range()

Pętla for w Pythonie wygląda w następujący sposób:

```python
for zmienna in sekwencja:
    kod który chcemy powtórzyć
```

Żeby powtórzyć coś określoną liczbę razy, możemy skorzystać z funkcji `range()`, która tworzy sekwencję liczb:

```python
for i in range(5):
    kod który chcemy powtórzyć 5 razy
```

Przeróbmy nasz kod z wiadomością!

```python
for i in range(5):
    print("Cześć! Miło nam Cię powitać na kursie Pythona!")
```

Funkcja `range()` może przyjmować różne parametry:
- `range(5)` - tworzy liczby od 0 do 4 (5 liczb)
- `range(1, 6)` - tworzy liczby od 1 do 5 
- `range(1, 11, 2)` - tworzy liczby od 1 do 10 co 2 (1, 3, 5, 7, 9)

Możemy też liczyć w dół:

```python
for i in range(5, 0, -1):
    print("Cześć! Miło nam Cię powitać na kursie Pythona!")
```

W tym przypadku:
- zaczynamy od 5
- kończymy przed 0 (czyli na 1)
- zmniejszamy o 1 (dlatego -1)

Spróbuj w swoim pliku Python zapisać powyższą pętlę. Spraw, by kod powtórzył się 10 razy.

Czas na nasze książki! Przypomnijmy - chcemy dodać identyfikator (id) kolejnym 30 książkom.

Możemy to zrobić tak:

```python
print("id-1")
print("id-2")
print("id-3")
print("id-4")
print("id-5")
print("id-6")
# ...
print("id-30")
```

Ale taki kod zająłby bardzo wiele miejsca. Wykorzystajmy więc pętle! Zauważmy, że tym razem powtarzamy tę samą czynność, jednak string, który chcemy wyświetlić, zmienia się. Zwiększa się dokładnie o 1. Podobnie zachowuje się nasz licznik!

Sprawdź co się wydarzy, gdy spróbujesz wyświetlić w konsoli wartość naszego licznika (to jest zmienna więc wystarczy wpisać jej nazwę).

```python
for i in range(30):
    print(i)
```

Konsola wyświetliła nam liczby od 0 do 29. W końcu `range(30)` tworzy liczby od 0 do 29. Gdy osiąga 30, zatrzymujemy pętlę. Musimy więc lekko przerobić naszą pętlę. Nasze id zaczyna się od 1, więc użyjemy `range(1, 31)` - zaczynamy od 1 i kończymy przed 31 (czyli na 30).

```python
for i in range(1, 31):
    print(i)
```

Super! Teraz dodajmy brakujący element id, czyli string "id-". Możemy do tego wykorzystać łączenie stringów. W Pythonie możemy łączyć stringi na kilka sposobów:

```python
for i in range(1, 31):
    print("id-" + str(i))
```

Zwróć uwagę, że musimy przekształcić liczbę `i` na string za pomocą `str(i)`, żeby móc ją połączyć ze stringiem "id-".

Możemy to również zrobić za pomocą f-stringów (formatowania stringów), co jest bardzo popularne w Pythonie:

```python
for i in range(1, 31):
    print(f"id-{i}")
```

### Zadanie:

Wykorzystaj powyższą pętlę, by nadać id 50 książkom. Zapisz kod w swoim pliku Python.

### Pętla while

Oprócz pętli `for` w języku Python występuje pętla `while`, której struktura wygląda tak:

```python
while wyrażenie_sprawdzające:
    kod który chcemy powtórzyć dopóki jest spełniany warunek
```

Pętla `for` jest wykonywana określoną ilość razy (gdy używamy `range()`). Pętla `while` działa, dopóki wyrażenie po słowie `while` jest prawdziwe (`True`).

Zauważ jednak, że w tej pętli nie ma automatycznego licznika. Dlatego często dodaje się go ręcznie. Wracając do naszej wiadomości do 5 osób:

```python
counter = 0
while counter < 5:
    print("Cześć! Miło nam Cię powitać na kursie Pythona!")
    counter += 1
```

Zmienną, która jest naszym licznikiem definiujemy przed pętlą. Przy każdej pętli zwiększamy licznik o 1 za pomocą `counter += 1`.

**Ważne:** Pamiętaj, żeby zawsze zwiększać licznik w pętli `while`, inaczej pętla będzie działać w nieskończoność!

Możemy też stworzyć pętlę while, która liczy w dół:

```python
counter = 5
while counter > 0:
    print("Cześć! Miło nam Cię powitać na kursie Pythona!")
    counter -= 1
```

### Zadanie:

W swoim pliku Python napisz taką pętlę `while`, która 10 razy napisze w konsoli "Python jest super!".

### Dodatkowe informacje o pętlach

W Pythonie możemy również używać pętli `for` do iterowania po stringach, listach i innych sekwencjach:

```python
# Iterowanie po stringu
for litera in "Python":
    print(litera)
```

```python
# Iterowanie po liście
owoce = ["jabłko", "banan", "wiśnia"]
for owoc in owoce:
    print(owoc)
```

Te zastosowania poznasz w kolejnych lekcjach, ale warto już teraz wiedzieć, że pętle w Pythonie są bardzo wszechstronne!



### Kontrolowanie pętli - break i continue

Czasami chcemy przedwcześnie zakończyć pętlę lub pominąć pewne iteracje. Do tego służą słowa kluczowe `break` i `continue`.

### Słowo kluczowe break

`break` pozwala nam całkowicie wyjść z pętli, nawet jeśli warunek pętli nadal jest spełniony.

Załóżmy, że chcemy przeszukać długi tekst i znaleźć pierwszą literę "x". Gdy ją znajdziemy, nie musimy dalej szukać:

```python
tekst = "Python jest fantastyczny język programowania"
for litera in tekst:
    if litera == "x":
        print("Znaleziono literę x!")
        break
    print(f"Sprawdzam literę: {litera}")
```

Jeśli w naszym tekście nie ma litery "x", pętla przejdzie przez wszystkie znaki. Ale gdyby była, pętla zatrzymałaby się natychmiast po jej znalezieniu.

Spróbujmy z tekstem, który zawiera "x":

```python
tekst = "Python to świetny język do nauki programowania"
for litera in tekst:
    if litera == "x":
        print("Znaleziono literę x!")
        break
    print(f"Sprawdzam literę: {litera}")
```

Możemy też używać `break` w pętli `while`. Załóżmy, że chcemy prosić użytkownika o hasło, dopóki nie poda prawidłowego:

```python
poprawne_haslo = "python123"
while True:  # to będzie pętla nieskończona, ale...
    haslo = input("Podaj hasło: ")
    if haslo == poprawne_haslo:
        print("Hasło poprawne!")
        break  # ...użyjemy break, żeby z niej wyjść
    else:
        print("Hasło niepoprawne, spróbuj ponownie.")
```

### Słowo kluczowe continue

`continue` pozwala nam pominąć resztę kodu w danej iteracji pętli i przejść do następnej.

Załóżmy, że chcemy wypisać wszystkie litery z tekstu, ale pomijamy spacje:

```python
tekst = "Python jest super"
for litera in tekst:
    if litera == " ":
        continue  # pomijamy spacje
    print(f"Litera: {litera}")
```

Albo chcemy wypisać tylko litery, pomijając wszystkie znaki interpunkcyjne:

```python
tekst = "Witaj, świecie! Jak się masz?"
for znak in tekst:
    if znak in ".,!?":
        continue  # pomijamy znaki interpunkcyjne
    print(f"Znak: {znak}")
```

Możemy też łączyć `continue` z pętlami numerycznymi. Załóżmy, że chcemy wypisać liczby od 1 do 10, ale pomijamy liczby parzyste:

```python
for i in range(1, 11):
    if i % 2 == 0:  # jeśli liczba jest parzysta
        continue    # pomijamy ją
    print(f"Liczba nieparzysta: {i}")
```

### Zadanie 1:

Napisz pętlę, która przejdzie przez string "Programowanie w Pythonie" i:
- Wypisze każdą literę
- Zatrzyma się, gdy znajdzie literę "w"
- Użyj `break` do zatrzymania pętli

### Zadanie 2:

Napisz pętlę, która przejdzie przez string "Hello World 123!" i:
- Wypisze tylko litery (pomijając spacje, cyfry i znaki interpunkcyjne)
- Użyj `continue` do pomijania niechcianych znaków

### Łączenie break i continue

Możemy używać obu słów kluczowych w tej samej pętli. Załóżmy, że chcemy policzyć samogłoski w tekście, ale zatrzymać się, gdy znajdziemy cyfrę:

```python
tekst = "Python ma 5 samogłosek"
samogloski = "aeiouAEIOU"
licznik_samoglosek = 0

for znak in tekst:
    if znak.isdigit():  # jeśli znajdziemy cyfrę
        print(f"Znaleziono cyfrę: {znak}")
        print(f"Zatrzymujemy liczenie. Znaleziono {licznik_samoglosek} samogłosek.")
        break
    
    if znak not in samogloski:  # jeśli to nie samogłoska
        continue  # pomijamy i idziemy dalej
    
    # jeśli doszliśmy tutaj, to znaczy że znak to samogłoska
    licznik_samoglosek += 1
    print(f"Znaleziono samogłoskę: {znak}")
```

### Zadanie 3:

Napisz program, który:
1. Przejdzie przez string "Uczę się programowania w roku 2024"
2. Będzie szukał liter "p", "r", "o", "g", "r", "a", "m" w tej kolejności
3. Pominie wszystkie inne znaki używając `continue`
4. Zatrzyma się gdy znajdzie wszystkie litery słowa "program" używając `break`
5. Wypisuje każdą znalezioną literę

### Pętla while z break i continue

Możemy też używać `break` i `continue` w pętlach `while`. Oto przykład prostego menu:

```python
while True:
    print("\n--- MENU ---")
    print("1. Powitaj się")
    print("2. Powiedz coś miłego")
    print("3. Wyjdź")
    
    wybor = input("Wybierz opcję (1-3): ")
    
    if wybor == "1":
        print("Cześć! Miło Cię poznać!")
        continue  # wracamy do początku pętli (pokazujemy menu ponownie)
    
    if wybor == "2":
        print("Jesteś wspaniałą osobą!")
        continue
    
    if wybor == "3":
        print("Do widzenia!")
        break  # wychodzimy z pętli
    
    # jeśli użytkownik wpisał coś innego
    print("Nieprawidłowy wybór, spróbuj ponownie.")
```

### Zadanie 4:

Napisz program z pętlą `while`, który:
1. Pyta użytkownika o jego ulubiony kolor
2. Jeśli poda "czerwony", "zielony" lub "niebieski", program gratuluje wyboru i kończy działanie
3. Jeśli poda "czarny", program mówi "To nie jest kolor!" i pyta ponownie
4. Dla wszystkich innych kolorów program mówi "Fajny wybór!" i pyta ponownie
5. Użyj `break` do zakończenia programu i `continue` do powrotu do pytania