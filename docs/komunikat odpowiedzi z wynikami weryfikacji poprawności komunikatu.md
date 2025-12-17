# **Odpowiedź z wynikami weryfikacji poprawności komunikatu**

## Przekazanie odpowiedzi z wynikami weryfikacji poprawności komunikatu
Nadawca: OSDp, OSP

Odbiorca: OSP, OSDp, Wytwórca przyłączony do sieci OSP

### Charakterystyka komunikatu
Komunikat ma charakter odpowiedzi technicznej, która jest wysyłana w odniesieniu do wszystkich komunikatów przekazywanych między OSP a Podmiotami.

Odpowiedź ma analogiczną strukturę dla każdego rodzaju komunikatu:

* polecenia redysponowania;
* odpowiedzi na wydane polecenie redysponowania;
* informacji o wydaniu polecenia redysponowania;
* zapytania o konfigurację obiektów redysponowania;
* Informacji o konfiguracji obiektów redysponowania.

Komunikat odpowiedzi określa status (przyjęcie bądź odrzucenie) danego rodzaju komunikatu oraz wskazuje na ten komunikat poprzez jego identyfikator nadany przez nadawcę, który jest traktowany jako komunikat referencyjny. W odpowiedzi przekazywana jest również przyczyna odrzucenia bądź, w przypadku potwierdzenia komunikatu, informacja o charakterze ostrzegawczym lub uzupełniającym.

### Status obsługi komunikatu
Komunikat odpowiedzi zawiera informacje o statusie komunikatu na jaki odpowiada, który należy rozumieć w następujący sposób:

**Komunikat przyjęty** -  Poprawna struktura komunikatu. Potwierdzenie odbioru komunikatu.

**Komunikat odrzucony** - Niepoprawna struktura komunikatu. Brak potwierdzenia odbioru komunikatu.


