---
title: 8. Instrukcje warunkowe
layout: post
---

Niektóre rzeczy dzieją się tylko wtedy, gdy zostanie spełniony konkretny warunek.  
Na przykład: woda wrze, gdy osiągnie 100°C, a drzwi otwierają się, gdy masz klucz.  
W programowaniu jest podobnie – dzięki instrukcjom warunkowym mówimy Pythonowi: *„Zrób coś, jeśli…”*.


## 🧠 if...elif...else

Instrukcja `if` sprawdza, czy warunek jest spełniony – jeśli tak, wykonuje wskazany kod.  
Dodatkowo możemy użyć `elif` (czyli „jeśli nie to, ale…”) i `else` („jeśli żaden warunek nie pasuje”).

Przykład:

    x = 34

    if x < 10:
        print("Liczba jest mniejsza od 10")
    elif x < 100:
        print("Liczba jest mniejsza od 100")
    else:
        print("Liczba jest większa lub równa 100")

📌 W Pythonie **nie używamy nawiasów `{}` jak w JavaScripcie** – zamiast tego bardzo ważne są **wcięcia (4 spacje)**.

---

## 🧪 Zadanie

1. Stwórz dwie zmienne `a` i `b` i przypisz im różne liczby
2. Napisz program, który:
    - wypisze `"a jest większe"` jeśli `a > b`
    - wypisze `"b jest większe"` jeśli `b > a`
    - wypisze `"a i b są równe"` w przeciwnym wypadku

---

## 📊 Operatory porównania

| Operator | Opis                 | Przykład     | Wynik   |
|----------|----------------------|--------------|---------|
| `==`     | równe                | `x == 5`     | True    |
| `!=`     | różne                | `x != 5`     | True    |
| `>`      | większe niż          | `x > 5`      | False   |
| `<`      | mniejsze niż         | `x < 5`      | True    |
| `>=`     | większe lub równe    | `x >= 5`     | False   |
| `<=`     | mniejsze lub równe   | `x <= 5`     | True    |

Uwaga: pojedynczy znak `=` służy **do przypisywania** wartości, a podwójny `==` do **porównywania**.

---

## 🧪 Zadania z porównaniami

1. Czy `23 + 3` to tyle samo co `15 + 11`?
2. Czy `29 // 7` daje `4`?
3. Czy `27 % 8` daje `3`?

---

## 🔁 Operatory logiczne

Czasem chcemy sprawdzić więcej niż jeden warunek naraz.  
Tu przydają się **operatory logiczne**:

| Operator | Działanie | Przykład                     | Wynik  |
|----------|-----------|------------------------------|--------|
| `and`    | i         | `x > 0 and x < 100`          | True   |
| `or`     | lub       | `x < 0 or x > 100`           | False  |
| `not`    | zaprzeczenie | `not (x == 5)`            | True   |

---

## 🧪 Zadania logiczne

1. Sprawdź, czy liczba `x` mieści się w przedziale od 10 do 20
2. Sprawdź, czy `x` jest większe od 100 **lub** równe 0
3. Sprawdź, czy `x` nie jest równe `y`

---

## 🎯 Sprawdzanie wieku

Poproś użytkownika o wiek i napisz program, który:

- Jeśli użytkownik ma mniej niż 12 lat – wypisze „Jesteś dzieckiem”
- Jeśli ma od 12 do 18 – wypisze „Jesteś nastolatką/nastolatkiem”
- Jeśli ma więcej – wypisze „Jesteś dorosła/dorosły”

Podpowiedź: pamiętaj, że `input()` zwraca tekst – trzeba przekonwertować go na liczbę za pomocą `int()`.

W kolejnej lekcji poznamy **pętle** – czyli jak powtarzać kod automatycznie i bez ręcznego kopiowania.  
To będzie początek Twojej przygody z automatyzacją! 🔁
