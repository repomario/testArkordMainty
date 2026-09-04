# Capitolato Tecnico

## Nome Progetto

TaskFlow Lite

## Descrizione

Realizzare una semplice applicazione web per la gestione di attività personali (To-Do List), che consenta agli utenti di creare, modificare, completare ed eliminare attività.

## Obiettivi

* Gestire un elenco di attività personali.
* Consentire una rapida organizzazione delle attività.
* Fornire un'interfaccia semplice e intuitiva.

## Requisiti Funzionali

### Gestione attività

L'utente deve poter:

* creare una nuova attività;
* modificare titolo e descrizione;
* contrassegnare un'attività come completata;
* eliminare un'attività;
* visualizzare l'elenco delle attività.

### Filtri

L'utente deve poter filtrare le attività per:

* tutte;
* completate;
* da completare.

## Requisiti Non Funzionali

* L'applicazione deve essere responsive.
* L'interfaccia deve essere semplice e facilmente utilizzabile.
* Le operazioni principali devono essere eseguibili con pochi clic.

## Vincoli Tecnici

* Applicazione web.
* Backend REST API.
* Database relazionale.
* Persistenza dei dati.

## Decisioni Architetturali Già Definite

* Architettura client/server.
* Database relazionale come sistema di persistenza.
* API REST come modalità di comunicazione tra frontend e backend.

## Ambito

### Incluso

* Gestione delle attività.
* Filtri di visualizzazione.
* Persistenza dei dati.

### Escluso

* Autenticazione utenti.
* Collaborazione tra utenti.
* Notifiche.
* Applicazione mobile.

## Deliverable Attesi

Il progetto dovrà essere inizializzato con:

* Blueprint del progetto;
* Roadmap iniziale;
* Specifiche funzionali;
* ADR relative alle decisioni architetturali già definite;
* Epics che rappresentino le principali aree funzionali del progetto.
