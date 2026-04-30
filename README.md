# Nierynkowe redysponowanie — B2B API

Specyfikacja i dokumentacja API dla nierynkowego redysponowania wydawanego przez OSP. Dane wymieniane są pomiędzy OSP i OSD oraz Wytwórcami w procesach związanych z prowadzeniem ruchu Krajowego Systemu Elektroenergetycznego.

> Log zmian znajduje się w [CHANGELOG.md](CHANGELOG.md)

## Specyfikacja OpenAPI

Pełna specyfikacja techniczna API dostępna jest w pliku: [`specs/redispatching-openapi.yml`](../specs/redispatching-openapi.yml)

Dostępna jest również [dokumentacja API w formacie REDOC](https://polskie-sieci-elektroenergetyczne.github.io/redispatching-api/)

| Parametr | Wartość |
|----------|---------|
| **Adres bazowy** | `https://b2b.pse.pl` |
| **Ścieżka bazowa** | `/redispatching/api/v1/` |
| **Uwierzytelnianie** | mTLS — certyfikaty klienckie X.509 podpisane przez zaufany CA operatora |
| **Format danych** | JSON |

## Dokumenty źródłowe

Niniejsze standardy w zakresie nierynkowego redysponowania opierają się na następujących dokumentach:
* Projekt Karty aktualizacji nr 2/CW-2/CK-2/CB-2/2024 Instrukcji Ruchu i Eksploatacji Sieci Przesyłowej (IRiESP) — w zakresie niezatwierdzonym decyzją Prezesa URE — przekazany do konsultacji w dniu 28 października 2025 r.

## Definicje

* **Podmiot** rozumiany jest jako OSD lub wytwórca OZE (właściciel lub podmiot jego reprezentujący)

## Część 1 — Polecenia redysponowania (SSE + REST)

API umożliwia OSP przekazywanie do Podmiotów poleceń redysponowania obiektów. Komunikacja odbywa się w czasie rzeczywistym za pomocą **Server-Sent Events (SSE)** dla powiadomień oraz **REST** dla wymiany danych.

Workflow:
1. Klient łączy się ze strumieniem SSE (`GET .../redispatch/{entityId}/stream`)
2. Otrzymuje zdarzenie `ORDER_ISSUED` informujące o nowym poleceniu
3. Pobiera szczegóły polecenia (`GET .../redispatch/{entityId}/orders/{orderId}`)
4. Przesyła potwierdzenie odbioru i decyzję (`POST .../acknowledgement`)

Podmiot — poza komunikatem technicznej odpowiedzi przyjęcia polecenia — jest zobowiązany odpowiedzieć na polecenie redysponowania dedykowanym komunikatem odpowiedzi, w którym przekazuje decyzję o redysponowaniu obiektów zgodnie z poleceniem (przyjęcie do realizacji lub informacja o braku możliwości wykonania).

Dodatkowo OSP ma możliwość poinformowania Wytwórcu, którego obiekt przyłączony jest do sieci przesyłowej, o wydanym poleceniu redysponowania jego obiektu, nawet jeśli samo redysponowanie odbywa się poprzez inny system.

W API dostępne są również operacje do pobrania informacji o konfiguracji obiektów redysponowania tj. jakie obiekty redysponowania są przypisane do Podmiotu oraz z jakich zasobów składa się dany obiekt.

Korzystanie z API redysponowania wymaga od uczestniczących w wymianie informacji z OSP zarejestrowania się jako partner biznesowy OSP i uzyskania identyfikatora partnera biznesowego.

| Rodzaj informacji | Komunikat |
|-------------------|-----------|
| Polecenia redysponowania (SSE + REST) | [Polecenia redysponowania (SSE)](docs/polecenia-redysponowania-sse.md) |
| Konfiguracja obiektów redysponowania | [Konfiguracja obiektów](docs/konfiguracja-obiektow.md) |
| Obsługa błędów | [Obsługa błędów](docs/obsluga-bledow.md) |

## Część 2 — Rozliczenia redysponowania (REST)

Druga część API służy do rozliczeń nierynkowego redysponowania.
API umożliwia Podmiotom dostarczenie do OSP danych niezbędnych do rozliczania nierynkowego redysponowania takich jak:
- wydane polecenia na MWE w sieci OSD w ramach poleceń wydanych przez OSP,
- ograniczenia występujące w sieci dystrybucyjnej w czasie redysponowania niezwiązanych z wydanym poleceniem OSP,
- energię certyfikowaną E_WYK_CERT dla instalacji wiatrowych korzystających z systemu wsparcia świadectw pochodzenia w czasie trwania redysponowania,
- informacja wynikająca z Ustawy uOZE o chęci skorzystania z systemu wsparcia przez MWE,
- przypisanie POB do MWE.

API w obszarze rozliczeń pozwala Podmiotom pobrać dane o historii wydanych poleceń w dobie poprzedzającej oraz informacji wynikającej z ustawy uOZE.

### Dokumenty źródłowe

Specyfikacja w zakresie rozliczeń nierynkowego redysponowania opiera się na następujących dokumentach:
- Instrukcja Ruchu i Eksploatacji Sieci Przesyłowej (IRiESP), obowiązująca od dnia 28 października 2025 r.

### Zestawienie komunikatów

| Rodzaj informacji | Nadawca | Odbiorca | Komunikat |
|-------------------|:-------:|:--------:|-----------|
| Historyczne polecenia redysponowania | OSP | Podmiot | [Historyczne polecenia](docs/historyczne-polecenia.md) |
| Polecenia redysponowania wydane przez OSD | Podmiot | OSP | [Polecenia OSD](docs/polecenia-osd.md) |
| Ograniczenia w sieci OSD niezwiązane z wydanym poleceniem OSP | Podmiot | OSP | [Ograniczenia sieciowe](docs/ograniczenia-sieciowe.md) |
| Wolumen energii wyprodukowanej objętej systemem wsparcia (E_WYK_CERT) | Podmiot | OSP | [Energia certyfikowana](docs/energia-certyfikowana.md) |
| Zgłoszenia informacji o chęci skorzystania z aukcyjnego systemu wsparcia (uOZE) | Podmiot | OSP | [System wsparcia uOZE](docs/system-wsparcia-uoze.md) |
| Zmiana podmiotu odpowiedzialnego za bilansowanie (POB) dla pojedynczego MWE | Podmiot | OSP | [Zmiana POB](docs/zmiana-pob.md) |
