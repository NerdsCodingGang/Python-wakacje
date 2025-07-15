---
title: 14. Wszędzie są obiekty!
layout: post
---

**Uwaga:** To jest rozszerzenie kursu - obiekty nie są nam niezbędne do tworzenia fajnych programów, ale warto wiedzieć, że istnieją! 😊

... bo wszystko w Pythonie jest obiektem! To kolejny sposób organizowania danych. W Pythonie mamy coś podobnego do obiektów JavaScript - **słowniki** (które już znasz!) oraz prawdziwe **obiekty** (klasy).

## Słowniki jako "obiekty" - już to znasz!

```python
person = {
    'name': 'Natalia',
    'age': 27,
    'hobby': ['swimming', 'cycling', 'fantasy books']
}
```

Jak widzisz, słownik przypomina listę, ale zamiast indeksów liczbowych mamy **klucze**. Klucze to nazwy, które pomagają nam zrozumieć, co przechowujemy.

By odwołać się do jakiegoś elementu słownika, używamy klucza:

```python
print(person['hobby'])
# lub
print(person.get('hobby'))
```

Do istniejącego słownika możemy dodawać nowe elementy:

```python
person['city'] = 'Poznań'
print(person)
```

Możemy je także usuwać:

```python
del person['hobby']
# lub
person.pop('hobby')
```

## Zagnieżdżone słowniki

Czasami w słowniku może być inny słownik:

```python
person = {   
    'name': 'Natalia',
    'age': 27,
    'hobby': ['swimming', 'cycling', 'fantasy books'],
    'city': 'Poznań',
    'family': {
        'mom': 'Anna',
        'dad': 'Paweł',
        'sister': 'Karolina'
    }
}
```

Jak wyświetlić imię siostry?

```python
print(person['family']['sister'])
```

## Prawdziwe obiekty - klasy (bonus dla ciekawskich!)

W Pythonie możemy tworzyć prawdziwe obiekty używając **klas**. To jak szablon do tworzenia obiektów:

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
        self.hobbies = []
    
    def add_hobby(self, hobby):
        self.hobbies.append(hobby)
    
    def introduce(self):
        return f"Cześć! Jestem {self.name} i mam {self.age} lat."

# Tworzenie obiektu
natalia = Person('Natalia', 27)
natalia.add_hobby('swimming')
natalia.add_hobby('cycling')

print(natalia.introduce())
print(f"Hobby: {natalia.hobbies}")
```

## Dlaczego obiekty są fajne?

1. **Organizacja** - grupują powiązane dane
2. **Czytelność** - `person['name']` mówi więcej niż `data[0]`
3. **Elastyczność** - można łatwo dodawać/usuwać właściwości

## Przykład: System książek

```python
library = {
    'books': [
        {
            'title': 'Hobbit',
            'author': 'J.R.R. Tolkien',
            'year': 1937,
            'available': True
        },
        {
            'title': 'Dune',
            'author': 'Frank Herbert', 
            'year': 1965,
            'available': False
        }
    ]
}

def find_available_books(library):
    available = []
    for book in library['books']:
        if book['available']:
            available.append(book['title'])
    return available

print("Dostępne książki:")
for title in find_available_books(library):
    print(f"- {title}")
```

## Zadanie (opcjonalne!)

Stwórz słownik reprezentujący Twoją ulubioną grę:

```python
game = {
    'title': 'Nazwa gry',
    'genre': 'Gatunek',
    'rating': 8.5,
    'platforms': ['PC', 'PlayStation', 'Xbox'],
    'details': {
        'developer': 'Studio deweloperskie',
        'release_year': 2023,
        'multiplayer': True
    }
}

# Wyświetl informacje o grze
def display_game_info(game):
    # Twoja implementacja tutaj!
    pass
```

## Podsumowanie

Obiekty (słowniki) to świetny sposób na organizację danych, ale nie są niezbędne! Wszystko, co możesz zrobić z obiektami, możesz też zrobić ze zwykłymi zmiennymi, listami i funkcjami. 

Obiekty po prostu sprawiają, że kod jest bardziej czytelny i łatwiejszy do utrzymania w większych projektach! 🚀

**Pamiętaj:** Nie musisz się tego uczyć na siłę - to tylko dodatkowe narzędzie w Twoim zestawie programistycznym!