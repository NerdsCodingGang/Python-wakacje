---
title: 10. Funkcje
layout: post
---

**Uwaga:** Dobrą praktyką jest pisanie kodu w języku angielskim - nazwy zmiennych, funkcji i komentarzy. Dzięki temu kod jest uniwersalny i zrozumiały dla programistów z całego świata.

Czasami chcemy wykonywać podobne rzeczy dla różnych wartości. Np. chcemy pomalować całe mieszkanie i musimy policzyć powierzchnię ścian dla każdego pokoju. Mamy pokoje o różnych wymiarach, ale samo liczenie będzie wyglądać dokładnie tak samo:

- Malujemy pokój o wymiarach 6m x 5m i wysokości 2,5 m.

- Sumujemy szerokości ścian: 2*6 + 2*5 = 22

- Wyliczamy powierzchnię ścian: 22 × 2,5 = 55

- Wyliczamy powierzchnię sufitu: 6 × 5 = 30

- Dodajemy powierzchnię ścian i sufitu: 55 + 30 = 85


![]({{ site.baseurl }}/assets/room.gif)

I tak dla 7 różnych pomieszczeń w naszym domu. Ale możemy to skrócić. W końcu chodzi o to, by zrobić coś takiego:

```python
x = jedna_sciana
y = druga_sciana
z = wysokosc
szer_scian = 2*x + 2*y
pow_scian = szer_scian * wysokosc
pow_sufitu = x * y
pow_malowania = pow_scian + pow_sufitu
```

Nasze zmienne elementy to x, y i z.

Do wykonywania takich czynności przyda nam się funkcja. Definicja funkcji wygląda następująco:

```python
def nazwa_funkcji():
    # co ma się wydarzyć

# np.:
def greeting():
    print('Hello World!')
```

Teraz funkcję należy wywołać:

```python
nazwa_funkcji()
greeting()
```

Przy każdym wywołaniu funkcji zadziała ona tak samo.

Ale co z naszymi zmiennymi parametrami? Otóż w nawiasach przy nazwie funkcji określmy właśnie te parametry. Np.

```python
def greeting(name):
    print('Hello ' + name)
```

Przy wywołaniu w miejscu parametru należy wstawić istniejące dane, np.

```python
greeting('Marta')
# >>> Hello Marta
greeting('Ania')
# >>> Hello Ania
```

Wróćmy do liczenia powierzchni: nasze zmienne parametry to szerokość jednej ściany, drugiej ściany i wysokość, czyli:

```python
def painting_area(wall_1, wall_2, height):
    # ....
```

Teraz wnętrze naszej funkcji:

```python
def painting_area(wall_1, wall_2, height):
    x = wall_1
    y = wall_2
    z = height
    walls_width = 2*x + 2*y
    walls_area = walls_width * height
    ceiling_area = x * y
    total_painting_area = walls_area + ceiling_area
    
    print(total_painting_area)
```

I jej wywołanie:

```python
painting_area(6, 5, 2.5)
painting_area(3, 4, 2.5)
```

### 🧪 Zadanie

W swoim pliku Python napisz funkcję o nazwie `hello_nerds_coding_gang`, która po wywołaniu wyświetli następujący napis: "Cześć, [tu poda imię osoby podanej w wywołaniu]! Witaj na warsztatach!".

```python
# Przykład wywołania:
hello_nerds_coding_gang('Anna')
# >>> Cześć, Anna! Witaj na warsztatach!
```