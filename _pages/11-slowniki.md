---
title: 11. Słowniki
layout: post
---

Słowniki to kolejny typ danych w Pythonie. Słownik pozwala przechowywać informacje w parach **klucz-wartość**. W przeciwieństwie do list, które używają numerycznych indeksów, słowniki używają kluczy do identyfikacji wartości.

Wyobraź sobie prawdziwy słownik - szukasz słowa (klucza) i znajdujesz jego definicję (wartość). Podobnie działają słowniki w Pythonie!

```python
slownik = {"klucz1": "wartość1", "klucz2": "wartość2", "klucz3": "wartość3"}
```

Słownik tworzymy używając nawiasów klamrowych `{}`, a pary klucz-wartość oddzielamy przecinkami. Klucz i wartość łączymy dwukropkiem `:`.

Stwórzmy np. słownik z informacjami o osobie:

```python
osoba = {"imie": "Anna", "nazwisko": "Kowalska", "wiek": 25, "miasto": "Warszawa"}
```

Aby wyświetlić wartość ze słownika, odwołujemy się do słownika i podajemy klucz:

```python
print(osoba["imie"])
# >>> Anna

print(osoba["wiek"])
# >>> 25
```

W swoim pliku Python stwórz teraz słownik o nazwie "ja", który zawiera informacje o Tobie: imię, wiek, ulubiony kolor i hobby. Następnie wypisz w konsoli swoje imię używając słownika.

### Właściwości słowników

Podobnie jak listy, słowniki mają swoją długość, którą możemy sprawdzić funkcją `len()`:

```python
print(len(osoba))
# >>> 4
```

Teraz wypisz w konsoli liczbę elementów w swoim słowniku "ja".

### Dodawanie i modyfikowanie elementów

Do dodawania nowej pary klucz-wartość wystarczy przypisać wartość do nowego klucza:

```python
osoba["email"] = "anna.kowalska@gmail.com"
print(osoba)
# >>> {"imie": "Anna", "nazwisko": "Kowalska", "wiek": 25, "miasto": "Warszawa", "email": "anna.kowalska@gmail.com"}
```

Dodaj do swojego słownika "ja" nowy klucz "ulubiona_ksiazka" z nazwą książki, którą lubisz.

Możemy również modyfikować istniejące wartości:

```python
osoba["wiek"] = 26
print(osoba["wiek"])
# >>> 26
```

Zmień wartość jednego z kluczy w swoim słowniku "ja" i wypisz go w konsoli.

### Różne typy danych w słowniku

W słowniku możemy przechowywać różne typy danych - stringi, liczby, listy, a nawet inne słowniki:

```python
student = {
    "imie": "Marek",
    "wiek": 20,
    "oceny": [4, 5, 3, 5, 4],
    "adres": {
        "ulica": "Główna 15",
        "miasto": "Kraków"
    },
    "aktywny": True
}
```

Aby dostać się do wartości w zagnieżdżonym słowniku:

```python
print(student["adres"]["miasto"])
# >>> Kraków

print(student["oceny"][0])
# >>> 4
```

### Sprawdzanie czy klucz istnieje

Zanim spróbujemy odwołać się do klucza, warto sprawdzić, czy istnieje. Używamy do tego słowa kluczowego `in`:

```python
if "email" in osoba:
    print(f"Email: {osoba['email']}")
else:
    print("Brak adresu email")
```

Sprawdź w swoim słowniku "ja", czy istnieje klucz "telefon". Jeśli nie, dodaj go!

### Usuwanie elementów ze słownika

Do usuwania elementów ze słownika możemy użyć kilku metod:

**Słowo kluczowe `del`**:
```python
del osoba["email"]
print(osoba)
# >>> {"imie": "Anna", "nazwisko": "Kowalska", "wiek": 26, "miasto": "Warszawa"}
```

**Metoda `pop()`** - usuwa element i zwraca jego wartość:
```python
usuniety_wiek = osoba.pop("wiek")
print(usuniety_wiek)  # >>> 26
print(osoba)          # >>> {"imie": "Anna", "nazwisko": "Kowalska", "miasto": "Warszawa"}
```

**Metoda `popitem()`** - usuwa ostatnio dodaną parę klucz-wartość:
```python
usunieta_para = osoba.popitem()
print(usunieta_para)  # >>> ("miasto", "Warszawa")
```

### Przydatne metody słowników

**Metoda `keys()`** - zwraca wszystkie klucze:
```python
osoba = {"imie": "Anna", "nazwisko": "Kowalska", "wiek": 25}
print(osoba.keys())
# >>> dict_keys(['imie', 'nazwisko', 'wiek'])
```

**Metoda `values()`** - zwraca wszystkie wartości:
```python
print(osoba.values())
# >>> dict_values(['Anna', 'Kowalska', 25])
```

**Metoda `items()`** - zwraca pary klucz-wartość:
```python
print(osoba.items())
# >>> dict_items([('imie', 'Anna'), ('nazwisko', 'Kowalska'), ('wiek', 25)])
```

**Metoda `get()`** - bezpieczny sposób pobierania wartości:
```python
# Jeśli klucz nie istnieje, zwraca None lub wartość domyślną
print(osoba.get("telefon"))           # >>> None
print(osoba.get("telefon", "Brak"))   # >>> Brak
print(osoba.get("imie", "Nieznane"))  # >>> Anna
```

### Pętla po słowniku

Możemy iterować po słowniku na kilka sposobów:

**Iterowanie po kluczach** (domyślne):
```python
osoba = {"imie": "Anna", "nazwisko": "Kowalska", "wiek": 25}

for klucz in osoba:
    print(klucz)
# >>> imie
# >>> nazwisko  
# >>> wiek
```

**Iterowanie po wartościach**:
```python
for wartosc in osoba.values():
    print(wartosc)
# >>> Anna
# >>> Kowalska
# >>> 25
```

**Iterowanie po parach klucz-wartość**:
```python
for klucz, wartosc in osoba.items():
    print(f"{klucz}: {wartosc}")
# >>> imie: Anna
# >>> nazwisko: Kowalska
# >>> wiek: 25
```

### Zadanie

Stwórz słownik "ksiazka" zawierający informacje o Twojej ulubionej książce: tytuł, autor, rok wydania, liczba stron, gatunek. Następnie:
1. Wypisz wszystkie informacje używając pętli
2. Dodaj klucz "przeczytana" z wartością True lub False
3. Usuń klucz "liczba_stron"
4. Wypisz tylko klucze słownika

### Łączenie słowników

Możemy połączyć dwa słowniki na kilka sposobów:

**Metoda `update()`**:
```python
osoba1 = {"imie": "Anna", "wiek": 25}
osoba2 = {"miasto": "Warszawa", "zawod": "programista"}

osoba1.update(osoba2)
print(osoba1)
# >>> {"imie": "Anna", "wiek": 25, "miasto": "Warszawa", "zawod": "programista"}
```

**Operator `|` (Python 3.9+)**:
```python
osoba1 = {"imie": "Anna", "wiek": 25}
osoba2 = {"miasto": "Warszawa", "zawod": "programista"}

nowa_osoba = osoba1 | osoba2
print(nowa_osoba)
# >>> {"imie": "Anna", "wiek": 25, "miasto": "Warszawa", "zawod": "programista"}
```

### Słownik z listą

Często używamy słowników do grupowania danych. Na przykład, lista uczniów w klasach:

```python
szkola = {
    "klasa_1a": ["Anna", "Marek", "Kasia"],
    "klasa_1b": ["Piotr", "Ola", "Tomek"],
    "klasa_2a": ["Ewa", "Jakub", "Maja"]
}

print(szkola["klasa_1a"])
# >>> ["Anna", "Marek", "Kasia"]

# Dodanie nowego ucznia do klasy
szkola["klasa_1a"].append("Paweł")
print(szkola["klasa_1a"])
# >>> ["Anna", "Marek", "Kasia", "Paweł"]
```

### Zadanie

Stwórz słownik "oceny", gdzie kluczami będą nazwy przedmiotów (np. "matematyka", "fizyka", "chemia"), a wartościami listy ocen z tych przedmiotów. Następnie:
1. Dodaj nową ocenę do matematyki
2. Oblicz średnią ocen z każdego przedmiotu
3. Wypisz przedmiot z najwyższą średnią

### Lista słowników

Możemy też tworzyć listy zawierające słowniki:

```python
uczniowie = [
    {"imie": "Anna", "wiek": 16, "klasa": "1a"},
    {"imie": "Marek", "wiek": 15, "klasa": "1b"},
    {"imie": "Kasia", "wiek": 16, "klasa": "1a"}
]

# Wypisanie wszystkich uczniów
for uczen in uczniowie:
    print(f"{uczen['imie']} ma {uczen['wiek']} lat i chodzi do klasy {uczen['klasa']}")
```

### Zadanie

Stwórz listę "produkty" zawierającą słowniki z informacjami o produktach w sklepie (nazwa, cena, kategoria, dostępność). Następnie:
1. Wypisz wszystkie produkty z kategorii "elektronika"
2. Znajdź najtańszy produkt
3. Policz ile jest produktów dostępnych (gdzie dostępność = True)

### Zagnieżdżone słowniki

Słowniki mogą zawierać inne słowniki, co pozwala na tworzenie złożonych struktur danych:

```python
firma = {
    "nazwa": "TechCorp",
    "adres": {
        "ulica": "Technologiczna 1",
        "miasto": "Warszawa",
        "kod": "00-001"
    },
    "pracownicy": {
        "jan_kowalski": {
            "stanowisko": "programista",
            "wynagrodzenie": 8000,
            "doświadczenie": 3
        },
        "anna_nowak": {
            "stanowisko": "designer",
            "wynagrodzenie": 7000,
            "doświadczenie": 5
        }
    }
}

print(firma["pracownicy"]["jan_kowalski"]["stanowisko"])
# >>> programista
```

### Zadanie

Stwórz słownik "biblioteka" reprezentujący system biblioteczny:
- Klucze to tytuły książek
- Wartości to słowniki z informacjami: autor, rok, dostępna (True/False), wypożyczający (imię osoby lub None)

Następnie napisz kod, który:
1. Wyświetla wszystkie dostępne książki
2. "Wypożycza" książkę (zmienia dostępna na False i dodaje imię wypożyczającego)
3. "Zwraca" książkę (zmienia dostępna na True i usuwa imię wypożyczającego)
4. Wyświetla statystyki: ile książek jest dostępnych, ile wypożyczonych