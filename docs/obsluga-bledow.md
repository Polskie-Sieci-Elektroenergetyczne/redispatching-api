# Obsługa błędów

## Opis

Obsługa błędów dotyczy wszystkich endpointów API redysponowania. Każdy endpoint może zwrócić odpowiedź błędną w postaci schematu `ErrorResponse`. Endpointy asynchroniczne (POST + GET /status) dodatkowo zwracają schemat `ProcessingStatusResponse` zawierający wyniki walidacji w postaci tablicy `ValidationDetail`.

## Schemat `ErrorResponse`

Odpowiedź serwera w przypadku błędu (kod HTTP 400, 403, 404).

| Pole | Typ | Wymagane | Opis |
|------|-----|:--------:|------|
| `message` | string | tak | Opis błędu |
| `errorDetails` | string | tak | Szczegółowa przyczyna błędu |
| `requestId` | string (uuid) | nie | Unikalny identyfikator komunikatu |

Przykład:
```json
{
  "message": "Błąd przetwarzania",
  "errorDetails": "Brak elementu o podanym mRID",
  "requestId": "550e8400-e29b-41d4-a716-446655440000"
}
```

## Schemat `ProcessingStatusResponse`

Odpowiedź na zapytanie o status przetwarzania przesłanego dokumentu (endpointy `GET .../status`).

| Pole | Typ | Wymagane | Opis |
|------|-----|:--------:|------|
| `requestId` | string (uuid) | tak | Unikalne ID nadane przez system PSE |
| `status` | string (enum) | tak | Status operacji: `ACCEPTED`, `APPROVED`, `REJECTED` |
| `validationViolations` | array of `ValidationDetail` | nie | Błędy i naruszenia walidacji |

Przykład:
```json
{
  "requestId": "550e8400-e29b-41d4-a716-446655440000",
  "status": "APPROVED",
  "validationViolations": []
}
```

## Schemat `ValidationDetail`

Opis naruszenia walidacji w czasie przetwarzania przesłanych danych.

| Pole | Typ | Wymagane | Opis |
|------|-----|:--------:|------|
| `severity` | string (enum) | tak | Stopień naruszenia: `INFO`, `WARN`, `ERROR` |
| `code` | string (max 10) | tak | Kod naruszenia walidacji |
| `field` | string | nie | Wskazanie na element w zgłoszeniu |
| `message` | string | tak | Opis naruszenia |

## Kody HTTP

| Kod | Znaczenie | Schemat odpowiedzi |
|-----|-----------|-------------------|
| 400 | Nieprawidłowe dane wejściowe | `ErrorResponse` |
| 403 | Odmowa dostępu | `ErrorResponse` |
| 404 | Nie znaleziono zasobu | `ErrorResponse` |

## Uwierzytelnianie

mTLS — certyfikaty klienckie X.509 podpisane przez zaufany CA operatora (patrz specyfikacja OpenAPI, sekcja `securitySchemes`).
