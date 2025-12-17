# PSDI Redysponowanie API B2B
Przedmiotem niniejszego dokumentu jest specyfikacja zakresu i formatu komunikatów dla rozliczeń nierynkowego redysponowania wymienianych przez dedykowany system informatyczny OSP (PSDI Redysponowanie). Dane wymieniane są pomiędzy OSP a OSD przyłączonymi do sieci przesyłowej w procesach związanych z rozliczaniem nierynkowego redysponowania.
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

# Dokumenty źródłowe
Niniejsze standardy w zakresie rozliczeń nierynkowego redysponowania opierają się na następujących dokumentach:
- Instrukcja Ruchu i Eksploatacji Sieci Przesyłowej (IRiESP), obowiązująca od dnia 28 października 2025 r.

# Ogólne zestawienie przekazywanych komunikatów dla rozliczeń nierynkowego redysponowania

[Historyczne polecenia redukcji](komunikat%20informacji%20o%20historycznych%20poleceniach%20redysponowania.md)   
[Polecenia redukcji wydane przez OSD](komunikat%20informacji%20o%20poleceniach%20redysponowania%20wydanych%20przez%20OSD.md)   
[Ograniczenia w sieci OSD niezwiązane z wydanym poleceniem OSP](komunikat%20informacji%20o%20ograniczeniach%20sieciowych%20w%20trakcie%20redysponowania.md)   
[Wolumen energii wyprodukowanej objętej systemem wsparcia (Ewyk_cert)](komunikat%20informacji%20o%20energi%20wyprodukowanej%20objętej%20systemem%20wsparcia.md)   
[Zgłoszenia informacji o chęci skorzystania z aukcyjnego systemu wsparcia (uOZE)](komunikat%20informacji%20o%20chęci%20skorzystania%20z%20aukcyjnego%20systemu%20wsparcia.md)  
[Zmiana podmiotu odpowiedzialnego za bilansowanie (POB) dla pojedynczego MWE](komunikat%20informacji%20o%20zmianie%20podmiotu%20odpowiedzialnego%20za%20bilansowanie.md)  
