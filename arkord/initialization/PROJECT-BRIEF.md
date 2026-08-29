Project Plan — Mainty
1. Project Overview

Mainty è un'applicazione web per la gestione delle attività di manutenzione di edifici, strutture e relativi asset.

Il sistema deve permettere a un'organizzazione di censire le proprie strutture e gli asset presenti al loro interno, segnalare problemi, pianificare interventi di manutenzione e assegnare il lavoro ai tecnici.

L'obiettivo principale è sostituire la gestione informale effettuata tramite messaggi, fogli di calcolo e comunicazioni verbali con un sistema centralizzato nel quale sia possibile sapere:

quali problemi sono stati segnalati;
quali interventi devono essere effettuati;
chi è responsabile dell'intervento;
quale sia lo stato corrente del lavoro;
quali interventi siano stati eseguiti in passato su uno specifico asset.

L'applicazione sarà inizialmente utilizzata da una singola organizzazione, ma l'architettura non dovrebbe impedire una futura evoluzione verso l'utilizzo da parte di più organizzazioni indipendenti.

2. Users and Roles

Il sistema prevede tre tipologie principali di utenti.

Administrator

L'Administrator gestisce la configurazione generale del sistema.

Deve poter:

creare e modificare utenti;
assegnare ruoli;
creare e modificare strutture;
creare e modificare asset;
accedere a tutte le attività di manutenzione;
consultare lo storico delle attività;
configurare le principali impostazioni applicative.
Maintenance Manager

Il Maintenance Manager coordina le attività di manutenzione.

Deve poter:

visualizzare le segnalazioni;
creare interventi di manutenzione;
modificare gli interventi;
assegnare gli interventi ai tecnici;
impostare priorità;
pianificare una data prevista;
cambiare lo stato degli interventi;
consultare lo storico;
filtrare e ricercare gli interventi.
Technician

Il Technician esegue gli interventi assegnati.

Deve poter:

visualizzare gli interventi che gli sono stati assegnati;
visualizzare i dettagli dell'intervento;
iniziare un intervento;
aggiungere note;
allegare fotografie;
completare un intervento;
indicare il lavoro effettuato.

Un Technician non deve poter modificare utenti, strutture o configurazioni amministrative.

3. Authentication and Access

L'accesso all'applicazione richiede autenticazione.

Ogni utente deve avere almeno:

nome;
cognome;
email;
ruolo;
stato attivo/disattivato.

L'email viene utilizzata come identificativo per l'accesso.

Gli utenti disattivati non devono poter accedere al sistema, ma i dati storici associati alle loro attività devono essere conservati.

Le autorizzazioni devono essere controllate anche dal backend e non solamente nascondendo funzionalità nell'interfaccia.

Non è richiesta nella prima versione l'autenticazione tramite provider esterni come Google, Microsoft o sistemi SSO aziendali.

4. Facilities

Una Facility rappresenta una struttura fisica gestita dall'organizzazione, ad esempio:

ufficio;
magazzino;
stabilimento;
negozio.

Ogni Facility deve avere almeno:

nome;
indirizzo;
descrizione opzionale;
stato attivo/inattivo.

Una Facility può contenere molti Asset.

Le Facility inattive devono rimanere disponibili nello storico ma non dovrebbero essere normalmente utilizzabili per creare nuove attività.

5. Assets

Un Asset rappresenta un elemento fisico soggetto a manutenzione.

Esempi:

climatizzatore;
ascensore;
quadro elettrico;
porta automatica;
macchina industriale;
impianto;
attrezzatura.

Ogni Asset deve appartenere a una Facility.

Un Asset deve poter contenere almeno:

nome;
codice identificativo;
descrizione;
Facility;
posizione interna opzionale;
stato;
data di installazione opzionale.

Il codice identificativo deve consentire di riconoscere rapidamente l'Asset all'interno dell'organizzazione.

Dalla pagina di un Asset deve essere possibile consultare lo storico degli interventi che lo riguardano.

Gli Asset non più utilizzati devono poter essere disattivati senza eliminare lo storico associato.

6. Maintenance Requests

Un utente autorizzato deve poter segnalare un problema creando una Maintenance Request.

Una richiesta deve contenere almeno:

titolo;
descrizione;
Facility;
Asset opzionale;
autore della segnalazione;
data di creazione;
priorità;
stato.

Deve essere possibile allegare fotografie alla segnalazione.

Una segnalazione potrebbe riguardare una Facility senza essere associata a uno specifico Asset.

Le priorità previste inizialmente sono:

Low;
Medium;
High;
Critical.

Il sistema deve rendere chiaramente distinguibili le segnalazioni Critical dalle altre.

7. Work Orders

Una Maintenance Request può portare alla creazione di un Work Order.

Il Work Order rappresenta il lavoro effettivamente pianificato ed eseguito.

Deve contenere almeno:

titolo;
descrizione;
Facility;
Asset opzionale;
priorità;
Technician assegnato;
stato;
data di creazione;
data pianificata opzionale;
data di inizio effettiva;
data di completamento;
note operative.

Gli stati principali previsti sono:

Open;
Assigned;
In Progress;
Completed;
Cancelled.

Il sistema deve impedire transizioni chiaramente incompatibili con il normale ciclo di lavoro.

Ad esempio, un Work Order completato non dovrebbe accidentalmente tornare In Progress.

Non è però ancora stato definito se alcuni ruoli debbano poter riaprire un Work Order completato in casi eccezionali.

8. Assignment and Scheduling

Un Maintenance Manager deve poter assegnare un Work Order a un Technician.

Un Technician deve poter vedere chiaramente il proprio lavoro assegnato.

Gli interventi possono avere una data prevista.

La schermata principale del Technician dovrebbe permettergli di capire rapidamente:

cosa deve fare;
quali interventi hanno priorità maggiore;
quali interventi sono pianificati per oggi;
quali attività risultano in ritardo.

Non è richiesta nella prima versione una pianificazione avanzata delle risorse o un sistema completo di calendarizzazione.

9. Work Execution

Quando il Technician inizia un intervento, il Work Order passa allo stato In Progress.

Durante il lavoro il Technician deve poter:

aggiungere note;
aggiungere fotografie;
consultare le informazioni dell'Asset;
consultare informazioni utili sull'intervento.

Quando il lavoro viene completato deve essere registrato almeno:

chi lo ha completato;
quando è stato completato;
una descrizione del lavoro effettuato.

Le informazioni registrate sugli interventi completati costituiscono parte dello storico manutentivo e non devono andare perse.

10. Comments and Activity History

Le principali operazioni effettuate sui Work Order devono essere tracciabili.

Il sistema dovrebbe permettere di ricostruire almeno:

creazione;
assegnazione;
cambio di stato;
modifica della priorità;
completamento.

Manager e Technician devono inoltre poter aggiungere commenti o note durante la gestione dell'intervento.

Lo storico deve distinguere, quando possibile, le modifiche automatiche del sistema dalle azioni effettuate dagli utenti.

11. Attachments

Maintenance Request e Work Order devono supportare allegati fotografici.

Le fotografie saranno utilizzate principalmente da smartphone durante la segnalazione di un problema o l'esecuzione di un intervento.

Il sistema deve evitare che il caricamento di file eccessivamente grandi comprometta il normale utilizzo dell'applicazione.

Non sono ancora stati definiti:

dimensione massima degli allegati;
numero massimo di allegati;
formati supportati;
politica di conservazione dei file.
12. Search and Filtering

Maintenance Manager e Administrator devono poter ricercare e filtrare Work Order.

I principali filtri devono comprendere almeno:

stato;
priorità;
Technician;
Facility;
Asset;
intervallo temporale.

Deve inoltre essere disponibile una ricerca testuale almeno sui principali contenuti identificativi degli interventi.

I filtri utilizzati contemporaneamente devono poter essere combinati.

13. Dashboard

Administrator e Maintenance Manager devono avere una dashboard sintetica sullo stato della manutenzione.

La dashboard dovrebbe mostrare almeno informazioni relative a:

Work Order aperti;
Work Order in corso;
Work Order completati;
interventi Critical;
interventi in ritardo.

La dashboard ha finalità operative e non deve diventare nella prima versione un sistema completo di Business Intelligence.

14. Notifications

Il sistema deve rendere evidente nell'applicazione quando:

un Technician riceve una nuova assegnazione;
cambia una condizione importante relativa a un Work Order;
un intervento Critical richiede attenzione.

Sarebbe utile poter inviare notifiche anche al di fuori dell'applicazione, ma non è ancora stato deciso se la prima versione debba utilizzare email, push notification o solamente notifiche interne.

15. User Interface

Mainty deve essere utilizzabile principalmente:

da desktop per Administrator e Maintenance Manager;
da smartphone e tablet per Technician.

L'interfaccia del Technician deve essere particolarmente semplice perché può essere utilizzata durante un intervento sul campo.

Le azioni frequenti devono richiedere il minor numero ragionevole di interazioni.

L'interfaccia deve adattarsi correttamente alle principali dimensioni desktop, tablet e smartphone.

Le funzionalità amministrative possono privilegiare l'esperienza desktop.

Non è richiesta un'applicazione mobile nativa nella prima versione.

16. Connectivity

L'applicazione è una web application e normalmente richiede connessione al server.

I Technician potrebbero però lavorare in aree con connettività instabile.

Sarebbe utile permettere almeno alcune operazioni anche durante brevi interruzioni di rete, ma non è stato deciso se il supporto offline faccia parte della prima versione.

Il sistema non deve perdere silenziosamente dati inseriti dall'utente a causa di problemi di connessione.

17. Data Persistence

I dati applicativi devono essere persistenti.

Deve essere utilizzato un database relazionale per i dati strutturati principali.

Le relazioni tra utenti, Facility, Asset, Maintenance Request e Work Order devono mantenere l'integrità dei dati.

La cancellazione di dati utilizzati nello storico deve essere gestita con particolare attenzione.

In generale è preferibile disattivare entità importanti invece di cancellarle definitivamente quando esistono riferimenti storici.

18. API and Architecture

L'applicazione deve utilizzare un'architettura client/server.

Il frontend comunica con il backend tramite API HTTP.

Il backend è responsabile almeno di:

business logic;
autorizzazione;
validazione;
persistenza;
gestione delle transizioni di stato.

Frontend e backend devono essere separati in modo sufficientemente chiaro da permettere un'evoluzione indipendente.

La tecnologia specifica del backend non è ancora stata scelta.

Per il database deve essere utilizzato PostgreSQL.

19. Security

Le password non devono essere memorizzate in chiaro.

Le API devono verificare autenticazione e autorizzazione.

Gli utenti non devono poter accedere a funzionalità riservate semplicemente modificando richieste provenienti dal frontend.

I file caricati dagli utenti devono essere trattati come contenuto non affidabile.

Informazioni sensibili come password, secret e credenziali infrastrutturali non devono essere memorizzate nel repository.

20. Reliability and Data Integrity

Le operazioni principali non devono lasciare il sistema in stati incoerenti.

In particolare devono essere protette le operazioni che modificano:

assegnazioni;
stato dei Work Order;
associazioni tra Asset e Facility;
dati storici.

Gli errori devono essere comunicati all'utente senza far apparire come completata un'operazione che il backend non ha realmente salvato.

21. Performance

L'applicazione deve mantenere una buona reattività durante il normale utilizzo.

Le schermate operative principali dovrebbero caricarsi rapidamente con quantità realistiche di dati.

Liste potenzialmente grandi, come Work Order e storico degli interventi, non devono richiedere necessariamente il caricamento dell'intero dataset in una singola richiesta.

Non sono ancora stati definiti volumi massimi, tempi di risposta formali o SLA.

22. Auditability

Per le operazioni importanti deve essere possibile determinare almeno:

quale utente ha effettuato l'azione;
quale operazione è stata effettuata;
quando è avvenuta.

L'audit non deve essere modificabile dagli utenti tramite le normali funzionalità applicative.

Non è ancora stato stabilito quali operazioni debbano essere considerate sufficientemente importanti da richiedere audit permanente.

23. Initial Scope

La prima versione deve concentrarsi su:

autenticazione;
utenti e ruoli;
Facility;
Asset;
Maintenance Request;
Work Order;
assegnazione dei Technician;
ciclo di esecuzione degli interventi;
commenti e fotografie;
ricerca e filtri;
dashboard operativa;
storico manutentivo;
responsive web UI.
24. Explicitly Out of Scope

Non fanno parte della prima versione:

applicazioni native iOS o Android;
gestione economica e fatturazione;
gestione ricambi e magazzino;
acquisti;
integrazione con sensori IoT;
manutenzione predittiva;
AI per diagnosticare guasti;
sistemi ERP;
gestione di fornitori esterni;
pianificazione avanzata delle risorse;
Business Intelligence avanzata;
autenticazione tramite provider aziendali esterni.
25. Future Evolution

Il progetto potrebbe successivamente evolvere verso:

più organizzazioni indipendenti;
gestione fornitori;
inventario dei ricambi;
manutenzione preventiva ricorrente;
notifiche esterne;
modalità offline;
QR code sugli Asset;
integrazioni con sistemi esterni;
analytics avanzati.

Questi elementi non devono essere considerati automaticamente requisiti della prima versione.