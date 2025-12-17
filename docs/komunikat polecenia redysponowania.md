# **Polecenie redysponowania**

## Wydanie polecenia redysponowania
Nadawca: OSP

Odbiorca: OSDp, Wytwórca przyłączony do sieci OSP

### Charakterystyka komunikatu
Operator systemu przesyłowego prowadząc ruch Krajowego Systemu Elektroenergetycznego (KSE) w sytuacji niezbilansowania KSE (tj. przypadku, w którym produkcja energii elektrycznej jest wyższa od krajowego zużycia) oraz przy braku innych środków dla zbilansowania KSE, w szczególności środków rynkowych, wydaje polecenia nierynkowego redysponowania dla instalacji OZE tworzących obiekty redysponowania.

Jeśli polecenie redysponowania dotyczy obiektów przyłączonych do sieci dystrybucyjnej różnych OSD, to wydane polecenie zostanie przekazane osobnymi komunikatami do każdego z OSD, których obiekty są redysponowane i z odpowiednim zestawem danych tylko dla tych obiektów.

Jeśli polecenie redysponowania dotyczy obiektu przyłączonego do sieci przesyłowej, a dany obiekt nie jest zintegrowany z systemem SCADA, to wydane polecenie zostanie przekazane kanałem PSDI do Wytwórcy tego obiektu. 

Komunikat zawiera podany okres wydanego polecenia wraz z listą obiektów redysponowania, których dotyczy. Dla każdego obiektu przekazywany jest zestaw danych - w szczególności maksymalne i minimalne wartości generacji/rozładowania określone ze względu na redysponowanie - w podziale na wskazane podokresy. Polecenie redysponowania może być wydane dla tego samego obiektu w obu kierunkach, ale w rozłącznych podokresach. Dodatkowo komunikat polecenia zawiera znacznik określający czy ograniczana jest moc generacji łącznie z mocą wytwarzaną na własne potrzeby i niewprowadzaną do sieci.

Dane otrzymane w tym komunikacie stanowią podstawę do wykonania polecenia. Dla jednostek przyłączonych do sieci przesyłowej, realizacja polecenia spoczywa bezpośrednio na Wytwórcy. Natomiast dla obiektów przyłączonych do sieci dystrybucyjnej, służby dyspozytorskie właściwych OSD są odpowiedzialne za zrealizowanie polecenia we współpracy z wytwórcami przyłączonymi do ich sieci.

### Status obsługi komunikatu
**Komunikat przyjęty** -  przekazanie technicznej odpowiedzi na komunikat, zawierającej informację o jego przyjęciu.

**Komunikat odrzucony** - przekazanie technicznej odpowiedzi na komunikat, zawierającej wyniki walidacji jego poprawności, będące powodem jego odrzucenia.