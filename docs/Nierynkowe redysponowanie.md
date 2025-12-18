# NIERYNKOWE REDYSPONOWANIE

Przedmiotem niniejszego dokumentu jest specyfikacja zakresu i formatu komunikatów dla nierynkowego redysponowania wymienianych przez dedykowany system informatyczny OSP (PSDI). Dane wymieniane są pomiędzy OSP a OSD i Wytwórcami przyłączonymi do sieci przesyłowej w procesach związanych prowadzeniem ruchu Krajowego Systemu Elektroenergetycznego.

Portalu Usług Systemowych i Działań Interwencyjnych (PSDI) w obszarze nierynkowego redysponowania wspiera służby dyspozytorskie Operatora Systemu Przesyłowego (OSP) w procesie nierynkowego redysponowania Odnawialnych Źródeł Energii (OZE), dla równoważenia dostaw energii elektrycznej z zapotrzebowaniem na tę energię oraz zapewnienia bezpieczeństwa pracy sieci elektroenergetycznej.

 PSDI umożliwia OSP przekazywanie do operatorów sieci dystrybucyjnej komunikatów będących poleceniem redysponowania obiektów do nich przyłączonych. OSD - poza komunikatem technicznej odpowiedzi przyjęcia polecenia - jest zobowiązany odpowiedzieć na polecenie redysponowania dedykowanym do tego komunikatem odpowiedzi na wydane polecenie. W komunikacie tym przekazuje decyzję o redysponowaniu jego obiektów zgodnie z poleceniem, tzn. OSD może potwierdzić przyjęcie polecenia do realizacji lub przekazać informację o braku możliwości wykonania polecenia.

Polecenia redysponowania w szczególnych przypadkach mogą być przekazywane poprzez PSDI również bezpośrednio do Wytwórców przyłączonych do sieci OSP. 

Dodatkowo OSP ma możliwość kanałem PSDI poinformowania Wytwórcy, którego obiekt przyłączony jest do sieci przesyłowej, o wydanym poleceniu redysponowania jego obiektu, nawet jeśli samo redysponowanie odbywa się poprzez inny system.

W PSDI przygotowano również komunikaty przy pomocy których OSD może zasięgnąć informacji o konfiguracji jego obiektów redysponowania tj. jakie obiekty redysponowania są przypisane do tego OSD oraz z jakich zasobów składa się dany obiekt. W tym celu inicjuje przekazanie komunikatu zapytania o konfigurację obiektów, z odpowiednimi parametrami. W zamian otrzymuje komunikat z informacją o konfiguracji obiektów z właściwym zestawem danych. 

Korzystanie z kanału PSDI wymaga od uczestniczących w wymianie informacji z OSP zarejestrowania się jako partner biznesowy OSP i uzyskania identyfikatora partnera biznesowego.

## Dokumenty źródłowe

Niniejsze standardy w zakresie nierynkowego redysponowania opierają się na następujących dokumentach:
* projekt Karty aktualizacji nr 2/CW-2/CK-2/CB-2/2024 Instrukcji Ruchu i Eksploatacji Sieci Przesyłowej (IRiESP) - w zakresie niezatwierdzonym decyzją Prezesa URE - przekazany do konsultacji w dniu 28 października 2025 r.

## Ogólne zestawienie przekazywanych komunikatów dla nierynkowego redysponowania

Informacje biznesowe w kanale PSDI są przekazywane w postaci komunikatów. Komunikat elektroniczny stanowi sformalizowany co do struktury oraz formatu zbiór danych przesyłanych jako komunikat na potrzeby wymiany informacji. Format komunikatów obowiązujących w kanale PSDI jest zgodny ze standardem opisu JSON.

| Rodzaj informacji | Nadawca | Odbiorca | Komunikat |
|-----------| :---------: | :---------: |-----------|
| Polecenie redysponowania | OSP | OSDp, Wytwórca przyłączony do sieci OSP| [Polecenie redysponowania](komunikat%20polecenia%20redysponowania.md?ref_type=heads) |
| Odpowiedź o na wydane polecenie redysponowania | OSDp | OSP | [Odpowiedź na wydane polecenie](komunikat%20odpowiedzi%20na%20wydane%20polecenie%20redysponowania.md?ref_type=heads) |
| Informacja o poleceniu redysponowania | OSP | Wytwórca przyłączony do sieci OSP | [Informacja o poleceniu redysponowania](komunikat%20informacji%20o%20poleceniu%20redysponowania.md?ref_type=heads) |
| Zapytanie o konfigurację obiektów redysponowania | OSDp | OSP | [Zapytanie o konfigurację obiektów](komunikat%20zapytania%20o%20konfigurację%20obiektów%20redysponowania.md?ref_type=heads) |
| Informacja o konfiguracji obiektów redysponowania | OSP | OSDp | [Informacja o konfiguracji obiektów](komunikat%20informacji%20o%20konfiguracji%20obiektów%20redysponowania.md?ref_type=heads) |
| Informacja o błędzie przetwarzania podjętego komunikatu | OSDp <br /><br /> OSP | OSP <br /><br /> OSDp, Wytwórca przyłączony do sieci OSP | [Informacja o błędzie przetwarzania komunikatu](komunikat%20informacji%20o%20błędzie%20przetwarzania.md?ref_type=heads) |
