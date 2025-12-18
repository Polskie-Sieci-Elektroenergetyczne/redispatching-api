## Zmiana podmiotu odpowiedzialnego za bilansowanie (POB) dla pojedynczego MWE 
#### Adres Rest API

```
- POST redispatching/api/v1/responsiblesubjectforgenerator
- GET redispatching/api/v1/responsiblesubjectforgenerator/status
```

#### Nadawca
Operator Systemu Dystrybucyjnego przyłaczony do sieci przesyłowej 

#### Odbiorca
Operator Systemu Przesyłowego

#### Charakterystyka komunikatu
Przekazanie informacji o zmianie przypisania POB do pojedynczego MWE polegające na podaniu informacji o:
- identyfikatorze mRID (Unikalny identyfikator MWE) MWE
- nazwie podmiotu odpowiedzialnego za bilansowanie
- numerze NIP podmiotu odpowiedzialnego za bilansowanie
- dacie obowiązywania od POB dla MWE

Warunki wymagane do rozpoczęcia komunikatu:
Zmiana przypisania POB dla MWE
Komunikat będzie dostępny do przesłania od daty zmiany przypisania POB do MWE

#### Status obsługi komunikatu
**Zgoszenie przyjęte:** Zmiana POB dla MWE została zarejestrowana w systemie OSP.

**Zgłoszenie odrzucone:** Zmiana POB dla MWE nie została zarejestrowana w systemie OSP.

#### Diagram sekwencji
```mermaid
sequenceDiagram
    participant REST Client
    participant B2B REST API
    participant Backend service
    REST Client->B2B REST API: POST redispatching/api/v1/responsiblesubjectforgenerator
    B2B REST API->B2B REST API: createRequest()
    B2B REST API-->REST Client: RestResponse
    B2B REST API->Backend service: approveRequest()
    Backend service->Backend service: approvalProcess()
    Backend service-->B2B REST API: approveResult()        
    opt
      loop  
        REST Client->B2B REST API: GET redispatching/api/v1/responsiblesubjectforgenerator/status
        B2B REST API-->REST Client: RestStatusResponse
      end
    end  
```
