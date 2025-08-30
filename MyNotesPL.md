# Teoria baz danych
### 1) Czym są bazy danych?:
Baza danych jest uporządkowana zbiorem informacji.
</p> <u>Przykłady:</u> </p>

Lista zakupów;
Historia wypożyczeń książek w bibliotece; 

### 2) Co można uznać za bazę danych?:
Za bazę danych możemy uznać plik tekstowy lub skoroszyt Excela, są to bazy o
strukturze płaskiej.

### 3) Jakie są główne elementy baz danych?:
Głównymi elementami baz danych jest tabela, która składa się z kolumn i wierszy.
Kolumny reprezentują cechy obiektu.
</p> <u>Przykład:</u> </p>

- Cena
- Kolor
- Stanowisko

Kolejnym elementem jest dodatkowa kolumna zwana kluczem głównym (podstawowym).
Najczęściej jest to liczba porządkowa.

### 4) Czym jest „Relacyjny model baz danych”?:
Jest to model polegający na rozbijaniu baz danych na jak najmniejsze elementy (tabele),
które zawierają listy cech obiektów. Taki zabieg zapobiega atomizacji baz danych.

### 5) Na czym polega atomizacja danych?
Atomizacja danych polega na rozbiciu jednej tabeli na wiele.

### 6) Jakie są typy relacji?:
Jeden do wielu = relacja pomiędzy tabelą klientów, a tabela z zamówieniami.
Wiele do wielu = relacja pomiędzy tabelą z zamówieniami i tabelą z produktami.
Jeden do jednego = jedna tabela przypisana jednemu elementowi.


# Odpytywanie danych
### 1) Jak wybieramy kolumnę w bazach danych?:
Jeśli chcemy wybrać/wyszukać coś w bazach danych używamy komendy select.
</p> <u>Przykład:</u> </p>
select BussinessEntityID, JobTitle
from HumanResources.Employee;

### 2) Jak zmienić nazwę kolumny?:
Jeśli chcemy zmienić nazwę kolumny, używamy do tego komendy
distinct [nazwa] as [Nasza Nazwa]
</p> <u>Przykład:</u> </p>
select distinct OrganizationLevel as „Poziom W Hierarchii”

### 3) Jak połączyć dwie kolumny w jedną?:
Jeśli chcemy połączyć dwie lub więcej kolumn w jedną używamy komendy „is a”
</p> <u>Przykład:</u> </p>
select LoginID + ’is a’ + JobTitle

### 4) Jak Filtrować Dane?:
Żeby filtrować dane używamy komendy „Where”.
</p> <u>Przykład:</u> </p>
where MaritalStatus = ’M’

# Typy Danych
### 1) Rodzaje danych i ich zakresy:

| Typ danych    | Zakres    |
|---|---|
| bit    | Liczba 0 lub 1 albo null    |
| tinyint    | 0 do 255    |
| smallint    | -32 768 do 32 767    |
| int    | -2,147,483,648 do 2,147,483,647    |
| bigint    | -9,223,372,036,854,775,808 do 9,223,372,036,854,775,807    |
| float    | Liczby zmiennoprzecinkowe o precyzji do 15 miejsc po przecinku. |
| char    | Tekst o stałej długości znaków (8000)    |
| varchar    | Tekst o zmiennej długości znaków (do 8000)    |
| text    | Tekst o zmiennej długości znaków (do 2 147 483 647)    |
| smallmoney    | Od -214 748,3648 do 214 748,3647    |
| money    | Od -922 337 203 685 477.5808 do 922 337 203 685 477.5807    |
| smalldatetime   | Data od 01.01.1900 do 06.06.2079    |
| datetime    | Data od 01.01.1753 do 31.12.9999    |

# Walidacja danych
### 1) Rodzaje walidacji danych:
- „ISNUMERIC” = Czy wskazane zapytanie da się przekonwertować na liczbę.
- „ISDATE" = Czy wyrażenie jest rozpoznawane jako data.
- „ISNULL"=Czy brakuje wartości we wskazanej kolumnie
- „COALESCE” = sprawdza kolejne elementy tablicy wprowadzonej do funkcji.
Zwraca pierwszą wartość, która nie jest null
- „NULLIF” = zwraca NULL, kiedy dwie porównywane wartości są równe

# Funkcję agregujące
### 1) Rodzaje funkcji agregujących:
- „SUM” - suma wartości. Może być stosowana wyłącznie dla danych liczbowych.
- „MIN” i „MAX” - najniższa i najwyższa wartość. Mogą być stosowane do danych
liczbowych, ciągów tekstu i dat.
- „COUNT (*) - zwraca ilość rekordów w tabeli.
- „COUNT (kolumna) - zwraca liczbę rekordów w kolumnie z pominięciem wartości null.
- „COUNT(DISTINCT kolumna) - zwraca liczbę unikatowych rekordów w kolumnie.
- „AVG” - średnia wartość. Może być stosowana wyłącznie dla danych liczbowych.
Funkcje agregującej ignorują pola z brakiem wartości (null).

# Złączenia i podzapytania
### 1) Na czym polega zapytanie "INNER JOIN"?:
Zapytanie „INNER JOIN”, czyli złączenie wewnętrze, łączy tabele pokazując ich część wspólną.  
### 2) Na czym polega łączenie „LEFT JOIN”?:
Jest to złączenie, która zwraca wszystkie rekordy z tabeli pierwszej i wszystkie które
pasują z tabeli drugiej.
### 3) Na czym polega łączenie „RIGHT JOIN”?:
Jest to złączenie, które działa odwrotnie do łączenia wewnętrznego „LEFT JOIN”.
### 4) Na czym polega łączenie „FULL JOIN”?:
Jest to złączenie, które zwraca wszystkie dane z obu źródeł,
### 5) Na czym polega łączenie „CROSS JOIN”?:
Jest to złączenie dające wynik w postaci iloczynu kartezjańskiego. W tym połączeniu
nie określamy relacji.