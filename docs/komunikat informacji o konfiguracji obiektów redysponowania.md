# **Informacja o konfiguracji obiektów redysponowania**

## Przekazanie informacji o konfiguracji obiektów redysponowania
Nadawca: OSP

Odbiorca: OSDp

### Charakterystyka komunikatu
Komunikat jest biznesową odpowiedzią na komunikat zapytania o konfigurację obiektów redysponowania inicjowany przez OSD do OSP.

Informacja o konfiguracji obiektów redysponowania dotyczy stanu na dobę określoną w zapytaniu oraz (w zależności od typu żądania w zapytaniu) zwraca:

* listę wszystkich obiektów redysponowania danego OSD;
* listę wszystkich obiektów redysponowania danego OSD wraz z listą zasobów składających się na każdy z tych obiektów;
* listę zasobów składających się na wskazany obiekt redysponowania.

Komunikat w zestawie danych dla obiektów redysponowania, zwraca parę danych tj. identyfikator mRID obiektu redysponowania oraz jego biznesowy kod. Dodatkowo przy zapytaniu o listę zasobów składających się na obiekt redysponowania, dla każdego z nich zwraca zestaw danych w postaci identyfikatora mRID danego zasobu, jego biznesowego kodu oraz wartości mocy referencyjnej.

### Status obsługi komunikatu
**Komunikat przyjęty** -  przekazanie technicznej odpowiedzi na komunikat, zawierającej informację o jego przyjęciu.

**Komunikat odrzucony** - przekazanie technicznej odpowiedzi na komunikat, zawierającej wyniki walidacji jego poprawności, będące powodem jego odrzucenia. 