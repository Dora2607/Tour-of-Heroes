# Tour of Heroes

Questo progetto è stato generato con Angular CLI versione 17.1.1.

## Descrizione del Progetto

Il progetto "Tour of Heroes" è un tutorial di Angular che aiuta i nuovi utenti a capire le funzionalità fondamentali di Angular. Questo progetto copre vari aspetti di Angular come i componenti, i template, i servizi, il routing e l'accesso ai dati.

## Installazione

Prima di tutto, assicurati di avere Node.js e npm installati sulla tua macchina. Poi, clona questo repository sulla tua macchina locale. Naviga nella cartella del progetto e installa le dipendenze con:

```bash
npm install
```

## Esecuzione dell'applicazione 
Per avviare l’applicazione, esegui il seguente comando nella cartella del progetto:
```bash
ng serve
```
Ora, apri il tuo browser e vai a http://localhost:4200/. L’applicazione si ricaricherà automaticamente se cambi qualcosa nei file sorgente.

## Dettagli dell'Applicazione

L'applicazione "Tour of Heroes" è un'applicazione single-page sviluppata con Angular. Utilizza un sistema di routing per navigare tra le diverse viste dell'applicazione. Le rotte definite sono le seguenti:

- `dashboard`: Mostra una panoramica dei eroi.
- `detail/:id`: Mostra i dettagli di un eroe specifico.
- `heroes`: Mostra un elenco di tutti gli eroi.

L'applicazione è composta dai seguenti moduli:

- `BrowserModule`: Fornisce i servizi necessari per eseguire applicazioni web.
- `FormsModule`: Fornisce supporto per il two-way data binding.
- `HttpClientModule`: Fornisce supporto per l'invio di richieste HTTP.
- `HttpClientInMemoryWebApiModule`: Interagisce con un database in memoria.

E dai seguenti componenti:

- `AppComponent`: Il componente radice dell'applicazione.
- `HeroesComponent`: Mostra un elenco di eroi.
- `HeroDetailComponent`: Mostra i dettagli di un eroe specifico.
- `MessagesComponent`: Mostra i messaggi dell'applicazione.
- `DashboardComponent`: Mostra una panoramica dei eroi.
- `HeroSearchComponent`: Fornisce una funzionalità di ricerca per i eroi.

Vediamo nel dettaglio le seguenti componenti:

### AppComponent

L'`AppComponent` è il componente principale dell'applicazione "Tour of Heroes". Questo componente fornisce il layout principale dell'applicazione e contiene un elemento di navigazione con link alle diverse viste dell'applicazione. Utilizza l'interpolazione per visualizzare il titolo dell'applicazione e un segnaposto `router-outlet` per visualizzare dinamicamente il componente corrispondente alla rotta corrente. Include anche il componente `app-messages` per visualizzare i messaggi dell'applicazione. 

### HeroesComponent

L'`HeroesComponent` è un componente in Angular che fornisce un'interfaccia per visualizzare, aggiungere e rimuovere "eroi". Il componente utilizza un servizio `HeroService` per eseguire operazioni sui dati degli eroi. Il template HTML del componente include un titolo, un campo di input e un pulsante per aggiungere nuovi eroi, e un elenco di tutti gli eroi con link ai dettagli di ciascun eroe e pulsanti per rimuovere gli eroi. Il componente fornisce metodi per recuperare tutti gli eroi, aggiungere un nuovo eroe e rimuovere un eroe esistente.

### HeroDetailComponent

L'`HeroDetailComponent` è un componente in Angular che fornisce un'interfaccia per visualizzare e modificare i dettagli di un "eroe" specifico. Il componente utilizza un servizio `HeroService` per eseguire operazioni sui dati degli eroi e un `ActivatedRoute` per accedere ai parametri del route. Il template HTML del componente include un titolo, un campo di input per il nome dell'eroe e due pulsanti per navigare indietro e salvare le modifiche. Il componente fornisce metodi per recuperare l'eroe corrente, navigare indietro e salvare le modifiche all'eroe.

### MessagesComponent

Il `MessagesComponent` è un componente in Angular che fornisce un'interfaccia per visualizzare e cancellare i messaggi dell'applicazione. Il componente utilizza un servizio `MessageService` per accedere ai messaggi dell'applicazione. Il template HTML del componente include un titolo, un pulsante per cancellare tutti i messaggi e un ciclo per visualizzare tutti i messaggi. Il componente non fornisce alcuna logica aggiuntiva oltre a quella fornita dal `MessageService`.

### DashboardComponent

Il `DashboardComponent` è un componente in Angular che fornisce un'interfaccia per visualizzare i "Top Heroes" e cercare eroi. Il componente utilizza un servizio `HeroService` per eseguire operazioni sui dati degli eroi. Il template HTML del componente include un titolo, un elenco di link agli eroi e un componente di ricerca di eroi. Il componente fornisce metodi per recuperare i primi 4 eroi.

### HeroSearchComponent

L'`HeroSearchComponent` è un componente in Angular che fornisce un'interfaccia per cercare eroi. Il componente utilizza un servizio `HeroService` per eseguire operazioni sui dati degli eroi e un `Subject` per tenere traccia dei termini di ricerca. Il template HTML del componente include un campo di input per i termini di ricerca e un elenco dei risultati della ricerca. Ogni risultato è un link al dettaglio dell'eroe. Il componente fornisce metodi per aggiungere nuovi termini di ricerca e impostare l'observable dei risultati della ricerca.


Inoltre, l'applicazione utilizza i seguenti servizi:

- `HeroService`: Questo servizio fornisce metodi per eseguire        operazioni CRUD (Create, Read, Update, Delete) su un elenco di “eroi".
- `InMemoryDataService`: Simula un database in memoria per lo sviluppo.
- `MessageService`: Gestisce i messaggi dell'applicazione.

L'applicazione "Tour of Heroes" è un ottimo esempio di come Angular può essere utilizzato per sviluppare applicazioni web moderne e reattive.

Vediamo nel dettaglio i servizi:

### HeroService

Il `HeroService` è un servizio fondamentale nell'applicazione "Tour of Heroes". Questo servizio fornisce metodi per eseguire operazioni CRUD (Create, Read, Update, Delete) su un elenco di "eroi". Utilizza il modulo `HttpClient` per interagire con un server remoto e il `MessageService` per registrare i messaggi dell'applicazione. Il `HeroService` include metodi per ottenere tutti gli eroi (`getHeroes`), ottenere un eroe specifico per ID (`getHero`), aggiornare un eroe esistente (`updateHero`), aggiungere un nuovo eroe (`addHero`), eliminare un eroe (`deleteHero`), e cercare eroi per nome (`searchHeroes`). Ogni metodo restituisce un `Observable`, che è un tipo di oggetto fornito dalla libreria RxJS, utilizzato per gestire operazioni asincrone in Angular.

### InMemoryDataService

Il `InMemoryDataService` è un servizio che simula un database in memoria per lo sviluppo. Implementa l'interfaccia `InMemoryDbService` fornita dal modulo `angular-in-memory-web-api`. Questo servizio fornisce un metodo `createDb` per creare un database in memoria contenente un array di "eroi". Ogni eroe ha un `id` e un `name`. Il servizio include anche un metodo `genId` che genera un ID univoco per un nuovo eroe. Se l'array di eroi è vuoto, `genId` restituisce l'ID iniziale (11). Se l'array di eroi non è vuoto, `genId` restituisce l'ID più alto tra gli eroi esistenti più 1.

### MessageService

Il `MessageService` è un servizio in Angular che fornisce un meccanismo per raccogliere e gestire i messaggi all'interno dell'applicazione. Mantiene un array di messaggi, con ogni messaggio rappresentato come una stringa. Il servizio fornisce due metodi principali: `add` e `clear`. Il metodo `add` accetta un messaggio come stringa e lo aggiunge all'array di messaggi. Il metodo `clear` cancella tutti i messaggi dall'array. Questo servizio può essere utilizzato per registrare le attività dell'applicazione o per fornire feedback all'utente.
