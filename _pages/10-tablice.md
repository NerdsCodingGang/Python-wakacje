---
title: 10. Listy
layout: post
---

Zmienne, które dotychczas uzywamy, zawierały tylko jeden element - string, liczbę, czy wartość logiczną. Czasami jednak musimy skorzystać z całej listy danych. Do ich przechowywania służą nam listy zwane tez tablicami.

```python
pusta_lista = []
lista = ["pomarańcza", 34, True, "mandolina", 45, [67, 56, "czerwony"]]
```
Wyświetl te dwie zmienne.

Jak widać, listę tworzymy zapisując dane pomiędzy kwadratowymi nawiasami i oddzielając te elementy od siebie przecinkami. W liście możemy przechowywać różne typy danych: stringi, liczby, zmienne typu logicznego, a nawet inne listy.

Stwórzmy np. listę znajomych:

```python
friends = ["Michał", "Marta", "Mikołaj", "John", "Natalia", "Ania"]
```

Aby wyświetlić element listy, odwołujemy się do listy i pozycji danego elementu.

UWAGA!

Kolejność elementów liczymy od 0. Tak więc:

```python
print(friends[0])
# >>> Michał

print(friends[3])
# >>> John
```

W swoim pliku Python stwórz teraz listę o nazwie "group", która zawiera imiona wszystkich osób z grupy, z którą pracujesz na warsztatach. Następnie wypisz w konsoli imię pierwszej zapisanej osoby.

Podobnie jak stringi, długość listy możemy ustalić dzięki funkcji **len()**

```python
print(len(friends))
# >>> 6
```

Teraz wypisz w konsoli długość listy z imionami osób z Twojej grupy, a następnie wyloguj imię osoby, która jest zapisana jako ostatnia.

Do dodawania nowego elementu służy metoda **append()**:

```python
friends.append('Kasia')

print(friends)
# >>> ["Michał", "Marta", "Mikołaj", "John", "Natalia", "Ania", "Kasia"]
```

Za jej pomocą dodajemy nowy element na końcu listy.

Dodaj do swojej listy "group" jeszcze jedno dowolne imię używając do tego metody `append()`, a następnie wypisz je w konsoli.

Możemy również nadpisać istniejący element listy o określonej pozycji:

```python
friends[2] = "Tomek"

print(friends)
# >>> ["Michał", "Marta", "Tomek", "John", "Natalia", "Ania", "Kasia"]
```

Nadpisz ostatnio dodane do swojej listy imię innym. Raz jeszcze wypisz ostatnie imię w konsoli.

Różne listy możemy dodać do siebie. Stwórz listę z imionami przyjaciół z pracy i drugą z imionami przyjaciół z imprez.

Aby stworzyć listę, w której znajdą się imiona wszystkich Twoich przyjaciół, możemy użyć operatora `+`:

```python
work_friends = ["Michał", "Marta", "Tomek", "John", "Natalia", "Ania", "Kasia"]
party_friends = ["Asia", "Kamil", "Bartek", "Ola", "Weronika", "Czarek"]

all_friends = work_friends + party_friends

print(all_friends)
# >>> ["Michał", "Marta", "Tomek", "John", "Natalia", "Ania", "Kasia", "Asia", "Kamil", "Bartek", "Ola", "Weronika", "Czarek"]
```

Możemy też użyć metody `extend()`, która dodaje wszystkie elementy z jednej listy do drugiej:

```python
work_friends = ["Michał", "Marta", "Tomek", "John", "Natalia", "Ania", "Kasia"]
party_friends = ["Asia", "Kamil", "Bartek", "Ola", "Weronika", "Czarek"]

work_friends.extend(party_friends)
print(work_friends)
# >>> ["Michał", "Marta", "Tomek", "John", "Natalia", "Ania", "Kasia", "Asia", "Kamil", "Bartek", "Ola", "Weronika", "Czarek"]
```

Sprawdź w konsoli, jak wygląda nowa lista powstała za pomocą `+` lub `extend()`.

By "pobrać" kawałek listy używamy mechanizmu nazywanego "slicing" (krojenie). Określamy od którego elementu chcemy ciąć i na którym chcemy skończyć:

```python
friends = ["Michał", "Marta", "Tomek", "John", "Natalia", "Ania", "Kasia"]

part = friends[1:4]
print(part)
# >>> ["Marta", "Tomek", "John"]
```

Zwróć uwagę, że `friends[1:4]` oznacza elementy od pozycji 1 (włącznie) do pozycji 4 (wyłącznie).

Stwórz teraz jeszcze jedną listę, której elementami będą pierwsze i drugie imię z listy "group". Użyj do tego slicing.

Do usuwania elementów z listy służy kilka metod:

**Metoda pop()** - usuwa i zwraca ostatni element (lub element o określonej pozycji):

```python
friends = ["Michał", "Marta", "Tomek", "John", "Natalia", "Ania", "Kasia"]

usuniety_element = friends.pop()
print(usuniety_element)  # >>> Kasia
print(friends)           # >>> ["Michał", "Marta", "Tomek", "John", "Natalia", "Ania"]

# Możemy też usunąć element o konkretnej pozycji:
friends.pop(2)
print(friends)           # >>> ["Michał", "Marta", "John", "Natalia", "Ania"]
```

**Metoda remove()** - usuwa pierwsze wystąpienie określonego elementu:

```python
friends = ["Michał", "Marta", "Tomek", "John", "Natalia", "Ania", "Kasia"]

friends.remove("Tomek")
print(friends)
# >>> ["Michał", "Marta", "John", "Natalia", "Ania", "Kasia"]
```

**Słowo kluczowe del** - usuwa element o określonej pozycji:

```python
friends = ["Michał", "Marta", "Tomek", "John", "Natalia", "Ania", "Kasia"]

del friends[2]
print(friends)
# >>> ["Michał", "Marta", "John", "Natalia", "Ania", "Kasia"]
```

Usuń teraz za pomocą jednej z powyższych metod pierwsze imię z listy "group".

### Wstawienie elementu w określone miejsce

Do wstawienia elementu w konkretne miejsce służy metoda **insert()**:

```python
friends = ["Michał", "Marta", "John", "Natalia", "Ania", "Kasia"]

friends.insert(2, "Patrycja")
print(friends)
# >>> ["Michał", "Marta", "Patrycja", "John", "Natalia", "Ania", "Kasia"]
```

Pierwszy parametr to pozycja, w którą chcemy wstawić element, drugi to wartość elementu.

### Wyszukiwanie elementu

Do wyszukiwania pozycji elementu służy metoda **index()**. Zwraca ona indeks danego elementu lub wywołuje błąd, jeśli go nie znajdzie:

```python
friends = ["Michał", "Marta", "Tomek", "John", "Natalia", "Ania", "Kasia"]

if "Marta" in friends:
    pozycja = friends.index("Marta")
    print(f"Marta znajduje się na pozycji {pozycja}")
else:
    print("Marty nie ma w tej liście")
```

Możemy też sprawdzić, czy element istnieje w liście używając operatora **in**:

```python
if "Marta" in friends:
    print("Marta znajduje się w tej liście!")
else:
    print("Marty nie ma w tej liście")
```

Korzystając z `index()` sprawdź jaką pozycję ma Twoje imię w liście "group".

### Pętla po liście

Pętla to doskonały sposób przechodzenia (iterowania) po elementach listy. Wykorzystajmy ją do wypisania naszych znajomych. Aby wypisać jakiś element listy, określamy jego indeks:

```python
friends = ["Michał", "Marta", "Tomek", "John", "Natalia", "Ania", "Kasia"]

print(friends[0])
print(friends[1])
print(friends[2])
print(friends[3])
# ...
```

Ale pojawiają się dwa problemy. Po pierwsze, będzie to mało optymalne. Po drugie, co jeśli nie wiem ile jest elementów na liście i jak długo mam powtarzać ten sam kod?

Spróbujmy więc pętli `for` z `range()`:

```python
friends = ["Michał", "Marta", "Tomek", "John", "Natalia", "Ania", "Kasia"]
for i in range(len(friends)):
    print(friends[i])
```

Używamy `range(len(friends))`, co da nam liczby od 0 do długości listy minus 1 - dokładnie to, czego potrzebujemy do indeksowania.

Ale Python oferuje jeszcze prostszy sposób - możemy iterować bezpośrednio po elementach listy:

```python
friends = ["Michał", "Marta", "Tomek", "John", "Natalia", "Ania", "Kasia"]
for friend in friends:
    print(friend)
```

To jest najbardziej pythonowy (prawdziwie pythoński) sposób!

Przećwiczmy to jeszcze wracając do naszej wiadomości. Powiedzmy, że chcemy ją spersonalizować i wyświetlić, np.

> "Cześć Michał! Miło nam Cię powitać na kursie Pythona!"

Wystarczy do naszej wcześniejszej pętli dodać brakujący tekst powitania:

```python
friends = ["Michał", "Marta", "Tomek", "John", "Natalia", "Ania", "Kasia"]
for friend in friends:
    print(f"Cześć {friend}! Miło nam Cię powitać na kursie Pythona!")
```

Możemy też użyć łączenia stringów:

```python
for friend in friends:
    print("Cześć " + friend + "! Miło nam Cię powitać na kursie Pythona!")
```

### 🧪 Zadanie

Używając pętli `for` spraw, aby w konsoli pojawił się napis witający na kursie Pythona wszystkie osoby zapisane w Twojej liście "group". Tekst ma być następujący: "Cześć \[tu imię osoby\]! Miło nam Cię powitać na kursie Pythona!".

### Enumerate - gdy potrzebujemy i indeksu i wartości

Czasami potrzebujemy zarówno indeksu elementu, jak i jego wartości. Do tego służy funkcja `enumerate()`:

```python
friends = ["Michał", "Marta", "Tomek", "John", "Natalia", "Ania", "Kasia"]
for i, friend in enumerate(friends):
    print(f"{i}: {friend}")
```

To wypisze:
```
0: Michał
1: Marta
2: Tomek
3: John
4: Natalia
5: Ania
6: Kasia
```

### 🧪 Zadanie

Wykorzystując pętlę znajdź i wypisz wszystkie samogłoski ze zdania: 

"Nad rzeczką opodal krzaczka, mieszkała kaczka-dziwaczka, lecz zamiast trzymać się rzeczki, robiła piesze wycieczki."

Podpowiedź: string można traktować jak listę znaków ;)

```python
zdanie = "Nad rzeczką opodal krzaczka, mieszkała kaczka-dziwaczka, lecz zamiast trzymać się rzeczki, robiła piesze wycieczki."
samogloski = "aeiouAEIOU"

for litera in zdanie:
    if litera in samogloski:
        print(litera)
```

### Dodatkowe metody list

Python oferuje wiele przydatnych metod do pracy z listami:

**count()** - zlicza wystąpienia elementu:
```python
lista = [1, 2, 3, 2, 2, 4]
print(lista.count(2))  # >>> 3
```

**reverse()** - odwraca listę:
```python
lista = [1, 2, 3, 4, 5]
lista.reverse()
print(lista)  # >>> [5, 4, 3, 2, 1]
```

**sort()** - sortuje listę:
```python
lista = [3, 1, 4, 1, 5, 9, 2, 6]
lista.sort()
print(lista)  # >>> [1, 1, 2, 3, 4, 5, 6, 9]
```

**clear()** - usuwa wszystkie elementy z listy:
```python
lista = [1, 2, 3, 4, 5]
lista.clear()
print(lista)  # >>> []
```

### 🧪 Zadanie

Stwórz listę zawierającą liczby od 1 do 10, następnie:
1. Dodaj liczbę 11 na koniec
2. Wstaw liczbę 0 na początku
3. Usuń liczbę 5 z listy
4. Wypisz wszystkie elementy używając pętli
5. Posortuj listę i wypisz ponownie