---
title: 8. Instrukcje warunkowe
layout: post
---


**Czy program może podejmować decyzje?**
Tak, ale decyzja zależy od tego, co... mu powiemy.
Niektóre rzeczy dzieją się tylko wtedy, gdy zostanie spełniony konkretny warunek.  
Na przykład: woda wrze, gdy osiągnie 100°C, a drzwi otwierają się, gdy masz klucz.  

W programowaniu jest podobnie – dzięki instrukcjom warunkowym mówimy Pythonowi: *„Zrób coś, jeśli…”*.

Na przykład:
```python
if temperatura > 100:
    print("Woda się gotuje!")
```
Komputer nie wie, czym jest wrzątek – ale potrafi porównać liczby i wykonać kod, jeśli spełniony jest warunek.


## 🧠 if, elif, else – logika w kodzie

W Pythonie warunki zapisujemy za pomocą `if`, `elif` i `else`.  
To trzy słowa kluczowe, które pozwalają sterować przebiegiem programu.

### `if` – sprawdza, czy warunek jest spełniony:

```python
age = 16

if age < 18:
    print("Jesteś niepełnoletni/a")
```

### `elif` – sprawdzany tylko wtedy, gdy wcześniejszy warunek był fałszywy:

```python
if age < 12:
    print("Jesteś dzieckiem")
elif age < 18:
    print("Jesteś nastolatkiem")
```

### `else` – wykonuje się tylko wtedy, gdy **żaden poprzedni warunek nie był spełniony**:

```python
if age < 12:
    print("Jesteś dzieckiem")
elif age < 18:
    print("Jesteś nastolatkiem")
else:
    print("Jesteś dorosły/a")
```

📌 Python **nie używa nawiasów klamrowych `{}` jak JavaScript czy C++** – tu bardzo ważne są **wcięcia (indentacja)**.  
```
if warunek:
    # kod do wykonania jeśli warunek jest True
elif inny_warunek:
    # jeśli pierwszy nie działa, sprawdź ten
else:
    # jeśli żaden nie działa, wykonaj to
```
### Przetestuj!

Przekopiuj poniszy kod i umieść go w nowym pliku, uruchom i zobacz jak działa

```python
score = int(input("Podaj wynik testu w %: "))

if score >= 90:
    print("Ocena: 6")
elif score >= 75:
    print("Ocena: 5")
elif score >= 60:
    print("Ocena: 4")
elif score >= 45:
    print("Ocena: 3")
else:
    print("Ocena: 2")
```

### 🔹 Zadanie 1
Poproś użytkownika o dwie liczby. Sprawdź, która jest większa, albo czy są równe.

### 🔹 Zadanie 2 
Poproś o wiek i przypisz kategorię:

- do 5: maluch
- 6–12: dziecko
- 13–18: nastolatek
- 19+: dorosły

### 🔹 Zadanie 3 
Zapisz do zmiennej tajną liczbę (np. 7). Poproś użytkownika o zgadnięcie.
Wypisz "Za mało", "Za dużo", lub "Brawo!" w zależności od odpowiedzi.

### ⭐️ Zadanie 4 
Rozszerzmy zadanie powyzej. Wylosuj (poszukaj biblioteki `random`) liczbę i zapisz do zmiennej.
Poproś użytkownika o zgadnięcie.
Wypisz ciepło - zimno w zależności od odpowiedzi.
