---
title: 7. Dane wejściowe i manipulacja tekstem
layout: post
---

Do tej pory wpisywaliśmy dane bezpośrednio w kodzie – np. `name = "Rita"`.

Ale co, jeśli chcemy zapytać użytkownika o imię lub wiek?  
Tu z pomocą przychodzi funkcja `input()`.


## Funkcja input()

🧾 Funkcja `input()` pozwala pobrać dane od użytkownika w trakcie działania programu.

Przykład:
```python
    print("Tu wpisz swoje imię: ")
    name = input()
```

Po uruchomieniu kodu Python zatrzyma się i poczeka, aż wpiszesz coś z klawiatury.  
Wpisany tekst zostanie przypisany do zmiennej `name`.

Można to też zapisać krócej:


    age = input("Ile masz lat? ")
    print("To już", age, "lat!")



## 🧪 Zadania

1. Przypisz swoje imię do zmiennej `my_name`
2. Przypisz swoje nazwisko do `my_surname`
3. Połącz imię i nazwisko w `full_name`
4. Zapytaj użytkownika o imię i wiek
5. Wyświetl powitanie oraz różnicę wieku między Tobą a użytkownikiem


### Indeksowanie znaków

Każdy ciąg znaków w Pythonie (czyli `str`) ma swoje **indeksy** – numerację od 0.  
Dzięki temu możemy „wyciągać” pojedyncze litery lub fragmenty tekstu.
Jest to tzw. indeksowanie. 


![Indeksowanie](../assets/step-3b.png){:title="Indeksowanie sekwencji" class="img-responsive"}

```
>>> seq = "Monty Python"
>>> print(seq[0])
>>> print(seq[1])
>>> print(seq[2])

>>> print(seq[6:10]) # przycinanie
Pyth

>>> print(seq[-1])
>>> print(seq[-2])

>>> print(seq[-12:-7])
Monty
```

Przycinanie obywa się wg. wzoru: `[start:stop:krok]` albo `[-od_tylu]`
# zawsze od zera!

Przeanalizuj kolejne linie kodu, każdą wyświetl:

```python
cool_string = "The quick brown fox jumped over the lazy dog"

# sprawdź długość - liczbę znaków
length = len(cool_string)  # 44

index0 = cool_string[0]  # litera: 'T'
index5 = cool_string[5]  # litera: 'u'

# znajdź ostatnią literę
index_last = len(cool_string) - 1 # dlaczego musmy odjąć 1?
last_char = cool_string[index_last]  # litera: 'g'

cool_slice_to_end = cool_string[4:]  # 'quick brown fox jumped over the lazy dog'

reversed_string = cool_string[::-1]  # odwraca kolejność liter
```

### 🧪 Zadanie

1. Stwórz zmienną z tekstem:

        "The quick brown fox jumped over the lazy dog"

2. Znajdź:
   - pierwszą literę
   - piątą literę
   - ostatnią literę (użyj `len()` i `-1`)
   - odwrócony ciąg (`[::-1]`)
   - długość napisu (`len()`)

---

## 🔄 Konwersja typów

Funkcja `input()` zawsze zwraca **tekst (`str`)**, nawet jeśli wpiszesz liczbę.
```python
    number = input("Wpisz tu 3: ")
    print(3 == number)         # False!
    print(type(number))        # <class 'str'>
```
Aby porównać z liczbą, musimy przekonwertować dane:
```
    number = int(number)
    print(3 == number)         # True
```
---

## 🧪 Zadania z konwersją

1. Stwórz zmienne:
```python
        a = 20
        c = "30"
```
2. Spróbuj:
```python
        print(a + c)      # Błąd!
```
3. Napraw to:
```python
        c = int(c)
        print(a + c)
```
4. Zamień `c` na `float` i dodaj z `a`

Patrząc na te przykłady... na czym polega konwersja typów? 

## 🔎 Mini projekt: czyszczenie tekstu

Stwórz zmienną z tekstem:
```
    quote = "Lorem ipsum dolor sit amet, consectetur adipiscing elit."
```

*Możesz skorzystać z Google, nie pytaj jednak o rozwiązanie AI - spróbuj ruszyć głową! 💡 *

1. Wyświetl długość tekstu (liczbę znaków)
2. Wyświetl pierwszą i ostatnią literę tekstu
3. Wytnij słowo `"elit"` za pomocą indeksowania
4. Usuń z tekstu wszystkie litery `"o"`
5. Zastąp przecinki (`,`) kropkami (`.`)
6. Sprawdź, na której pozycji pojawia się pierwsze wystąpienie litery `"i"`
7. Policz, ile razy litera `"e"` występuje w tekście
8. Zamień wszystkie litery na wielkie
9. Odwróć cały ciąg znaków
10. Utwórz nową zmienną `lorem_clean`, w której:
    - nie ma żadnych przecinków,
    - tekst zaczyna się dużą literą,
    - kończy się kropką (nawet jeśli wcześniej jej nie było)
11. Sprawdź, czy tekst zawiera słowo `"dolor"`
12. Podziel tekst na wyrazy i zapisz je jako listę

💡 Pamiętaj, że możesz tworzyć kolejne zmienne pomocnicze, by nie nadpisywać  `quote = Lorem...`.


W kolejnej lekcji nauczymy się podejmować decyzje w kodzie – czyli jak powiedzieć Pythonowi:  
*„jeśli użytkownik wpisał więcej niż 18 – wyświetl >>Możesz wejść<<”*  
Czas na `if`, `else` i instrukcje warunkowe!
