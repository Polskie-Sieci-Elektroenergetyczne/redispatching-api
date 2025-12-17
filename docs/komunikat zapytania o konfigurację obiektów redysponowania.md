# **Zapytanie o konfigurację obiektów redysponowania**

## Wysłanie zapytania o konfigurację obiektów redysponowania
Nadawca: OSDp

Odbiorca: OSP

### Charakterystyka komunikatu
Komunikat zapytania o konfigurację obiektów redysponowania przekazywany przez OSD pozwala na odpytanie OSP o listę obiektów podlegających redysponowaniu i przyłączonych do sieci tego OSD.

W żądaniu należy określić jakiego zakresu informacji dotyczy komunikat. Rozróżnia się następujące typy zapytań: 

* lista wszystkich obiektów redysponowania danego OSD;
* lista wszystkich obiektów obiekty redysponowania danego OSD wraz z listą zasobów składających się na każdy z tych obiektów;
* lista zasobów składających się na wskazany obiekt redysponowania.

W przypadku chęci pozyskania listy zasobów składających się na dany obiekt redysponowania należy podać identyfikator mRiD tego obiektu. 

Komunikat umożliwia odpytanie o stan konfiguracji obiektów redysponowania na dany dzień. W tym celu w komunikacie należy określić odpowiednią dobę. Może to być doba bieżąca (D) lub doba następna (D+1), a także data przeszła (jednak nie wcześniejsza niż 2 miesiące od doby bieżącej).

Nie jest możliwe zapytanie o konfigurację obiektów spoza sieci danego OSD, tj. przyłączonych do sieci innego OSD.

### Status obsługi komunikatu
**Komunikat przyjęty** -  przekazanie technicznej odpowiedzi na komunikat, zawierającej informację o jego przyjęciu. Rozpoczęcie generowania komunikatu z informacją o konfiguracji obiektów redysponowania.

**Komunikat odrzucony** - przekazanie technicznej odpowiedzi na komunikat, zawierającej wyniki walidacji jego poprawności, będące powodem jego odrzucenia.