# Wprowadzenie do Cyberbezpieczeństwa (WCYB) 25Z

## Laboratorium Python
Autor: Paweł Popiołek <<pawel.popiolek@pw.edu.pl>>

## Spis Treści

1. [Wprowadzenie](#wprowadzenie)
2. [Wykonywanie poleceń](#wykonywanie-polecen)
3. [Zmienne](#zmienne)
4. [Operatory](#operatory)
5. [Środowisko pracy](#srodowisko-pracy)
6. [Listy](#listy)
7. [Instrukcje Warunkowe, Pętle](#instrukcje-warunkowe-petle)
8. [Funkcje](#funkcje)
9. [Klasy](#klasy)
10. [Biblioteki i środowiska wirtualne](#biblioteki-i-srodowiska-wirtualne)
11. [Wyrażenia regularne w Pythonie (RegEx)](#wyrazenia-regularne-w-pythonie-regex)
12. [Pisanie stylowego kodu (PEP8)](#pisanie-stylowego-kodu-pep8)



# 1. Wprowadzenie <a id="wprowadzenie"></a>

## Czym jest Python?
**Dlaczego warto nauczyć się Pythona dla potrzeb cyberbezpieczeństwa?** Język ten, plasujący się na czele listy najchętniej wybieranych języków skryptowych, jest doskonałym narzędziem do automatyzacji monotonnych zadań i tworzenia różnorodnych aplikacji. W środowiskach eksperckich z dziedziny cyberbezpieczeństwa Python jest często wybierany do tworzenia tzw. PoC (Proof of Concepts) oraz wielu narzędzi do sprawdzania bezpieczeństwa systemów. Jego łatwa w nauce składnia sprzyja szybkiemu prototypowaniu, a elastyczność oraz obszerna pomoc społeczności sprawiają, że jest on również odpowiedni dla bardziej złożonych projektów.

Oto kilka kluczowych obszarów zastosowań Pythona w cyberbezpieczeństwie:

1. **Automatyzacja Zadań**: Szybkie tworzenie skryptów do automatyzacji zadań, takich jak zbieranie danych o zagrożeniach, analiza logów czy zarządzanie konfiguracją zabezpieczeń.
2. **Analiza Malware**: Używanie narzędzi i bibliotek do badania złośliwego oprogramowania i zrozumienia, jakie zagrożenia może ono stwarzać.
3. **Testy Penetracyjne**: Projektowanie narzędzi i skryptów do przeprowadzania testów penetracyjnych w celu identyfikacji i oceny podatności systemów.
4. **Kryminalistyka Cyfrowa**: Analiza dowodów cyfrowych w celu identyfikacji nieautoryzowanej aktywności i rekonstrukcji zdarzeń.
5. **Odpowiedź na Incydenty**: Tworzenie narzędzi do szybkiego reagowania na incydenty bezpieczeństwa i łagodzenia ich skutków.
6. **Rozwój Narzędzi Bezpieczeństwa**: Projektowanie i rozwijanie narzędzi do monitorowania bezpieczeństwa, wykrywania anomalii i ochrony przed zagrożeniami.

Nie zależnie od tego, czy planujesz tworzyć skrypty do automatyzacji działań na stronie internetowej, analizować ogromne zbiory danych, przeprowadzać zaawansowane ataki na systemy czy projektować interaktywne usługi bezpieczeństwa, Python jest świetnym wyborem.

**Co jeszcze warto wiedzieć o Pythonie?** Jest to język interpretowany, co oznacza, że nie wymaga kompilacji kodu do postaci maszynowej, jak w przypadku języka C. Kod jest interpretowany przez Pythona bezpośrednio w trakcie wykonania. Jest to również język wysokiego poziomu, co upraszcza proces programowania, eliminując potrzebę martwienia się o zarządzanie pamięcią czy bezpośrednie wywołania systemowe. Python jest wszechstronny i nie narzuca jednego, konkretnego paradygmatu programowania.



# 2. Wykonywanie poleceń <a id="wykonywanie-polecen"></a>

Kod w Pythonie można uruchomić na wiele sposobów. Dwie najczęściej używane metody to uruchamianie kodu z pliku .py oraz bezpośrednio w środowisku Python IDLE. W tym fragmencie przyjrzymy się, jak korzystać z obu tych metod. Uruchamianie kodu z pliku jest przydatne podczas tworzenia pełnego skryptu, podczas gdy IDLE jest idealne do szybkiego testowania niewielkich fragmentów kodu. Zacznijmy od metody opartej na plikach.

**Wykonywanie z pliku.** Klasyczny kod, który wyświetla napis "Hello world!". W Pythonie prezentuje się tak:

```python
print("Hello world!")
```

Uruchamiając ten skrypt, napis "Hello world!" zostanie wyświetlony w terminalu. Aby to przetestować, otwórz edytor tekstu, wprowadź powyższy kod i zapisz plik jako hello.py. Następnie uruchom go poleceniem ```python3 hello.py```. Uwaga: Pamiętaj o konieczności uruchomienia skryptu z poziomu odpowiedniego katalogu (do przechodzenia pomiędzy katalogami, wykorzystaj polecenie```cd```).

```
[~] python3 hello.py
Hello world!
```

**IDLE.** Możemy również korzystać z IDLE, wbudowanego środowiska Pythona, bezpośrednio w terminalu, co ułatwia szybkie prototypowanie. Uruchamiamy je, wywołując binarny plik Pythona bez żadnych argumentów (```python3```). W IDLE możemy wykonywać proste operacje matematycznie, lub tworzyć i używać zmienne. Rezultat wyrażenia zostanie wyświetlony w kolejnym wierszu, chyba że wynik zostanie przypisany do zmiennej - wtedy nic się nie wyświetli. Możemy również importować biblioteki oraz definiować funkcje i klasy bezpośrednio w IDLE. W dalszej części tutoriala zagłębimy się bardziej w biblioteki, funkcje i klasy. Oto przykład użycia IDLE:

```
[~] python3
Python 3.11.5 (main, Aug 24 2023, 15:09:45)
Type "help", "copyright", "credits" or "license" for more information.
>>> 2 + 4
6
>>> zmienna = 2 + 5
>>> zmienna
7
>>> zmienna + 5
12
>>> print('Hello world!')
Hello world!
```

Kod w Pythonie jest wykonywany od góry do dołu. Jest to ważne do zapamiętania podczas pisania skryptów w Pythonie, ponieważ język nie wie, co jest dalej w skrypcie dopóki do tego nie dojdzie. Jeśli chcielibyśmy wypisać zmienną zamiast wartość bezpośrednio, musi być ona zdefiniowana przed odwołaniem. Na przykład

```
>>> zmienna = 'Tekst do wypisania'
>>> print(zmienna)
Tekst do wypisania
```
Aby wyjść z IDLE, wpisujemy ```exit(0)```. Liczba 0 to kod powrotu (ang. return code), gdzie 0 oznacza, że wszystko jest w porządku (przyjęło się, że wartość różna od 0 wskazuje na błąd).

```
>>> exit(0)
```



## Ćwiczenia do wykonania

1. Napisz skrypt, w którym zdefiniujesz dwie liczby, a następnie z wykorzystaniem funkcji print wypisz ich sumę. Kod wykonaj z pliku.
2. Zrób to samo tylko przy wykorzystaniu Python IDLE.
3. Zapisz i wykonaj z pliku następujący skrypt w którym odwołanie do zmiennej następuje przed jej zadeklarowaniem, sprawdź co się stanie. Następnie popraw skrypt, tak aby wszystko wykonało się prawidłowo.
    ```python
    print(tekst)
    tekst = "Od góry do dołu"
    ```


### Przykładowe rozwiązania

#### Zadanie 1.
```python
liczba1 = 2
liczba2 = 4
print(liczba1 + liczba2)
```
```
$ python3 skrypt.py
6
```

#### Zadanie 2.
```
$ python3 
...
>>> liczba1 = 2
>>> liczba2 = 4
>>> liczba1 + liczba2
6
```

#### Zadanie 3. 
```python
tekst = "Od góry do dołu"
print(tekst)
```
```
Od góry do dołu
```

# 3. Zmienne <a id="zmienne"></a>

**Nazewnictwo zmiennych**

W Pythonie, przyjęte są pewne konwencje i zasady dotyczące nazewnictwa zmiennych. Nazwy zmiennych powinny być zawsze opisowe i łatwe do zrozumienia, co ułatwia czytanie i utrzymanie kodu. Nazwy mogą składać się z liter (zarówno małych, jak i dużych), cyfr oraz znaku podkreślenia `_`, ale nie mogą zaczynać się od cyfry. W Pythonie wielkość liter ma znaczenie, więc `zmienna`, `Zmienna` i `ZMIENNA` będą traktowane jako trzy różne zmienne. Zalecane jest stosowanie notacji `snake_case` dla nazw zmiennych (czyli słowa oddzielane znakiem podkreślenia i pisane małymi literami), na przykład `moja_zmienna`. Stosowanie notacji `CamelCase` jest zazwyczaj zarezerwowane dla nazw klas. Oto kilka przykładów poprawnych nazw zmiennych:

```python
moja_zmienna = 10
wiek_uzytkownika = 21
suma = 5 + 3
```

Należy unikać używania słów kluczowych języka Python (takich jak `if`, `else`, `for`, `while`, `class`, `def`, `return` itp.) jako nazw zmiennych, ponieważ może to prowadzić do nieoczekiwanych błędów i problemów w działaniu programu.


**Łańcuchy znaków**

W Pythonie stringi (łańcuchy znaków) mogą zawierać specjalne sekwencje znaków, które są interpretowane w specyficzny sposób. Te znaki specjalne są poprzedzone odwrotnym ukośnikiem (`\`) i służą do reprezentowania białych znaków, takich jak nowe linie, tabulacje, czy też do umieszczania w stringach znaków specjalnych, takich jak apostrofy czy cudzysłowy, które zwykle mają specjalne znaczenie w Pythonie. Poniżej znajdziesz tabelę z najczęściej używanymi znakami specjalnymi w stringach Pythona:

| Znak Specjalny | Opis                                        |
|----------------|----------------------------------------------|
| `\\`           | Backslash (\)                               |
| `\'`           | Apostrof (')                                |
| `\"`           | Cudzysłów (")                               |
| `\n`           | Nowa linia (linefeed)                       |
| `\t`           | Tabulacja pozioma (horizontal tab)          |
| `\v`           | Tabulacja pionowa (vertical tab)            |


Podstawowo, łańcuchy znaków zapisujemy w następujący sposób:
```python
pytanie = 'Czy łańcuchy znkaów możemy zapisywać tylko w taki sposób?'
odpowiedz = "Nie, łańcuchy znaków możemy pisać również w ten sposób"
```
W Pythonie możemy wykonywać operacje na znakach takie jak:

```python
lancuch = pytanie + "\n" + odpowiedz 
print(lancuch)
```
```
Czy łańcuchy znkaów możemy zapisywać tylko w taki sposób?
Nie, łańcuchy znaków możemy pisać również w ten sposób
```
```python
print((pytanie + "\n")*3)
```
```
Czy łańcuchy znkaów możemy zapisywać tylko w taki sposób?
Czy łańcuchy znkaów możemy zapisywać tylko w taki sposób?
Czy łańcuchy znkaów możemy zapisywać tylko w taki sposób?

```

```python
tekst_specjalny = 'Oto przejście do nowej linii\nTabulator\tApostrof\''
print(tekst_specjalny)
```
```
Oto przejście do nowej linii
Tabulator    Apostrof'
```
Dodatkowo, warto w tym miejscu zwrócić uwagę, że w zależności od wykorzystywanego formatu łańcucha znaku, możemy w jego wnętrzu stosować apostrof lub cudzysłów normalnie (bez *backslash*'a). Przykład:
```python
lanuch_przez_apostrof = '"Cytat"'
lanuch_przez_cudzyslow = "'Cytat'"
print(lancuch_przez_apostrof + " " + lancuch_przez_cudzyslow)
```
```
"Cytat" 'Cytat'
```
Łańcuchy znaków możemy również specjalnie formatować (tzw. format string), co pozwala m.in. na wygodne wypisywanie zmiennych liczbowych w dobranych kontekście tekstowym. W tym celu, przy wypisywaniu, przed otwarciem łańucha, zastosujmy znak ```f```. Przykład:
```python
wynik_dzialania = 2 * 5
print(f'Wynik działania: {wynik_dzialania}')
```
```
Wynik działania: 10
```


**Zmienne liczbowe**

Zmienne liczbowe w Pythonie, podobnie jak w innych językach programowania, mogą przyjmować różne formy. Do najbardziej podstawowych typów należą liczby całkowite (int), reprezentujące liczby bez części dziesiętnej, na przykład `10`. Kolejnym typem są liczby zmiennoprzecinkowe (float), które mogą zawierać część dziesiętną, np. `20.5`. Python obsługuje także liczby zespolone (complex), które składają się z części rzeczywistej i urojonej, na przykład `5+3j`.

```python
dzialanie = 4 * 7
oczekiwany_wynik = 28
```
Co ważne, w Pythonie, w przeciwieństwie do wielu popularnych języków programowania, nie musimy z góry określać typu danej zmiennej liczbowej. Język ten jest dynamicznie typowany, co oznacza, że typ zmiennej jest określany w trakcie wykonania programu, a nie w momencie jej deklaracji. Daje to programistom dużą elastyczność i pozwala na szybsze pisanie kodu, ponieważ nie trzeba martwić się o explicite określanie typów danych. Przykład:

```python
calkowite = 10
zmiennoprzecinkowe = 20.5
zespolone = 5 + 3j
```
Warto również zauważyć, że dynamiczne typowanie w Pythonie umożliwia łatwą zmianę typu zmiennej w trakcie działania programu. Na przykład, jeśli przypiszemy zmiennej, która wcześniej przechowywała liczbę całkowitą, wartość zmiennoprzecinkową, Python bez problemu poradzi sobie z tą zmianą.

**Wartości puste**

W Pythonie, aby reprezentować brak wartości lub niezdefiniowany stan, używa się słowa kluczowego `None`. Jest to specjalny typ danych, który jest często używany w sytuacjach, gdzie chcemy zainicjalizować zmienną, ale nie chcemy jej na razie przypisywać żadnej konkretnej wartości.

```python
wartosc_pusta = None
```

**Zmienne logiczne (boolean)**

Zmienne logiczne w Pythonie są wykorzystywane do reprezentowania wartości prawda/fałsz. Będą one istotne w konstrukcjach sterujących, takich jak instrukcje warunkowe czy pętle. Do reprezentowania wartości logicznych służą słowa kluczowe `True` (prawda) i `False` (fałsz).

```python
czy_oczekiwany_wynik_prawidlowy = True
czy_wartosc_pusta_jest_liczbowa = False
```

**Sprawdzanie i konwersja typów zmiennych**

W Pythonie, ze względu na jego dynamiczną naturę, często pojawia się potrzeba sprawdzenia lub zmiany typu zmiennej. Możemy to zrobić przy wykorzystaniu funkcji `type()`, która zwraca typ obiektu:

```python
liczbowa_calkowita = 10
print(type(liczbowa_calkowita))
```
```
<class 'int'>
```
```python
zmienna_logiczna = True
print(type(zmienna_logiczna))
```
```
<class 'bool'>
```
- Konwersja do liczby całkowitej: Jeśli mamy zmienną z liczbą zmiennoprzecinkową lub łańcuchem znaków reprezentującym liczbę, a potrzebujemy liczby całkowitej, użyjemy funkcji `int()`:
```python
x = 10.5
y = "20"
x = int(x)
y = int(y)
print(f'x = {x}\ty = {y}')
print(f'Oto typ zmiennej x: {type(x)}, a oto typ zmiennej y: {type(y)}.')
```
```
x = 10    y = 20
Oto typ zmiennej x: <class 'int'>, a oto typ zmiennej y: <class 'int'>.
```
- Konwersja do liczby zmiennoprzecinkowej: Jeżeli chcemy zamienić liczbę całkowitą lub tekst na liczbę zmiennoprzecinkową, używamy funkcji `float()`:
```python
a = 15
b = "30.75"
a = float(a)
b = float(b)
print(f'a = {a}\tb = {b}')
print(f'Oto typ zmiennej a: {type(a)}, a oto typ zmiennej b: {type(b)}.')
```
```
a = 15.0    b = 30.75
Oto typ zmiennej a: <class 'float'>, a oto typ zmiennej b: <class 'float'>.
```
- Konwersja do łańcucha znaków: Aby zamienić liczbę całkowitą, zmiennoprzecinkową lub wartość logiczną na łańcuch znaków, używamy funkcji `str()`:
```python
m = 100
n = 3.14
m = str(m)
n = str(n)
print(f'm = {m}\tn = {n}')
print(f'Oto typ zmiennej m: {type(m)}, a oto typ zmiennej n: {type(n)}.')
```
```
m = 100    n = 3.14
Oto typ zmiennej m: <class 'str'>, a oto typ zmiennej n: <class 'str'>.
```

- Konwersja do wartości logicznej: Wartości liczbowe, łańcuchy znaków i inne typy danych można konwertować na wartości logiczne (typ boolean) przy pomocy funkcji `bool()`. Funkcja `bool()` zwraca `True` dla wartości, które są uznawane za prawdziwe, i `False` dla wartości uznawanych za fałszywe. Oto jakie wartości są konwertowane na `False`:
    - Liczba 0
    - Pusty łańcuch znaków: `""` lub `''`
    - Pusta lista: `[]`
    - Pusty słownik: `{}`
    - Pusta krotka (tuple) `()`
    - Wartość `None`

    Wszystkie inne wartości są konwertowane na `True`. Na przykład:

```python
a = 1
print(bool(a))  
```

```
True
```

```python
pusta_lista = []
print(bool(pusta_lista))
```

```
False
```

```python
napis = "Python"
print(bool(napis))
```

```
True
```

**Komentarze**

Komentarze w kodzie źródłowym są niezbędne, aby ułatwić zrozumienie działania programu zarówno dla autora, jak i dla innych programistów, którzy mogą z nim pracować. W Pythonie, aby dodać komentarz, używa się znaku `#`. Tekst po tym znaku w danej linii jest ignorowany przez interpreter Pythona.

```python
# Warto pozostawiać komentarze w kodzie:)
```

## Ćwiczenia do wykonania

1. Zdefiniuj trzy zmienne: jedną typu string, jedną typu int i jedną typu float. Następnie wypisz ich typy przy pomocy funkcji `type()`.

2. Stwórz dwa stringi, a następnie połącz je ze sobą w jeden string. Wypisz wynik.


3. Mając dwie zmienne, `imie` i `wiek`, wypisz zdanie wykorzystując formatowanie stringów, które przy założeniu, że `imie` to "Jan" a `wiek` to 30, będzie wyglądało tak:
    ```
    Podane dane:

    Imię:    "Jan"
    Wiek:    30 lat
    ```

4. Zdefiniuj zmienne typu float, które są blisko tej samej wartości całkowitej, ale z różnymi częściami dziesiętnymi (np. `9.4`, `9.5`, `9.6`). Następnie dokonaj ich konwersji na typ int i obserwuj, jak zachowuje się zaokrąglenie. Dodatkowo dla tych samych liczb sprawdź, jak działa funkcja zaokraglenia `round()`.

### Przykładowe rozwiązania

#### Zadanie 1.

```python
# Zdefiniowanie zmiennych
napis = "Hello world!"
liczba_calkowita = 42
liczba_zmiennoprzecinkowa = 3.14

# Wypisanie typów zmiennych
print(type(napis))
print(type(liczba_calkowita))
print(type(liczba_zmiennoprzecinkowa))
```

```plaintext
<class 'str'>
<class 'int'>
<class 'float'>
```

#### Zadanie 2.

```python
# Definicja stringów
napis1 = "Python "
napis2 = "rządzi!"

# Połączenie stringów
wynik = napis1 + napis2

# Wypisanie wyniku
print(wynik)
```

```plaintext
Python rządzi!
```

#### Zadanie 3.

```python
# Definicja zmiennych
imie = "Jan"
wiek = 30

# Wypisanie zdania z formatowaniem
print(f"Podane dane:\n\nImię:\t\"{imie}\"\nWiek:\t{wiek} lat")
```

```plaintext
Podane dane:

Imię:    "Jan"
Wiek:    30 lat
```

#### Zadanie 4.

```python
# Definicja zmiennych
liczba1 = 9.4
liczba2 = 9.5
liczba3 = 9.6

# Konwersja do int
liczba_calkowita1 = int(liczba1)
liczba_calkowita2 = int(liczba2)
liczba_calkowita3 = int(liczba3)

print(f'Konwersja liczby {liczba1} na int: {liczba_calkowita1}')
print(f'Konwersja liczby {liczba2} na int: {liczba_calkowita2}')
print(f'Konwersja liczby {liczba3} na int: {liczba_calkowita3}')

# Zaokrąglenie
zaokraglona_liczba1 = round(liczba1)
zaokraglona_liczba2 = round(liczba2)
zaokraglona_liczba3 = round(liczba3)

print(f'Zaokrąglenie liczby {liczba1}: {zaokraglona_liczba1}')
print(f'Zaokrąglenie liczby {liczba2}: {zaokraglona_liczba2}')
print(f'Zaokrąglenie liczby {liczba3}: {zaokraglona_liczba3}')
```

```plaintext
Konwersja liczby 9.4 na int: 9
Konwersja liczby 9.5 na int: 9
Konwersja liczby 9.6 na int: 9
Zaokrąglenie liczby 9.4: 9
Zaokrąglenie liczby 9.5: 10
Zaokrąglenie liczby 9.6: 10
```

# 4. Operatory <a id="operatory"></a>

W Pythonie operatory są specjalnymi symbolami lub słowami kluczowymi, które są używane do wykonania operacji na zmiennych i wartościach. W tej sekcji omówimy różne kategorie operatorów oraz ich użycie.

**Operatory Arytmetyczne**

Operatory arytmetyczne służą do przeprowadzania podstawowych operacji matematycznych.

```python
a = 10
b = 3
```

##### Dodawanie `+`
Dodaje dwie wartości.
```python
c = a + b
print("Dodawanie:", c)
```
```
Dodawanie: 13
```

##### Odejmowanie `-`
Odejmuje prawą wartość od lewej.
```python
c = a - b
print("Odejmowanie:", c)
```
```
Odejmowanie: 7
```

##### Mnożenie `*`
Mnoży dwie wartości.
```python
c = a * b
print("Mnożenie:", c)
```
```
Mnożenie: 30
```

##### Dzielenie `/`
Dzieli lewą wartość przez prawą. Wynikiem jest liczba zmiennoprzecinkowa.
```python
c = a / b
print("Dzielenie:", c)
```
```
Dzielenie: 3.3333333333333335
```

##### Reszta z Dzielenia `%`
Zwraca resztę z dzielenia lewej wartości przez prawą.
```python
c = a % b
print("Reszta z dzielenia:", c)
```
```
Reszta z dzielenia: 1
```

##### Potęgowanie `**`
Podnosi lewą wartość do potęgi prawej wartości.
```python
c = a ** b
print("Potęgowanie:", c)
```
```
Potęgowanie: 1000
```

##### Dzielenie Całkowite `//`
Dzieli lewą wartość przez prawą, ale zwraca tylko część całkowitą wyniku.
```python
c = a // b
print("Dzielenie całkowite:", c)
```
```
Dzielenie całkowite: 3
```

**Operatory Logiczne**

Operatory logiczne służą do przeprowadzania operacji logicznych, takich jak AND, OR i NOT.

```python
x = True
y = False
```

##### AND `and`
Zwraca True tylko wtedy, gdy obie wartości są prawdziwe.
```python
print("AND:", x and y)
```
```
AND: False
```

##### OR `or`
Zwraca True, gdy przynajmniej jedna z wartości jest prawdziwa.
```python
print("OR:", x or y)
```
```
OR: True
```

##### NOT `not`
Zwraca przeciwną wartość logiczną.
```python
print("NOT x:", not x)
print("NOT y:", not y)
```
```
NOT x: False
NOT y: True
```

**Operatory Relacji**

Operatory relacji służą do porównywania wartości.

```python
a = 10
b = 20
c = "10"
d = "20"
```

##### Równość `==`
Sprawdza, czy dwie wartości są równe.
```python
print("Równość liczb:", a == b)
print("Równość stringów:", c == d)
print("Równość liczby i (konwertowanego) stringa:", a == int(c))
```
```
Równość liczb: False
Równość stringów: False
Równość liczby i (konwertowanego) stringa: True
```

##### Nierówność `!=`
Sprawdza, czy dwie wartości są różne.
```python
print("Nierówność:", a != b)
```
```
Nierówność: True
```

##### Mniejsze niż `<`
Sprawdza, czy lewa wartość jest mniejsza niż prawa.
```python
print("Mniejsze niż:", a < b)
```
```
Mniejsze niż: True
```

##### Mniejsze bądź równe `<=`
Sprawdza, czy lewa wartość jest mniejsza lub równa prawej.
```python
print("Mniejsze bądź równe:", a <= b)
```
```
Mniejsze bądź równe: True
```

##### Większe niż `>`
Sprawdza, czy lewa wartość jest większa niż prawa.
```python
print("Większe niż:", a > b)
```
```
Większe niż: False
```

##### Większe bądź równe `>=`
Sprawdza, czy lewa wartość jest większa lub równa prawej.
```python
print("Większe bądź równe:", a >= b)
```
```
Większe bądź równe: False
```


## Ćwiczenia do wykonania

1. W dziedzinie cyberbezpieczeństwa, Systemy zarządzania informacjami i zdarzeniami z zakresu bezpieczeństwa (SIEM) są kluczowym elementem infrastruktury bezpieczeństwa. Dla zespołu odpowiedzialnego za bezpieczeństwo, ważne jest zrozumienie, jak koszty zakupu takich systemów wpływają na miesięczny budżet. 
   
   Przyjmijmy, że nasz zespół rozważa zakup subskrypcji na system SIEM, który kosztuje 90 tys. dolarów amerykańskich rocznie. Twoim zadaniem jest obliczenie, ile realnie kwoty ubędzie z miesięcznego budżetu zespołu (w złotówkach), biorąc pod uwagę ten zakup.
   
   Przyjmujemy uproszczony kurs wymiany USD/PLN na poziomie 4.20. 

2. Pracując w dziale cyberbezpieczeństwa, często spotkasz się z sytuacjami, gdzie musisz analizować różne zagrożenia i podejmować decyzje na podstawie dostępnych danych. W tym zadaniu wykorzystamy operatory logiczne `and`, `or` oraz `not`, aby przeanalizować różne scenariusze zagrożeń.

   Przykładowe scenariusze:
   - `zagrozenie_1` oznacza, że system wykrył podejrzane połączenie sieciowe.
   - `zagrozenie_2` oznacza, że system wykrył podejrzane pliki na serwerze.
   - `zagrozenie_3` oznacza, że system wykrył nieautoryzowany dostęp do bazy danych.
    
   Przyjmij, że wykryto następujące wartości dla badanych zagrożeń:
   
    ```python
    zagrozenie_1 = True
    zagrozenie_2 = False
    zagrozenie_3 = True
    ```

   Twoim zadaniem jest sprawdzenie:
   - Czy istnieje jednocześnie podejrzane połączenie sieciowe i podejrzane pliki na serwerze?
   - Czy istnieje podejrzane połączenie sieciowe lub nieautoryzowany dostęp do bazy danych?
   - Czy nie ma żadnego zagrożenia związanego z podejrzanymi plikami na serwerze?

3. Porównywanie stringów:
    - Przypisz wartość "Python" do zmiennej `str1` i wartość "python" do zmiennej `str2`. Sprawdź i wypisz wyniki porównania tych dwóch stringów pod kątem równości, nierówności, a także sprawdź porządek leksykograficzny. Sprawdź również, jak zachowają się te porównania po użyciu funkcji `lower()` na obu stringach.

    - Nastepnie przypisz wartość "apple" do zmiennej `str3` i wartość "banana" do zmiennej `str4`. Sprawdź i wypisz wyniki porównania tych dwóch stringów pod kątem równości, nierówności, a także sprawdź porządek leksykograficzny.

    - Sprawdź teraz, czy `str3` jest prefiksem dla `str4`. W tym celu skorzystaj z funkcji `startswith()`.

    

### Przykładowe rozwiązania

#### Zadanie 1.
```python
roczny_koszt_siema_usd = 90000
kurs_wymiany_usd_pln = 4.20
miesieczny_koszt_siema_pln = (roczny_koszt_siema_usd * kurs_wymiany_usd_pln) / 12
print(f"Miesięczny koszt SIEM w PLN: {miesieczny_koszt_siema_pln:.2f} zł")
```

```
Miesięczny koszt SIEM w PLN: 31500.00 zł
 ```

#### Zadanie 2.

```python
zagrozenie_1 = True
zagrozenie_2 = False
zagrozenie_3 = True
print("Czy istnieje jednocześnie podejrzane połączenie sieciowe i podejrzane pliki na serwerze?", zagrozenie_1 and zagrozenie_2)
print("Czy istnieje podejrzane połączenie sieciowe lub nieautoryzowany dostęp do bazy danych?", zagrozenie_1 or zagrozenie_3)
print("Czy nie ma żadnego zagrożenia związanego z podejrzanymi plikami na serwerze?", not zagrozenie_2)
```
```python
zagrozenie_1 = True
zagrozenie_2 = False
zagrozenie_3 = True
print("Czy zagrożenie 1 i 2 występują razem?", zagrozenie_1 and zagrozenie_2)
print("Czy występuje zagrożenie 1 lub 3?", zagrozenie_1 or zagrozenie_3)
print("Czy brak zagrożenia 2?", not zagrozenie_2)
```

```
Czy zagrożenie 1 i 2 występują razem? False
Czy występuje zagrożenie 1 lub 3? True
Czy brak zagrożenia 2? True
```
#### Zadanie 3.

- część 1.
    
    ```python
    str1 = "Python"
    str2 = "python"
    print("Równość:", str1 == str2)
    print("Nierówność:", str1 != str2)
    print("Porządek leksykograficzny (str1 < str2):", str1 < str2)
    print("Porządek leksykograficzny po lower() (str1 < str2):", str1.lower() < str2.lower())
    ```

    ```
    Równość: False
    Nierówność: True
    Porządek leksykograficzny (str1 < str2): False
    Porządek leksykograficzny po lower() (str1 < str2): False
    ```
- część 2.

    ```python
    str3 = "apple"
    str4 = "banana"
    print("Równość:", str3 == str4)
    print("Nierówność:", str3 != str4)
    print("Porządek leksykograficzny (str3 < str4):", str3 < str4)
    ```

    ```
    Równość: False
    Nierówność: True
    Porządek leksykograficzny (str3 < str4): True
    ```
- część 3.

    ```python
    print("Czy str3 jest prefiksem str4:", str4.startswith(str3))
    ```

    ```
    Czy str3 jest prefiksem str4: False
    ```

# 5. Środowisko pracy <a id="srodowisko-pracy"></a>

Dla efektywnego przeprowadzania projektów nieocenione okazują się specjalistyczne środowiska programistyczne, które usprawniają pracę i pomagają w organizacji kodu. Poniżej opisano dwa podstawowe narzędzia, które mogą znacznie ułatwić pracę z projektami programistycznymi.

**Conda**

Conda to system zarządzania pakietami, który ułatwia instalację, aktualizację i zarządzanie bibliotekami i środowiskami. Proces instalacji jest prosty i można go dokonać, odwiedzając jedną z poniższych stron:
- [Miniconda](https://docs.conda.io/projects/miniconda/en/latest/)
- [Anaconda](https://www.anaconda.com/download/)

Po zainstalowaniu Conda, należy uruchomić ponownie terminal i zweryfikować instalację za pomocą polecenia `conda list`. Jeśli wystąpią problemy, należy sprawdzić konfigurację poprzez `source ~/.bashrc` lub `source ~/.zshrc`. W przypadku korzystania z Miniconda, może być również konieczna instalacja `ipykernel` przy pomocy polecenia `conda install ipykernel`.

Szczegóły tego rozwiązania omówione zostaną w dalszej części tutorial'u.

**Visual Studio Code + Jupyter Notebook**

Visual Studio Code to wszechstronne środowisko, które wspiera również Jupyter Notebooks. Aby zacząć:
1. Odwiedź stronę [Visual Studio Code](https://code.visualstudio.com/docs/setup/linux) i pobierz odpowiednią wersję dla Twojego procesora (z reguły będzie to x64, ale jak ktoś posiada nowego MacBooka to arm64:)).
2. Przenieś pobrany plik do docelowego katalogu i rozpakuj go za pomocą `tar -vxzf ...`.
3. Zainstaluj za pomocą `sudo apt install ./<file>.deb`.
4. Po instalacji uruchom VS Code.

Dalsze kroki to:
- Przejście przez przewodnik 'Getting Started'.
- Instalacja rozszerzeń: Python i Jupyter przez 'Extensions'.
- Instalacja `ipykernel` oraz `pandas` za pomocą `pip` w terminalu.

Aby rozpocząć pracę z Jupyter w VS Code:
1. Utwórz nowy plik wybierając Python/Jupyter.
2. Otwórz nowy terminal przez 'Terminal: New Terminal'.
3. Wybierz środowisko Python dla Jupyter poprzez `/bin/python` (dla wersji Python 3.11).

**Uwaga:** Domyślnie, dla dalszej części tutoriala zaleca się uruchamianie wszelkich stworzonych skrytpów i komponentów standardowo z plików, na razie pomijając Jupyter Notebook - ta technologia przyda się najbardziej w zadaniach analizy danych, których ten tutorial nie uwzględnia.

## Ćwiczenia do wykonania

1. Wykorzystaj terminal w VS Code do wykonania podstawowych operacji.
2. Przećwicz korzystanie z Jupyter Notebook, tworząc nowe komórki i uruchamiając przykładowy kod.


# 6. Listy

Listy w Pythonie to jedne z najbardziej wszechstronnych typów danych. Służą do przechowywania uporządkowanych sekwencji elementów, które mogą być różnych typów.

**Tworzenie List**
Listy tworzymy, umieszczając elementy w nawiasach kwadratowych `[]`, oddzielając je przecinkami.

```python
lista = [1, 2, 3, 4, 5]
print(lista)
```

```
[1, 2, 3, 4, 5]
```

**Dodawanie Elementów**
Do listy można dodawać nowe elementy za pomocą metody `append()`, co powoduje dodanie elementu na jej końcu.

```python
lista.append(6)  # Dodawanie na końcu listy
print(lista)
```

```
[1, 2, 3, 4, 5, 6]
```

**Indexowanie List**
Listy są indeksowane od zera, co oznacza, że pierwszy element znajduje się na pozycji 0.

```python
print(lista[0])  # Pierwszy element
print(lista[-1])  # Ostatni element, indexowanie ujemne
```

```
1
6
```

**Wycinanie List**
Możemy wycinać fragmenty listy, tworząc nową listę, która zawiera tylko wybrane elementy.

```python
print(lista[1:4])  # Elementy od drugiego do czwartego
```

```
[2, 3, 4]
```

**Modyfikacja Elementów**
Możemy zmieniać wartości elementów w liście, odwołując się do nich przez ich indeks.

```python
lista[0] = 10  # Zmiana wartości pierwszego elementu
print(lista)
```

```
[10, 2, 3, 4, 5, 6]
```

**Metody List**
Listy w Pythonie mają wiele metod, które pozwalają na manipulację ich zawartością. Oto kilka przykładów:

| Metoda       | Opis                                               |
|--------------|----------------------------------------------------|
| `append()`   | Dodaje element na końcu listy                      |
| `extend()`   | Rozszerza listę o elementy z innej kolekcji        |
| `insert()`   | Wstawia element na wskazaną pozycję w liście       |
| `remove()`   | Usuwa pierwsze wystąpienie elementu z listy        |
| `pop()`      | Usuwa element na wskazanej pozycji w liście        |
| `clear()`    | Usuwa wszystkie elementy z listy                   |
| `index()`    | Zwraca indeks pierwszego wystąpienia elementu      |
| `count()`    | Zlicza wystąpienia elementu w liście               |
| `sort()`     | Sortuje listę                                      |
| `reverse()`  | Odwraca kolejność elementów w liście               |

**Ograniczenia**
Listy w Pythonie nie mają praktycznie żadnych ograniczeń co do liczby elementów czy typów danych, które mogą przechowywać. Mogą zawierać dowolne typy danych, w tym inne listy, co pozwala na tworzenie list zagnieżdżonych (listy list).

**Indeksowanie List**
Python oferuje zaawansowane techniki indeksowania, w tym indeksowanie ujemne oraz wycinanie (slicing):

- Indeksowanie ujemne pozwala na odwoływanie się do elementów od końca listy, gdzie `-1` oznacza ostatni element, `-2` przedostatni, itd.
- Wycinanie pozwala na uzyskanie nowej listy poprzez wybranie zakresu indeksów, gdzie `lista[start:stop:step]` zwróci nową listę z elementami od indeksu `start` do `stop` (wyłącznie), z krokiem `step`.

```python
lista = [1, 2, 3, 4, 5, 6, 7, 8, 9]
print(lista[-3:])  # Wypisuje trzy ostatnie elementy
print(lista[::2])  # Wypisuje co drugi element listy
```

```
[7, 8, 9]
[1, 3, 5, 7, 9]
```


### Stringi jako Listy

Stringi w Pythonie można traktować jak listy znaków, co oznacza, że można po nich iterować i uzyskiwać dostęp do poszczególnych znaków.

**Iterowanie po Stringu**
Podobnie jak w listach, możemy iterować po stringach za pomocą pętli `for`.
```python
for znak in "Python":
    print(znak)
```
```
P
y
t
h
o
n
```

**Dostęp do Poszczególnych Znaków**
Tak samo jak w listach, możemy uzyskiwać dostęp do poszczególnych znaków w stringu.
```python
napis = "Python"
print(napis[0])  # Pierwszy znak
print(napis[-1])  # Ostatni znak, indexowanie ujemne
```
```
P
n
```

**Wycinki Stringów**
Możemy wycinać fragmenty stringów, tworząc nowe stringi.
```python
print(napis[1:4])  # Znaki od drugiego do czwartego
```
```
yth
```

**Odwracanie Stringów**
Używając wycinków, możemy odwrócić string. Działa to, ponieważ wycinki pozwalają nam określić kierunek iteracji po stringu.
```python
print(napis[::-1])  # Odwrócony string
```
```
nohtyP
```

### Słowniki

Słowniki to struktury danych przechowujące pary klucz-wartość. Poniżej lista najczęściej wykorzystywaych dla nich metod:

| Metoda         | Opis                                              |
|----------------|---------------------------------------------------|
| `get(key)`     | Zwraca wartość dla klucza; `None` jeśli nie istnieje  |
| `items()`      | Zwraca parę klucz-wartość jako nowe widoki słownika  |
| `keys()`       | Zwraca widok kluczy w słowniku                    |
| `values()`     | Zwraca widok wartości w słowniku                  |
| `pop(key)`     | Usuwa klucz i zwraca wartość; błąd jeśli nie istnieje |
| `popitem()`    | Usuwa i zwraca parę (klucz, wartość) jako krotkę  |
| `clear()`      | Usuwa wszystkie elementy ze słownika              |


**Tworzenie Słownika**
Słowniki tworzymy, umieszczając pary klucz-wartość w nawiasach klamrowych `{}`, oddzielając je przecinkami.
```python
slownik = {'klucz1': 'wartosc1', 'klucz2': 'wartosc2'}
print(slownik)
```
```
{'klucz1': 'wartosc1', 'klucz2': 'wartosc2'}
```

**Dodawanie Elementów**
Możemy dodawać nowe pary klucz-wartość do słownika.
```python
slownik['klucz3'] = 'wartosc3'
print(slownik)
```
```
{'klucz1': 'wartosc1', 'klucz2': 'wartosc2', 'klucz3': 'wartosc3'}
```

**Dostęp do Elementów**
Możemy uzyskiwać dostęp do wartości w słowniku, używając kluczy.
```python
print(slownik['klucz1'])
```
```
wartosc1
```

**Modyfikacja Elementów**
Możemy zmieniać wartości przypisane do kluczy w słowniku.
```python
slownik['klucz1'] = 'nowa_wartosc'
print(slownik)
```
```
{'klucz1': 'nowa_wartosc', 'klucz2': 'wartosc2', 'klucz3': 'wartosc3'}
```

## Ćwiczenia do Wykonania

1. Jesteś administratorem systemu i masz za zadanie zaktualizować listę protokołów sieciowych używanych w firmie. Obecna lista protokołów zawiera `["HTTP", "FTP", "SSH", "TELNET"]`. Twoim zadaniem jest usunięcie przestarzałego protokołu "TELNET", dodanie bezpieczniejszego "HTTPS". Na koniec, wyświetl dwa najnowsze protokoły dodane do listy.
2. W działaniach związanych z cyberbezpieczeństwem ważne jest, aby hasła były skomplikowane i trudne do odgadnięcia. Posiadasz hasło `"aB3$7@xZ"`, które chcesz zbadać pod kątem złożoności. Twoim zadaniem jest sprawdzenie, które znaki są alfanumeryczne, a następnie przekształcenie hasła na format, w którym wszystkie litery są wielkie, aby zasymulować wymóg użycia wielkich liter w hasłach. Na koniec odwróć kolejność znaków, aby zobaczyć, jak hasło wyglądałoby w mniej przewidywalnej formie.
3. Masz dany słownik raport, który zawiera informacje o stanie zabezpieczeń różnych usług sieciowych. Twoim zadaniem jest zaktualizowanie tego słownika, aby każda usługa była zmapowana na status "bezpieczny" lub "niebezpieczny". Po zaktualizowaniu słownika, wyświetl status bezpieczeństwa dla usługi "FTP" oraz "SSH". W słowniku raport powinny znaleźć się również usługi "SMTP", "DNS" oraz "HTTPS", gdzie "SMTP" i "DNS" powinny mieć przypisany status "niebezpieczny", a "HTTPS" status "bezpieczny".

### Przykładowe rozwiązania

#### Zadanie 1.
```python
# Definiujemy listę protokołów
protokoly = ["HTTP", "FTP", "SSH", "TELNET"]

# Aktualizacja listy protokołów
protokoly.remove("TELNET")
protokoly.append("HTTPS")


# Wyświetlanie dwóch ostatnich protokołów
print("\nDwa ostatnie protokoły w liście:")
print(protokoly[-2:])
```

```
Dwa ostatnie protokoły w liście:
['SSH', 'HTTPS']
```

#### Zadanie 2.
```python
# Definiujemy hasło
haslo = "aB3$7@xZ"

# Znaki alfanumeryczne
alfanumeryczne = ''.join([znak for znak in haslo if znak.isalnum()])

# Wersja hasła z wielkimi literami
haslo_wielkie = haslo.upper()

# Hasło w odwróconej kolejności
haslo_odwrocone = haslo[::-1]

# Wyniki
print("Znaki alfanumeryczne:", alfanumeryczne)
print("Hasło z wielkimi literami:", haslo_wielkie)
print("Hasło odwrócone:", haslo_odwrocone)
```

```
Znaki alfanumeryczne: aB37xZ
Hasło z wielkimi literami: AB3$7@XZ
Hasło odwrócone: Zx@7$3Ba
```

#### Zadanie 3.
```python
# Słownik raport z rozbudowanym stanem bezpieczeństwa usług
raport = {
    "SSH": "bezpieczny",
    "FTP": "niebezpieczny",
    "HTTP": "bezpieczny",
    "SMTP": "niebezpieczny",
    "DNS": "bezpieczny",
    "HTTPS": "bezpieczny"
}

# Wyświetlenie statusu dla usługi FTP
print("Status bezpieczeństwa dla FTP:", raport["FTP"])

# Wyświetlenie statusu dla usługi SSH
print("Status bezpieczeństwa dla SSH:", raport["SSH"])

```

```
Status bezpieczeństwa dla FTP: niebezpieczny
Status bezpieczeństwa dla SSH: bezpieczny
```

# 7. Instrukcje Warunkowe, Pętle <a id="instrukcje-warunkowe-petle"></a>
## Instrukcje Warunkowe

Instrukcje warunkowe służą do podejmowania decyzji w programie w zależności od spełnienia określonych warunków.

**Po co są instrukcje warunkowe?**
Instrukcje warunkowe pozwalają na wykonywanie różnych fragmentów kodu w zależności od tego, czy dany warunek jest prawdziwy (True) czy fałszywy (False). To podstawowy sposób na kontrolowanie przepływu programu.

**if**
Instrukcja `if` sprawdza warunek, a jeśli jest spełniony, wykonuje zagnieżdżony blok kodu.

```python
x = 10
if x > 5:
    print("x jest większe od 5")
```

```
x jest większe od 5
```

**if-else**
Instrukcja `else` pozwala na wykonanie alternatywnego bloku kodu, gdy warunek w `if` nie jest spełniony.

```python
y = 3
if y > 5:
    print("y jest większe od 5")
else:
    print("y jest mniejsze lub równe 5")
```

```
y jest mniejsze lub równe 5
```

**if-elif-else**
Instrukcja `elif` umożliwia sprawdzenie wielu warunków przed przejściem do bloku `else`.

```python
z = 5
if z > 5:
    print("z jest większe od 5")
elif z == 5:
    print("z jest równe 5")
else:
    print("z jest mniejsze od 5")
```

```
z jest równe 5
```

**Instrukcje z wieloma warunkami**
Warunki można łączyć przy użyciu operatorów logicznych `and`, `or` oraz negować używając `not`. Istnieją również ich odpowiedniki w postaci symboli: `&` dla `and`, `|` dla `or` oraz `!` dla `not`, choć ich użycie wymaga specjalnej uwagi, szczególnie w kontekście operatorów bitowych.

```python
x = 10
y = 5
if x > 5 and y < 10:  # Możemy też napisać: if x > 5 & y < 10
    print("x jest większe od 5 i y jest mniejsze od 10")
```

```
x jest większe od 5 i y jest mniejsze od 10
```

Operator `and` wymaga, aby oba warunki były prawdziwe. Aby wykonać blok kodu, gdy przynajmniej jeden z warunków jest prawdziwy, używamy operatora `or`.

```python
if x > 5 or y > 10:  # Możemy też napisać: if x > 5 | y > 10
    print("Przynajmniej jeden z warunków jest prawdziwy")
```

```
Przynajmniej jeden z warunków jest prawdziwy
```

Operator `not` służy do odwrócenia wyniku warunku.

```python
if not (x < 5):  # Możemy też napisać: if !(x < 5)
    print("x nie jest mniejsze od 5")
```

```
x nie jest mniejsze od 5
```

**Połączenie warunków i priorytety**
Operatory logiczne w Pythonie mają swoje priorytety. `not` ma wyższy priorytet niż `and`, który ma wyższy priorytet niż `or`. Możemy użyć nawiasów, aby zmienić kolejność wykonywania operacji.

```python
if (x > 5 or y > 5) and not (x == 10 and y == 10):
    print("Złożony warunek spełniony")
```

```
Złożony warunek spełniony
```

Zaleca się unikanie zbyt skomplikowanych warunków w jednym wyrażeniu, aby kod był czytelny i łatwy w utrzymaniu.


## Pętle

Pętle umożliwiają wielokrotne wykonanie określonego bloku kodu.

**Pętla while**
Pętla `while` wykonuje blok kodu, dopóki podany warunek jest prawdziwy.

```python
i = 0
while i < 5:
    print(i)
    i += 1
```

```
0
1
2
3
4
```

**Pętla for**
Pętla `for` służy do iterowania po sekwencji (np. liście lub zakresie).

```python
for j in range(5):
    print(j)
```

```
0
1
2
3
4
```

**Pętla for-each**
Pętla `for-each` pozwala na iterowanie bezpośrednio po elementach sekwencji.

```python
lista = [10, 2, 3, 4, 5, 6]
for element in lista:
    print(element)
```

```
10
2
3
4
5
6
```

**Funkcja range()**
Funkcja `range` pozwala na generowanie sekwencji liczb. Może być używana z różnymi parametrami:

- `range(stop)`: generuje liczby od 0 do `stop - 1`
- `range(start, stop)`: generuje liczby od `start` do `stop - 1`
- `range(start, stop, step)`: generuje liczby od `start` do `stop - 1` z krokiem `step`

```python
for num in range(2, 10, 2):
    print(num)
```

```
2
4
6
8
```

**Kontrola przepływu pętli: break i pass**
Instrukcje `break` i `pass` służą do kontroli przepływu wewnątrz pętli:

- `break` natychmiast kończy najbliższą pętlę, w której się znajduje.
- `pass` nie robi nic, jest jak placeholder, pozwalający na zapisanie struktury kodu bez wypełniania bloku kodem.

```python
for val in "string":
    if val == "i":
        pass
    print(val)
```

```
s
t
r
i
n
g
```

```python
for val in "string":
    if val == "i":
        break
    print(val)
```

```
s
t
r
```

## Ćwiczenia do Wykonania

1. Napisz program, który przyjmie liczbę od użytkownika i wypisze, czy liczba ta jest parzysta czy nieparzysta, czy jest dodatnia, ujemna, czy równa zero. Użyj operatorów logicznych do sprawdzenia warunków oraz pętli do weryfikacji czynników liczby pierwszej. W celu przyjęcia danych od użytkiownika należy wykorszystać wbdowaną funkcję `input()`. Przykład wykorzystania funkcji `input()`:
    ```python
    # Prośba o wpisanie imienia użytkownika
    imie = input("Jak masz na imię? ")

    # Wypisanie powitania z imieniem podanym przez użytkownika
    print(f"Cześć, {imie}! Miło Cię poznać.")

    # Prośba o wpisanie wieku użytkownika
    wiek = input("Ile masz lat? ")

    # Konwersja wieku z tekstu na liczbę całkowitą
    wiek = int(wiek)

    # Wypisanie informacji zwrotnej z wiekiem użytkownika
    print(f"Okej, masz {wiek} lat. To znaczy, że urodziłeś się w roku {2023 - wiek}.")
    ```

2. Napisz program w języku Python, który symuluje proces sprawdzania stanu portów na serwerze. Program powinien przejrzeć porty od 1 do 50 i dla każdego z nich wykonać następujące czynności:
    - Jeżeli numer portu jest **parzysty**, uznaj port za "zamknięty" i wydrukuj informację o tym.
    - Jeżeli numer portu jest **nieparzysty**, uznaj port za "otwarty" i wydrukuj informację.
    - Gdy program natrafi na port o numerze **22** (SSH), powinien wydrukować komunikat "Bezpieczny port SSH znaleziony, kontynuuję skanowanie..." i kontynuować działanie bez przerywania pętli.
    - Jeśli program dojdzie do portu o numerze **50**, powinien wydrukować "Zakończono skanowanie portów" i zakończyć działanie programu.

    Wykorzystaj pętlę `for` i funkcję `range()`.

### Przykładowe rozwiązania

#### Zadanie 1.

```python
# Prośba o wpisanie liczby przez użytkownika
tekst_wejsciowy = input("Podaj liczbę: ")

# Konwersja wprowadzonego tekstu na liczbę całkowitą
liczba = int(tekst_wejsciowy)

# Sprawdzanie, czy liczba jest równa zero
if liczba == 0:
    print("Liczba jest równa zero")
else:
    # Liczba jest różna od zera, sprawdzamy czy jest dodatnia czy ujemna
    if liczba > 0:
        print("Liczba jest dodatnia")
    else:
        print("Liczba jest ujemna")
    
    # Sprawdzanie parzystości liczby
    if liczba % 2 == 0:
        print("Liczba jest parzysta")
    else:
        print("Liczba jest nieparzysta")

```

```
Podaj liczbę: 7    <-- przykład
Liczba jest dodatnia
Liczba jest nieparzysta
```

#### Zadanie 2.

```python
for port in range(1, 51):  # Przechodzenie przez listę portów od 1 do 50
    if port == 22:  # Jeśli port to 22
        print("Bezpieczny port SSH znaleziony, kontynuuję skanowanie...")
    elif port % 2 == 0:  # Jeśli numer portu jest parzysty
        print(f"Port {port} jest zamknięty.")
    else:  # Jeśli numer portu jest nieparzysty
        print(f"Port {port} jest otwarty.")
    
    if port == 50:  # Jeśli port to 50
        print("Zakończono skanowanie portów")
        break

```

```
Port 1 jest otwarty.
Port 2 jest zamknięty.
Port 3 jest otwarty.
Port 4 jest zamknięty.
...
Bezpieczny port SSH znaleziony, kontynuuję skanowanie...
...
Port 48 jest zamknięty.
Port 49 jest otwarty.
Port 50 jest zamknięty.
Zakończono skanowanie portów
```


# 8. Funkcje <a id="funkcje"></a>

Funkcje w Pythonie pozwalają na zdefiniowanie bloku kodu, który wykonuje określone akcje, produkuje wartości i opcjonalnie zwraca jedną lub więcej z tych wartości. Dzięki funkcjom, możemy ponownie używać kodu i pracować z naszymi danymi bardziej efektywnie, bez konieczności ponownego wynajdywania koła.

**Definiowanie Funkcji**

Aby zdefiniować funkcję, używamy słowa kluczowego `def`, po którym następuje nazwa funkcji, nawiasy (które mogą zawierać parametry) oraz dwukropek. Ciało funkcji zaczyna się w nowej linii i jest wcięte.

**Prosta Funkcja**

Poniżej znajduje się przykład prostej funkcji, która zwraca wartość parametru powiększoną o jeden.

```python
def dodaj_jeden(x):
    return x + 1
```

Aby użyć tej funkcji, wywołujemy ją, podając argument w nawiasach:

```python
wynik = dodaj_jeden(5)
print(wynik)
```
```
6
```

**Parametry Funkcji**

Funkcje mogą przyjmować parametry, które są wartościami przekazywanymi do funkcji w celu przetworzenia. Parametry te mogą być dowolnego typu.

Przykład funkcji przyjmującej dwa parametry:

```python
def dodaj(x, y):
    return x + y
```

Wywołanie funkcji z dwoma argumentami:

```python
wynik = dodaj(2, 3)
print(wynik)
```
```
5
```

**Zwracanie Wartości z Funkcji**

Słowo kluczowe `return` służy do zwracania wartości z funkcji. Funkcja zwraca sterowanie do miejsca, z którego została wywołana, a także opcjonalnie zwraca wartość.

```python
def pomnoz_przez_dwa(x):
    return x * 2
```

Przykład użycia funkcji:

```python
wynik = pomnoz_przez_dwa(4)
print(wynik) 
```
```
8
```

**Funkcje Jako Argumenty Innych Funkcji**

Funkcje w Pythonie są obiektami pierwszej klasy, co oznacza, że możemy przekazywać je jako argumenty do innych funkcji, zwracać je z funkcji, przypisywać je do zmiennych i przechowywać je w innych strukturach danych.

Przykład funkcji, która przyjmuje inną funkcję jako argument:

```python
def wykonaj_dzialanie(funkcja, argument):
    return funkcja(argument)
```

Użycie tej funkcji z funkcją `dodaj_jeden`:

```python
wynik = wykonaj_dzialanie(dodaj_jeden, 5)
print(wynik)
```
```
6
```

## Ćwiczenia do Wykonania

1. Napisz funkcję `sprawdz_silne_haslo`, która przyjmuje hasło jako argument i zwraca `True`, jeśli hasło spełnia następujące kryteria dla silnego hasła:
    - ma co najmniej 8 znaków długości,
    - zawiera co najmniej jedną cyfrę,
    - zawiera co najmniej jedną wielką literę.

    Wykorzystaj funkcje `len()`, `any()` oraz metody `isdigit()` i `isupper()` do sprawdzenia tych warunków w hasle.

2. Napisz funkcję `rejestruj_aktywnosc`, która przyjmuje nazwę użytkownika oraz dowolną liczbę czasów logowania (reprezentowanych jako stringi z czasem) i drukuje komunikat z najwcześniejszym i najpóźniejszym czasem logowania dla danego użytkownika. Wykorzystaj funkcje `min()` i `max()` do znalezienia odpowiednich czasów.

    Użyj formatowania stringów, aby wygenerować czytelny komunikat, na przykład:
`"Użytkownik: [nazwa], Pierwsze logowanie: [czas], Ostatnie logowanie: [czas]".`

    **Uwaga**: Godziny w formie stringa, takie jak "08:00" czy "12:00", są porównywalne w Pythonie, ponieważ porównanie stringów odbywa się alfabetycznie, znak po znaku od lewej do prawej. W kontekście godzin w formacie HH:MM, jeśli stringi są w tym samym formacie, ich porównanie alfabetyczne (leksykograficzne) jest równoważne porównaniu czasowemu pod warunkiem, że oba stringi mają tę samą długość i są poprawnie sformatowane.
    
### Przykładowe rozwiązania

#### Zadaine 1.

```python
def sprawdz_silne_haslo(haslo):
    return (len(haslo) >= 8 and
            any(znak.isdigit() for znak in haslo) and
            any(znak.isupper() for znak in haslo))

# Testowanie funkcji
print(sprawdz_silne_haslo("SilneHaslo1")) 
print(sprawdz_silne_haslo("haslo"))       
```

```
True
False
```

#### Zadanie 2.

```python
def rejestruj_aktywnosc(nazwa_uzytkownika, czasy_logowania):
    najwczesniejsze_logowanie = min(czasy_logowania)
    najpozniejsze_logowanie = max(czasy_logowania)
    print(f"Użytkownik: {nazwa_uzytkownika}, Pierwsze logowanie: {najwczesniejsze_logowanie}, Ostatnie logowanie: {najpozniejsze_logowanie}")

# Testowanie funkcji
rejestruj_aktywnosc("jankowalski", ["08:00", "12:00", "18:00"])

```

```
Użytkownik: jankowalski, Pierwsze logowanie: 08:00, Ostatnie logowanie: 18:00
```

# 9. Klasy <a id="klasy"></a>

Programowanie obiektowe to paradygmat programowania, który wykorzystuje "obiekty" – struktury danych składające się z pól danych (nazywanych atrybutami) i procedur, znanych jako metody. W Pythonie, klasy są podstawowym narzędziem do implementacji struktur danych i zachowań obiektów, będąc fundamentem dla programowania obiektowego.

**Czym są Klasy?**

Klasa w Pythonie to rodzaj "przepisu" lub "szablonu", który definiuje jak będą tworzone obiekty (instancje klasy). Klasy opisują stan (atrybuty) i zachowanie (metody), które będą współdzielone przez wszystkie instancje.

```python
class NazwaKlasy:
    # definicje zmiennych i metod
```

**Konstruktor Klasy**

Konstruktor to specjalna metoda w klasie, która jest automatycznie wywoływana, kiedy tworzymy nowy obiekt tej klasy. W Pythonie, konstruktor zdefiniowany jest przez metodę `__init__`, która inicjalizuje nową instancję klasy.

```python
class PrzykladowaKlasa:
    def __init__(self, param1, param2):
        self.atrybut1 = param1
        self.atrybut2 = param2
```

**Metody Klasy**

Metody to funkcje zdefiniowane wewnątrz klasy, które określają zachowania i akcje, które może wykonać instancja klasy. Są one wywoływane na instancjach obiektów i często działają na atrybutach tych obiektów.

```python
class PrzykladowaKlasa:
    # Konstruktor klasy
    def __init__(self, param1, param2):
        self.atrybut1 = param1
        self.atrybut2 = param2
    
    # Metoda klasy
    def metoda_klasy(self):
        print(f"Atrybut1: {self.atrybut1}, Atrybut2: {self.atrybut2}")
```

**Tworzenie Obiektów**

Tworzenie obiektu, zwane także instancjacją, polega na wywołaniu klasy jako funkcji, przekazując do niej argumenty wymagane przez konstruktor.

```python
obiekt = PrzykladowaKlasa("wartość1", "wartość2")
```

**Dostęp do Atrybutów i Metod**

Po stworzeniu obiektu, do jego atrybutów i metod dostęp uzyskujemy za pomocą operatora kropki `.`.

```python
print(obiekt.atrybut1)  # Wypisze wartość atrybut1
obiekt.metoda_klasy()   # Wywoła metodę klasy i wypisze wartości atrybutów
```

**\_\_main__**

W Pythonie, blok `if __name__ == "__main__":` jest używany do wskazania, że kod powinien być uruchomiony tylko wtedy, gdy skrypt jest wykonywany bezpośrednio, a nie importowany jako moduł do innego skryptu. Zmienna `__name__` w Pythonie jest specjalną wbudowaną zmienną, która przyjmuje wartość `"__main__"` w skrypcie, który jest głównym programem.


### Przykład wykorzystania:

```python
def funkcja():
    print("Funkcja została uruchomiona!")

def funkcja_glowna():
    print("Skrypt uruchomiony bezpośrednio")
    funkcja()

if __name__ == "__main__":
    funkcja_glowna()
```

W powyższym skrypcie, jeśli uruchomisz ten plik bezpośrednio, na przykład przez wywołanie `python skrypt.py`, zobaczysz oba wydruki:

```
Skrypt uruchomiony bezpośrednio
Funkcja została uruchomiona!
```


Ale jeśli ten sam plik zostanie zaimportowany z innego skryptu Pythona za pomocą `import skrypt`, nie zostanie wydrukowane nic z powyższego, ponieważ blok `if __name__ == "__main__":` nie zostanie wykonany. Funkcja `main()` zostanie uruchomiona tylko wtedy, gdy skrypt jest głównym programem.



## Ćwiczenia do wykonania

1. Stwórz klasę Firewall, która będzie przechowywać zasady (reguły) dotyczące ruchu sieciowego i oceniać, czy próba połączenia jest dozwolona, czy zablokowana. Klasa powinna mieć następujące metody:
    - \_\_init__(self): inicjalizacja listy zasad (każda zasada to słownik z kluczami: 'ip', 'port' i 'akcja'),
    - dodaj_zasade(self, ip, port, akcja): dodaje nową zasadę do firewalla,
    - sprawdz_polaczenie(self, ip, port): zwraca True, jeśli połączenie jest dozwolone, False jeśli zablokowane, na podstawie zasad.

2. Zaprojektuj klasę Uzytkownik, która będzie zarządzać informacjami o użytkownikach w systemie bezpieczeństwa. Klasa powinna posiadać:
    - Atrybuty instancji: login, haslo, email, poziom_dostepu (gdzie poziom dostępu określa uprawnienia użytkownika w systemie, np. 'admin', 'user', 'guest').
    - Metodę \_\_init__(self, login, haslo, email, poziom_dostepu): inicjalizacja nowego użytkownika z podanymi atrybutami,
    - Metodę zmien_haslo(self, stare_haslo, nowe_haslo): metoda pozwala zmienić hasło użytkownika, ale tylko jeśli stare haslo jest poprawne,
    - Metodę \_\_str__(self): która zwraca informacje o użytkowniku (bez hasła) w czytelnej formie,
    - Metodę zresetuj_haslo(self): resetuje hasło do domyślnej wartości, np. "Password123", i zwraca informację o zmianie.
    
### Przykładowe rozwiązania

#### Zadanie 1.
```python
class Firewall:
    def __init__(self):
        self.zasady = []

    def dodaj_zasade(self, ip, port, akcja):
        self.zasady.append({'ip': ip, 'port': port, 'akcja': akcja})

    def sprawdz_polaczenie(self, ip, port):
        for zasada in self.zasady:
            if zasada['ip'] == ip and zasada['port'] == port:
                return zasada['akcja'] == 'dozwol'
        return False  # Domyślnie blokujemy połączenie, jeśli nie ma zasady

# Testowanie klasy
fw = Firewall()
fw.dodaj_zasade("192.168.1.1", "22", "dozwol")
fw.dodaj_zasade("192.168.1.2", "80", "zablokuj")

print(fw.sprawdz_polaczenie("192.168.1.1", "22"))
print(fw.sprawdz_polaczenie("192.168.1.2", "80")) 

```

```
True
False
```

#### Zadanie 2.
```python
class Uzytkownik:
    def __init__(self, login, haslo, email, poziom_dostepu):
        self.login = login
        self.haslo = haslo
        self.email = email
        self.poziom_dostepu = poziom_dostepu

    def zmien_haslo(self, stare_haslo, nowe_haslo):
        if self.haslo == stare_haslo:
            self.haslo = nowe_haslo
            return "Hasło zostało zmienione."
        else:
            return "Błędne stare hasło, nie zmieniono hasła."

    def __str__(self):
        return f"Użytkownik: {self.login}, Email: {self.email}, Poziom dostępu: {self.poziom_dostepu}"

    def zresetuj_haslo(self):
        self.haslo = "Password123"
        return "Hasło zostało zresetowane do domyślnej wartości."

# Testowanie klasy
uzytkownik = Uzytkownik("jnowak", "BezpieczneHaslo123", "jnowak@example.com", "user")
print(uzytkownik)
print(uzytkownik.zmien_haslo("BezpieczneHaslo123", "NoweHaslo321"))
print(uzytkownik.zresetuj_haslo())

```

```
Użytkownik: jnowak, Email: jnowak@example.com, Poziom dostępu: user
Hasło zostało zmienione.
Hasło zostało zresetowane do domyślnej wartości.
```

# 10. Biblioteki i środowiska wirtualne <a id="biblioteki-i-srodowiska-wirtualne"></a>

**Importowanie Bibliotek w Pythonie**

W Pythonie, aby korzystać z funkcji dostarczanych przez bibliotekę, najpierw musimy ją zaimportować za pomocą instrukcji `import`. Na przykład:

```python
import datetime
```

`datetime` to moduł wbudowany w Pythonie, który dostarcza funkcje do pracy z datami i czasem. Pozwala na tworzenie obiektów reprezentujących datę, czas, a nawet kombinację obu.

Przykład użycia:

```python
from datetime import datetime

aktualny_czas = datetime.now()
print(aktualny_czas)
```

### Zarządzanie pakietami z `pip`

Python Package Index (PyPI) to repozytorium oprogramowania dla języka programowania Python. `pip` jest narzędziem, które pozwala instalować i zarządzać pakietami z tego repozytorium.

Aby zainstalować bibliotekę, użyj:

```bash
pip install nazwa_pakietu
```

Jeśli chcesz zainstalować konkretną wersję, zrób to tak:

```bash
pip install nazwa_pakietu==wersja
```

Aby zaktualizować pakiet, użyj:

```bash
pip install --upgrade nazwa_pakietu
```

Możesz też odinstalować pakiet za pomocą:

```bash
pip uninstall nazwa_pakietu
```

Aby zobaczyć listę zainstalowanych pakietów:

```bash
pip list
```

**`requirements.txt`**

Plik `requirements.txt` jest standardem dla Pythona, który pozwala na śledzenie zależności projektu. Aby wygenerować ten plik, użyj polecenia `freeze`:

```bash
pip freeze > requirements.txt
```

To polecenie zapisze listę wszystkich zainstalowanych pakietów wraz z ich wersjami do pliku `requirements.txt`.

**Instalacja zależności z `requirements.txt`**

Aby zainstalować zależności z pliku `requirements.txt`, użyj:

```bash
pip install -r requirements.txt
```

### Zarządzanie pakietami z `conda`

Conda to system zarządzania pakietami, który jest używany głównie dla języka Python, ale może również zarządzać pakietami z innych języków. Conda pozwala na tworzenie odizolowanych środowisk, które mogą mieć różne wersje pakietów.

Podstawowe polecenia `conda`:

Aby zainstalować pakiet:

```bash
conda install nazwa_pakietu
```

Aby zainstalować pakiet z określonego kanału:

```bash
conda install -c kanal nazwa_pakietu
```

Aktualizowanie pakietu:

```bash
conda update nazwa_pakietu
```

Odinstalowywanie pakietu:

```bash
conda remove nazwa_pakietu
```

Wyszukiwanie pakietów:

```bash
conda search nazwa_pakietu
```

Aby zobaczyć listę zainstalowanych pakietów w aktywnym środowisku:

```bash
conda list
```

### Porównanie `pip` i `conda`

- `pip` jest standardowym menedżerem pakietów dla Pythona, który instaluje pakiety z PyPI.
- `conda` może zarządzać pakietami nie tylko dla Pythona. Conda może również tworzyć izolowane środowiska, co jest przydatne w przypadku różnych projektów z różnymi zależnościami.
- `pip` instaluje pakiety w ramach już istniejącego środowiska Pythona, `conda` może tworzyć nowe środowiska z dedykowanymi wersjami Pythona i pakietów.
- Pliki `requirements.txt` są używane z `pip` do śledzenia zależności projektu, podczas gdy `conda` używa pliku `environment.yml` do tego samego celu.

### Przykłady z pakietami `requests` i `BeautifulSoup4` (`bs4`)

**Instalacja pakietów**

Instalacja za pomocą `pip`:

```bash
pip install requests
pip install beautifulsoup4
```

Instalacja za pomocą `conda`:

```bash
conda install requests
conda install -c anaconda beautifulsoup4
```

**Przykład użycia**

Użycie `requests` do pobrania treści strony internetowej i `BeautifulSoup4` do jej przetwarzania:

```python
import requests
from bs4 import BeautifulSoup

url = 'https://www.przykladowa-strona.com'
response = requests.get(url)
soup = BeautifulSoup(response.text, 'html.parser')

# Znajdź wszystkie paragrafy na stronie
paragrafy = soup.find_all('p')

for p in paragrafy:
    print(p.text)
```

### Wirtualne środowiska Pythona (`venv`)

Wirtualne środowiska w Pythonie (`venv`) pozwalają na tworzenie izolowanych środowisk dla poszczególnych projektów Pythonowych. Dzięki temu, możesz zarządzać zależnościami projektów niezależnie od siebie, co pomaga unikać konfliktów i zapewnia większą kontrolę nad pakietami i ich wersjami.

Aby stworzyć nowe środowisko, wykonaj:

```bash
python3 -m venv nazwa_srodowiska
```

Aby aktywować środowisko, użyj:

```bash
source nazwa_srodowiska/bin/activate
```

Gdy środowisko jest aktywne, możesz zarządzać pakietami z użyciem `pip`. Aby śledzić zależności projektu, wyeksportuj zainstalowane pakiety do `requirements.txt`:

```bash
pip freeze > requirements.txt
```

Aby zainstalować pakiety z pliku `requirements.txt` w aktywnym środowisku:

```bash
pip install -r requirements.txt
```
Aby dezaktywować aktualne środowisko venv:

```bash
deactivate
```


### Środowiska Conda (`conda env`)

Conda jest potężnym narzędziem do zarządzania środowiskami, które pozwala na obsługę różnych wersji Pythona i pakietów, co jest niezwykle przydatne przy pracy nad wieloma projektami wymagającymi różnych konfiguracji.

Aby utworzyć nowe środowisko conda z określoną wersją Pythona:

```bash
conda create --name nazwa_srodowiska python=3.x
```

Aby aktywować środowisko conda:

```bash
conda activate nazwa_srodowiska
```

Możesz eksportować środowisko do pliku `environment.yml`, co pozwala na łatwe replikowanie środowiska na innych maszynach:

```bash
conda env export > environment.yml
```

Tworzenie środowiska z pliku `environment.yml`:

```bash
conda env create -f environment.yml
```

Conda pozwala na tworzenie kompleksowych i łatwo przenaszalnych środowisk, co czyni ją idealnym narzędziem dla projektów wymagających specyficznych i skomplikowanych konfiguracji zależności. Aby dezaktywować aktualnie używane środiwsko conda:
```bash
conda deactivate
```


## Ćwiczenia do wykonania

1. Rozpocznij od zainstalowania biblioteki `click` i przy jej pomocy stwórz prosty program, który poprosi użytkownika o wprowadzenie swojego imienia i wyświetli personalizowane powitanie (znajdź i sprawdź dokumentację biblioteki).
2. Stwórz wirtualne środowisko za pomocą `venv`, zainstaluj w nim pakiet `numpy`, a następnie wygeneruj plik `requirements.txt`. Podejrzyj wygenerowany plik.
3. Użyj Conda do stworzenia nowego środowiska, zainstaluj w nim pakiet `numpy` i wyeksportuj listę pakietów do pliku `environment.yml`. Podejrzyj wygenerowany plik.
4. Wykorzystaj biblioteki `requests` i `BeautifulSoup` do pobrania i wyświetlenia tytułu strony internetowej. Zainstaluj wymagane pakiety, jeśli nie są jeszcze zainstalowane. Znajdź i skorzystaj z ogólnodostępnej dokumentacji wskazanych bibliotek.

### Przykładowe rozwiązania


#### Zadanie 1.
```python
import click

@click.command()
def welcome():
    name = click.prompt('Proszę wpisz swoje imię')
    click.echo(f'Witaj, {name}!')

if __name__ == "__main__":
    welcome()
```

```
$ python welcome.py
Proszę wpisz swoje imię: Marek
Witaj, Marek!
```
#### Zadanie 2.
```bash
# Tworzenie wirtualnego środowiska
python -m venv myenv
# Aktywacja środowiska w systemie Unix/macOS
source myenv/bin/activate 
# Aktywacja środowiska w systemie Windows
myenv\Scripts\activate
# Instalacja pakietów
pip install requests
# Generowanie pliku requirements.txt
pip freeze > requirements.txt
# (Opcjonalnie) wyłączenie aktualnego środowiska venv
deactivate
```

```
$ cat requirements.txt
requests==x.x.x    <-- tu będzie konkretna wersja
```

#### Zadanie 3.
```bash
# Tworzenie nowego środowiska Conda
conda create --name mycondaenv
# Aktywowanie środowiska
conda activate mycondaenv
# Instalacja pakietu numpy
conda install numpy
# Eksportowanie listy pakietów do pliku
conda env export > environment.yml
# (Opcjonalnie) wyłączenie aktualnego środowiska conda
conda deactivate
```

```
$ cat environment.yml
name: mycondaenv
dependencies:
  - numpy=x.x.x
  - pip:
    - some-package==x.x.x
```

#### Zadanie 4.
```python
import requests
from bs4 import BeautifulSoup

# Przykładowy URL do pobrania danych
url = 'https://www.example.com'

# Pobranie danych ze strony
response = requests.get(url)

# Utworzenie obiektu BeautifulSoup
soup = BeautifulSoup(response.text, 'html.parser')

# Wyszukanie tytułu i wyświetlenie go
title = soup.find('title').text
print(f'Tytuł strony: {title}')
```

```
Tytuł strony: Example Domain
```

# 11. Wyrażenia regularne w Pythonie (RegEx) <a id="wyrazenia-regularne-w-pythonie-regex"></a>

Wyrażenia regularne, zwane też regexami, to sekwencje znaków używane do wyszukiwania i zastępowania wzorców w tekście. Dzięki nim można np. sprawdzić, czy ciąg znaków wygląda jak adres email, numer telefonu, czy zawiera tylko cyfry.

**Dlaczego warto ich używać?**

- **Automatyzacja**: Przetwarzaj teksty szybko, wykonując złożone zadania wyszukiwania i zastępowania.
- **Walidacja danych**: Sprawdź, czy dane wejściowe pasują do oczekiwanego formatu.
- **Wyszukiwanie**: Znajdź wszystkie wystąpienia określonego wzorca w tekście.
- **Transformacja tekstu**: Zmień format danych wejściowych na żądany format wyjściowy.

### Podstawy regex w Pythonie

W Pythonie, wyrażenia regularne obsługiwane są przez moduł `re`, który należy zaimportować przed użyciem.

```python
import re
```

**Przykłady podstawowych operacji**

1. **Wyszukiwanie wzorca**:
   ```python
   tekst = "Nauka Pythona jest zabawna!"
   wzorzec = 'Pythona'
   pasuje = re.search(wzorzec, tekst)
   if pasuje:
       print("Znaleziono wzorzec!")
   ```

2. **Podział tekstu**:
   ```python
   tekst = "Nauka-Pythona-jest-zabawna!"
   podzielony_tekst = re.split('-', tekst)
   print(podzielony_tekst)
   ```

3. **Zastępowanie tekstu**:
   ```python
   tekst = "Nauka Pythona jest zabawna!"
   tekst_zastapiony = re.sub('zabawna', 'super', tekst)
   print(tekst_zastapiony)
   ```

**Tabela z różnymi znakami w regexie**

| Znak | Opis                                    |
|------|-----------------------------------------|
| `.`  | Dopasowuje dowolny znak oprócz nowej linii (domyślnie) |
| `^`  | Dopasowuje początek linii                      |
| `$`  | Dopasowuje koniec linii                        |
| `*`  | Dopasowuje 0 lub więcej wystąpień poprzedzającego elementu |
| `+`  | Dopasowuje 1 lub więcej wystąpień poprzedzającego elementu |
| `?`  | Oznacza, że poprzedzający element jest opcjonalny (0 lub 1 wystąpienie) |
| `{n}`| Dopasowuje dokładnie `n` wystąpień poprzedzającego elementu |
| `{n,}`| Dopasowuje `n` lub więcej wystąpień poprzedzającego elementu |
| `{n,m}`| Dopasowuje od `n` do `m` wystąpień poprzedzającego elementu |
| `[]` | Zestaw znaków. Dopasowuje każdy znak zawarty w nawiasach |
| `[^]`| Zaprzeczenie zestawu znaków. Dopasowuje każdy znak niezawarty w nawiasach |
| `\|`  | Alternatywa, dopasowuje każdy z podanych wzorców |
| `\b` | Dopasowuje granicę słowa |
| `\B` | Dopasowuje pozycję, która nie jest granicą słowa |
| `\d` | Dopasowuje dowolną cyfrę (odpowiednik [0-9]) |
| `\D` | Dopasowuje dowolny znak, który nie jest cyfrą |
| `\s` | Dopasowuje dowolny biały znak (np. spacja, tabulacja) |
| `\S` | Dopasowuje dowolny znak niebędący białym znakiem |
| `\w` | Dopasowuje dowolny znak słowny (odpowiednik [a-zA-Z0-9_]) |
| `\W` | Dopasowuje dowolny znak, który nie jest znakiem słownym |


**Przykład z wykorzystaniem wyrażeń regularnych**

Załóżmy, że chcemy znaleźć wszystkie adresy email w dużym dokumencie tekstowym. Adresy email mają charakterystyczny wzorzec, składają się z lokalnej części, symbolu `@`, oraz domeny. Poniższy regex może być użyty do ich wyszukiwania:

```python
import re

tekst = "Kontakt: jankowalski@example.com lub support@example.net"
pattern = r'[A-Za-z]+@[A-Za-z]+\.[A-Za-z0-9]+'
adresy_email = re.findall(pattern, tekst)

print(adresy_email)
```

```plaintext
['jan.kowalski@example.com', 'support@example.net']
```

## Ćwiczenia do wykonania

1. Twoim zadaniem jest napisanie wyrażenia regularnego, które wykryje każde użycie `sudo` w pliku z logami systemowymi. Użycie `sudo` może wskazywać na próby wykonania komend z uprawnieniami administratora, co w niektórych przypadkach może być niebezpieczne. Przykładowe logi do testów:
    ```plaintext
    Użytkownik1 uruchomił komendę: ls -la /home/użytkownik
    Użytkownik2 uruchomił komendę: rm -rf /home/użytkownik
    Użytkownik3 uruchomił komendę: sudo rm -rf /
    ```
2. Atakujący często tworzą adresy e-mail z domenami najwyższego poziomu, które są rzadko używane w celu uniknięcia wykrycia. Twoim zadaniem jest napisanie wyrażenia regularnego, które znajdzie adresy e-mail zakończone na .xyz w dowolnym tekście. W celu wykonanania zadania możesz skorzystać z narzędzi online. Przykładowy tekst do przeszukania:
    ```plaintext
    Kontaktuj się z nami! Oto kilka sposobów, aby to zrobić:
    - E-mail: contact@example.com
    - Wsparcie: support@ourcompany.com
    - Incydenty: incidents@unknown.xyz
    - Marketing: promo@offers.xyz
    ```

### Przykładowe rozwiązania

#### Zadanie 1.

```python
import re

logi = """
Użytkownik1 uruchomił komendę: ls -la /home/użytkownik
Użytkownik2 uruchomił komendę: rm -rf /home/użytkownik
Uwaga! Użytkownik3 uruchomił komendę: sudo rm -rf /
"""

pattern = r'\bsudo\b'
matches = re.findall(pattern, logi)

if matches:
    print("Znaleziono użycie 'sudo' w logach.")
else:
    print("Nie znaleziono użycia 'sudo' w logach.")
```

```plaintext
Znaleziono użycie 'sudo' w logach.
```

#### Zadanie 2.
```python
import re

text = """
Kontaktuj się z nami! Oto kilka sposobów, aby to zrobić:
- E-mail: contact@example.com
- Wsparcie: support@ourcompany.com
- Incydenty: security_alert@unknown.xyz
- Marketing: promo@offers.xyz
"""

# Wzorzec do wyszukiwania adresów e-mail zakończonych na .xyz
pattern = r'\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[xX][yY][zZ]\b'

matches = re.findall(pattern, text)

if matches:
    print("Znaleziono podejrzane adresy e-mail:")
    for match in matches:
        print(match)
else:
    print("Nie znaleziono podejrzanych adresów e-mail.")

```

```
Znaleziono podejrzane adresy e-mail:
security_alert@unknown.xyz
promo@offers.xyz
```



# 12. Pisanie stylowego kodu (PEP8) <a id="pisanie-stylowego-kodu-pep8"></a>

Styl pisania kodu jest kluczowy dla zachowania czytelności i łatwości utrzymania projektów programistycznych. W Pythonie istnieje oficjalny przewodnik stylu, znany jako PEP8, który zawiera zalecenia dotyczące formatowania kodu Python. Poniżej kilka kluczowych zasad z tego przewodnika:

**Nazewnictwo Zmiennych**

- Zmienne powinny być nazwane małymi literami, a poszczególne słowa powinny być oddzielone podkreślnikiem. Używamy konwencji `snake_case`.
  
```python
liczba_studentow = 25
srednia_ocena = 4.5
```

- Unikaj używania jednoliterowych nazw zmiennych, z wyjątkiem krótkotrwałego użycia zmiennych iteratorów w pętlach.
  
```python
for i in range(10):
    print(i)
```

**Formatowanie Linii i Białe Znaki**

- Używaj pustych linii, aby oddzielić funkcje i bloki kodu wewnątrz funkcji.
- Unikaj nadmiernego użycia białych znaków w nawiasach, nawiasach kwadratowych i klamrach.

```python
# Dobrze sformatowany kod
log_activity(servers[1], {threat_level: 2})

# Źle sformatowany kod
log_activity( servers[ 1 ], { threat_level: 2 } )
```

**Importy**

- Importy powinny zawsze być umieszczane na górze pliku, zaraz po ewentualnych komentarzach modułu i docstringach, a przed zmiennymi modułu i konstantami.
- Importy powinny być grupowane w następującej kolejności:
  1. Importy standardowej biblioteki.
  2. Importy związane z zewnętrznymi bibliotekami.
  3. Importy z lokalnego aplikacji / biblioteki.
- Zaleca się dodawanie pustej linii między każdą grupą importów.

```python
import os
import sys

from math import sqrt

from moj_modul import moja_funkcja
```

**Komentarze**

- Komentarze powinny być kompletne zdania i powinny być używane, gdy kod nie jest wystarczająco jasny.
- Unikaj zbędnych komentarzy, które powtarzają to, co już jest oczywiste z kodu.
- Używaj komentarzy do wyjaśnienia decyzji projektowych, które mogą nie być oczywiste dla czytelników kodu.

**Pisanie Funkcji i Metod**

- Funkcje i metody powinny być krótkie i spełniać jedno zadanie.
- Nazwy funkcji powinny być opisowe; unikaj skomplikowanych skrótów.
- Argumenty funkcji powinny być nazwane.

## Ćwiczenia do wykonania

1. Zainstaluj narzędzie `flake8`, które pomoże Ci sprawdzić zgodność Twojego kodu z konwencją PEP8. Oto przykładowy kod, który zawiera kilka błędów stylu:

```python
import sys,os
def moja_funkcja(x,y,z):return x+y+z
lista=[1,2,3,4,5]
if len(lista)>0:
  print('Lista nie jest pusta!')
else: print('Lista jest pusta!')
for i in lista:print(f'Element listy: {i}')
```


Aby zainstalować `flake8`, użyj polecenia:

```
pip install flake8
```

Następnie zapisz powyższy kod w pliku o nazwie `przyklad.py` i uruchom `flake8` w terminalu:

```
flake8 przyklad.py
```

Narzędzie `flake8` wskaże linie kodu, które naruszają zasady stylu PEP8, oraz poda krótki opis błędu. Twoim zadaniem jest poprawienie tych błędów i ponowne uruchomienie `flake8`, aż do momentu, gdy nie zostaną wykryte żadne problemy ze stylem.

### Przykładowe rozwiązania

#### Zadanie 1.
```python
def moja_funkcja(x, y, z):
    return x + y + z


lista = [1, 2, 3, 4, 5]

if len(lista) > 0:
    print('Lista nie jest pusta!')
else:
    print('Lista jest pusta!')

for i in lista:
    print(f'Element listy: {i}')

```


**Źródła**

Automate the Boring Stuff With Python - https://automatetheboringstuff.com

HTB Academy - https://academy.hackthebox.com

Python dokumentacja - https://docs.python.org/pl/3/reference/index.html





