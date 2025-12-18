# NIERYNKOWE REDYSPONOWANIE

Przedmiotem niniejszego dokumentu jest specyfikacja zakresu i formatu komunikatów dla nierynkowego redysponowania wymienianych przez dedykowany system informatyczny OSP (PSDI). Dane wymieniane są pomiędzy OSP a OSD i Wytwórcami przyłączonymi do sieci przesyłowej w procesach związanych prowadzeniem ruchu Krajowego Systemu Elektroenergetycznego.

Portalu Usług Systemowych i Działań Interwencyjnych (PSDI) w obszarze nierynkowego redysponowania wspiera służby dyspozytorskie Operatora Systemu Przesyłowego (OSP) w procesie nierynkowego redysponowania Odnawialnych Źródeł Energii (OZE), dla równoważenia dostaw energii elektrycznej z zapotrzebowaniem na tę energię oraz zapewnienia bezpieczeństwa pracy sieci elektroenergetycznej.

 PSDI umożliwia OSP przekazywanie do operatorów sieci dystrybucyjnej komunikatów będących poleceniem redysponowania obiektów do nich przyłączonych. OSD - poza komunikatem technicznej odpowiedzi przyjęcia polecenia - jest zobowiązany odpowiedzieć na polecenie redysponowania dedykowanym do tego komunikatem odpowiedzi na wydane polecenie. W komunikacie tym przekazuje decyzję o redysponowaniu jego obiektów zgodnie z poleceniem, tzn. OSD może potwierdzić przyjęcie polecenia do realizacji lub przekazać informację o braku możliwości wykonania polecenia.

Polecenia redysponowania w szczególnych przypadkach mogą być przekazywane poprzez PSDI również bezpośrednio do Wytwórców przyłączonych do sieci OSP. 

Dodatkowo OSP ma możliwość kanałem PSDI poinformowania Wytwórcy, którego obiekt przyłączony jest do sieci przesyłowej, o wydanym poleceniu redysponowania jego obiektu, nawet jeśli samo redysponowanie odbywa się poprzez inny system.

W PSDI przygotowano również komunikaty przy pomocy których OSD może zasięgnąć informacji o konfiguracji jego obiektów redysponowania tj. jakie obiekty redysponowania są przypisane do tego OSD oraz z jakich zasobów składa się dany obiekt. W tym celu inicjuje przekazanie komunikatu zapytania o konfigurację obiektów, z odpowiednimi parametrami. W zamian otrzymuje komunikat z informacją o konfiguracji obiektów z właściwym zestawem danych. 

Korzystanie z kanału PSDI wymaga od uczestniczących w wymianie informacji z OSP zarejestrowania się jako partner biznesowy OSP i uzyskania identyfikatora partnera biznesowego.

### Dokumenty źródłowe

Niniejsze standardy w zakresie nierynkowego redysponowania opierają się na następujących dokumentach:
* projekt Karty aktualizacji nr 2/CW-2/CK-2/CB-2/2024 Instrukcji Ruchu i Eksploatacji Sieci Przesyłowej (IRiESP) - w zakresie niezatwierdzonym decyzją Prezesa URE - przekazany do konsultacji w dniu 28 października 2025 r.

### Ogólne zestawienie przekazywanych komunikatów dla nierynkowego redysponowania

Informacje biznesowe w kanale PSDI są przekazywane w postaci komunikatów. Komunikat elektroniczny stanowi sformalizowany co do struktury oraz formatu zbiór danych przesyłanych jako komunikat na potrzeby wymiany informacji. Format komunikatów obowiązujących w kanale PSDI jest zgodny ze standardem opisu JSON.

| Rodzaj informacji | Nadawca | Odbiorca | Komunikat |
|-----------| :---------: | :---------: |-----------|
| Polecenie redysponowania | OSP | OSDp, Wytwórca przyłączony do sieci OSP| [Polecenie redysponowania](komunikat%20polecenia%20redysponowania.md?ref_type=heads) |
| Odpowiedź o na wydane polecenie redysponowania | OSDp | OSP | [Odpowiedź na wydane polecenie](komunikat%20odpowiedzi%20o%20podjęciu%20polecenia%20redysponowania.md?ref_type=heads) |
| Informacja o poleceniu redysponowania | OSP | Wytwórca przyłączony do sieci OSP | [Informacja o poleceniu redysponowania](komunikat%20informacji%20o%20poleceniu%20redysponowania.md?ref_type=heads) |
| Zapytanie o konfigurację obiektów redysponowania | OSDp | OSP | [Zapytanie o konfigurację obiektów](Komunikat%20zapytania%20o%20konfigurację%20obiektów%20redysponowania.md?ref_type=heads) |
| Informacja o konfiguracji obiektów redysponowania | OSP | OSDp | [Informacja o konfiguracji obiektów](Komunikat%20informacji%20o%20konfiguracji%20obiektów%20redysponowania.md?ref_type=heads) |
| Odpowiedź z wynikami weryfikacji poprawności komunikatu | OSDp <br /><br /> OSP | OSP <br /><br /> OSDp, Wytwórca przyłączony do sieci OSP | [Odpowiedź z wynikami](Komunikat%20odpowiedzi%20z%20wynikami%20weryfikacji%20poprawności%20komunikatu.md?ref_type=heads) |

## Rozliczenia redysponowania

Przedmiotem niniejszego rozdziału jest specyfikacja zakresu i formatu komunikatów dla rozliczeń nierynkowego redysponowania wymienianych przez dedykowany system informatyczny OSP (PSDI Redysponowanie). Dane wymieniane są pomiędzy OSP a OSD przyłączonymi do sieci przesyłowej w procesach związanych z rozliczaniem nierynkowego redysponowania.
Portal Usług Systemowych i Działań Interwencyjnych (PSDI Redysponowanie) w obszarze rozliczeń nierynkowego redysponowania wspiera Operatora Sieci Dystrybucyjnej w procesie dostarczania danych do rozliczeń nierynkowego redysponowania Odnawialnych Źródeł Energii (OZE) przyłączonych do sieci dystrybucyjnej.
PSDI umożliwia OSD przekazywanie do operatorów sieci przesyłowej komunikatów związanych z dostarczeniem danych niezbędnych do rozliczania nierynkowego redysponowania takich jak: 
- wydane polecenia na MWE w sieci OSD w ramach poleceń wydanych przez OSP, 
- organiczenia występujące w sieci dystrybucyjnej w czasie redysponowania niezwiązanych z wydanym poleceniem OSP, 
- energię certyfikowaną E_wyk_cert dla instalacji wiatrowych korzystających z systemu wsparcia świadectw pochodzenia w czasie trwania redysponowania, 
- informacja wynikająca z Ustawy uOZE o chęciu skorzystania z systemu wsparcia przez MWE, dla złożonych oświadczeń poza aplikacją WOZE
- przypisanie POB do MWE. 
Portal Usług Systemowych i Działań Interwencyjnych (PSDI Redysponowanie) w obszarze rozliczeń nierynkowego redysponowania wspiera Operatora Sieci Przesyłowej w procesie przekazania informacji o:
- historii wydanych poleceń w dobie poprzedającej,
- przekazaniu informacji wynikającej z obowiązku Ustawy uOZE, dla MWE, które miały złożone oświadczenie przez aplikację WOZE.
Polecenia redysponowania w szczególnych przypadkach mogą być przekazywane poprzez PSDI również bezpośrednio do Wytwórców przyłączonych do sieci OSP.
Dodatkowo OSP ma możliwość kanałem PSDI poinformowania Wytwórcy, którego obiekt przyłączony jest do sieci przesyłowej, o wydanym poleceniu redysponowania jego obiektu, nawet jeśli samo redysponowanie odbywa się poprzez inny system.
Korzystanie z kanału PSDI Redysponowanie na potrzeby rozliczeń nierynkowego redysponowania wymaga od uczestniczących w wymianie informacji z OSP zarejestrowania się jako partner biznesowy OSP i uzyskania identyfikatora partnera biznesowego.

### Dokumenty źródłowe
Niniejsze standardy w zakresie rozliczeń nierynkowego redysponowania opierają się na następujących dokumentach:
- Instrukcja Ruchu i Eksploatacji Sieci Przesyłowej (IRiESP), obowiązująca od dnia 28 października 2025 r.

### Ogólne zestawienie przekazywanych komunikatów dla rozliczeń nierynkowego redysponowania

| Rodzaj informacji | Nadawca | Odbiorca | Komunikat |
|-----------| :---------: | :---------: |-----------|
| Historyczne polecenia redukcji | OSP | OSDp | [komunikat informacji o historycznych poleceniach redysponowania](komunikat%20informacji%20o%20historycznych%20poleceniach%20redysponowania.md) |   
| Polecenia redukcji wydane przez OSD | OSDp | OSP | [komunikat informacji o poleceniach redysponowania wydanych przez OSD](komunikat%20informacji%20o%20poleceniach%20redysponowania%20wydanych%20przez%20OSD.md) |   
| Ograniczenia w sieci OSD niezwiązane z wydanym poleceniem OSP | OSDp | OSP | [komunikat informacji o ograniczeniach sieciowych w trakcie redysponowania](komunikat%20informacji%20o%20ograniczeniach%20sieciowych%20w%20trakcie%20redysponowania.md) |
| Wolumen energii wyprodukowanej objętej systemem wsparcia (Ewyk_cert) | OSDp | OSP | [komunikat informacji o energi wyprodukowanej objętej systemem wsparcia](komunikat%20informacji%20o%20energi%20wyprodukowanej%20objętej%20systemem%20wsparcia.md) |
| Zgłoszenia informacji o chęci skorzystania z aukcyjnego systemu wsparcia (uOZE) | OSDp | OSP | [komunikat informacji o chęci skorzystania z aukcyjnego systemu wsparcia](komunikat%20informacji%20o%20chęci%20skorzystania%20z%20aukcyjnego%20systemu%20wsparcia.md) |
| Zmiana podmiotu odpowiedzialnego za bilansowanie (POB) dla pojedynczego MWE | OSDp OSP | OSP OSDp | [komunikat informacji o zmianie podmiotu odpowiedzialnego za bilansowanie.md](komunikat%20informacji%20o%20zmianie%20podmiotu%20odpowiedzialnego%20za%20bilansowanie.md) |
