Initialization Plan
1. Project Understanding
Project purpose

Mainty è una web application centralizzata per gestire manutenzione di strutture e asset, sostituendo processi informali basati su messaggi, fogli di calcolo e comunicazioni verbali.

Il sistema deve permettere di conoscere problemi segnalati, interventi necessari, responsabilità, stato del lavoro e storico manutentivo degli asset.

Business goals
Centralizzare la gestione delle attività di manutenzione.
Rendere tracciabili segnalazioni, interventi, assegnazioni e completamenti.
Fornire uno storico manutentivo persistente.
Consentire a Manager e Administrator di coordinare e controllare il lavoro.
Consentire ai Technician di gestire operativamente gli interventi assegnati.
Ridurre la dipendenza da strumenti e comunicazioni non strutturate.
Non precludere una futura evoluzione multi-organizzazione, senza includerla automaticamente nella prima versione.
Target users
Administrator — configurazione, utenti, ruoli, Facility, Asset, accesso globale e storico.
Maintenance Manager — gestione operativa delle segnalazioni e dei Work Order.
Technician — esecuzione sul campo degli interventi assegnati.
Functional scope
Autenticazione e gestione accesso.
Gestione utenti e ruoli.
Gestione Facility.
Gestione Asset.
Maintenance Request.
Work Order.
Assegnazione dei Work Order ai Technician.
Pianificazione basilare degli interventi.
Esecuzione e completamento degli interventi.
Commenti, note e fotografie.
Storico delle attività e degli interventi.
Ricerca e filtri.
Dashboard operativa.
Notifiche applicative per eventi rilevanti.
Responsive web UI.
Non-functional expectations
Autorizzazione verificata dal backend.
Password non memorizzate in chiaro.
Upload trattati come contenuto non affidabile.
Persistenza dei dati strutturati in PostgreSQL.
Integrità dei dati e conservazione dello storico.
Operazioni principali affidabili e consistenti.
UI desktop per ruoli gestionali e smartphone/tablet per Technician.
Buona reattività con quantità realistiche di dati.
Gestione di liste potenzialmente grandi senza obbligo di caricare l'intero dataset.
Auditabilità delle operazioni importanti.
Nessuna perdita silenziosa dei dati inseriti in presenza di problemi di connessione.
Constraints
Web application client/server.
Frontend e backend separati.
Comunicazione frontend/backend tramite API HTTP.
PostgreSQL per i dati strutturati principali.
Autenticazione richiesta.
Controlli di autorizzazione lato backend.
Singola organizzazione nella prima versione.
Nessuna applicazione mobile nativa nella prima versione.
Nessun provider di autenticazione esterno nella prima versione.
Backend technology non ancora scelta.
Known risks
Regole incomplete sulle transizioni eccezionali dei Work Order.
Requisiti degli allegati incompleti.
Strategia delle notifiche esterne non definita.
Supporto offline non deciso.
Requisiti prestazionali non quantitativi.
Perimetro dell'audit permanente non completamente definito.
L'obiettivo di non impedire il futuro multi-tenancy potrebbe influenzare scelte architetturali senza che il multi-tenancy sia attualmente requisito.
2. Reasoning Results
Facts
Mainty gestisce manutenzione di Facility e Asset.
La prima versione è destinata a una singola organizzazione.
Esistono tre ruoli principali: Administrator, Maintenance Manager e Technician.
L'accesso richiede autenticazione.
L'email identifica l'utente per l'accesso.
Gli utenti possono essere disattivati preservandone lo storico.
L'autorizzazione deve essere verificata dal backend.
Facility e Asset possono essere disattivati preservando lo storico.
Ogni Asset appartiene a una Facility.
Una Maintenance Request può riguardare una Facility senza Asset.
Le Maintenance Request supportano fotografie.
Le priorità iniziali sono Low, Medium, High e Critical.
Una Maintenance Request può portare a un Work Order.
Gli stati principali del Work Order sono Open, Assigned, In Progress, Completed e Cancelled.
Il Technician può essere assegnato a un Work Order.
L'avvio dell'intervento porta il Work Order a In Progress.
Il completamento deve registrare autore, momento e descrizione del lavoro.
Le principali operazioni sui Work Order devono essere tracciabili.
Maintenance Request e Work Order supportano fotografie.
Work Order possono essere ricercati e filtrati.
Administrator e Maintenance Manager dispongono di una dashboard operativa.
Devono esistere segnalazioni applicative per eventi importanti.
Administrator e Manager utilizzano principalmente desktop; Technician smartphone/tablet.
L'applicazione è una web application client/server.
PostgreSQL è richiesto.
Il backend gestisce business logic, autorizzazione, validazione, persistenza e transizioni di stato.
Password, secret e credenziali infrastrutturali non devono essere memorizzati in forma non sicura o nel repository secondo quanto applicabile.
La prima versione non comprende le capacità dichiarate Explicitly Out of Scope.
Inferences
Facility, Asset, Maintenance Request e Work Order costituiscono entità di dominio distinte, perché il Brief attribuisce loro identità, dati e comportamenti differenti.
Lo storico manutentivo dipende dalla conservazione delle relazioni tra Work Order completati, Asset, Facility e utenti coinvolti.
La disattivazione è distinta dalla cancellazione per utenti, Facility e Asset perché il Brief richiede esplicitamente conservazione storica.
L'esecuzione sul campo richiede un'esperienza UI distinta per priorità d'uso rispetto alle funzioni amministrative, pur rimanendo nella stessa web application.
Il sistema necessita di enforcement dei ruoli lato server perché la sola restrizione UI è esplicitamente insufficiente.
Critical costituisce una priorità con rilevanza operativa particolare perché deve essere chiaramente distinguibile e richiedere attenzione.
Open Point Signals
Non è definito se e come un Work Order Completed possa essere riaperto.
I limiti e le politiche degli allegati non sono definiti.
Non è deciso se la prima versione debba includere notifiche esterne e con quale canale.
Non è deciso se la prima versione debba supportare operazioni offline.
Non sono definiti volumi, tempi di risposta o SLA quantitativi.
Non è definito il perimetro esatto delle operazioni soggette ad audit permanente.
Non è definito quanto l'architettura della prima versione debba concretamente prepararsi al futuro multi-tenancy.
Risks
Una definizione incompleta del lifecycle dei Work Order può produrre comportamenti incoerenti.
Allegati senza limiti definiti possono influire su sicurezza, storage e performance.
Connettività instabile può compromettere l'esperienza sul campo se non è chiaro il comportamento in caso di failure.
Requisiti prestazionali qualitativi possono produrre interpretazioni differenti della conformità.
Un audit scope non definito può portare a tracciamento insufficiente o eccessivo.
Anticipare eccessivamente il futuro multi-tenancy potrebbe introdurre complessità non necessaria nella prima versione.
3. Governance Proposal
Blueprint Outline
Project Identity

Mainty è una web application per la gestione centralizzata della manutenzione di Facility e Asset di una singola organizzazione.

Purpose

Gestire l'intero flusso operativo dalla segnalazione di un problema alla pianificazione, assegnazione, esecuzione e storicizzazione dell'intervento.

Goals
Centralizzazione delle attività di manutenzione.
Tracciabilità del lavoro.
Coordinamento tra ruoli gestionali e Technician.
Conservazione dello storico.
Accesso rapido alle informazioni operative.
Esperienza adeguata sia alla gestione desktop sia al lavoro sul campo.
Scope

Autenticazione, utenti e ruoli, Facility, Asset, Maintenance Request, Work Order, assegnazioni, esecuzione, commenti, fotografie, ricerca, filtri, dashboard, notifiche applicative e storico.

Principal constraints

Web application client/server, API HTTP, PostgreSQL, autenticazione, autorizzazione backend, conservazione dei dati storici e responsive UI.

Architectural direction

Frontend e backend separati; backend responsabile delle regole applicative e della persistenza; database relazionale PostgreSQL.

Evolution boundary

Multi-organizzazione, offline completo, notifiche esterne e altre evoluzioni future non devono essere trattate automaticamente come scope corrente.

Roadmap Outline
Stage 1 — Foundation and Access

Autenticazione, utenti, ruoli e fondazioni applicative.

Stage 2 — Maintenance Domain Foundation

Facility e Asset con relazioni e conservazione storica.

Stage 3 — Maintenance Intake

Maintenance Request, priorità e fotografie.

Stage 4 — Work Management

Work Order, assegnazioni, scheduling basilare e lifecycle operativo.

Stage 5 — Field Execution

Esperienza Technician, note, fotografie, avvio e completamento degli interventi.

Stage 6 — Operational Visibility

Storico, ricerca, filtri, dashboard e notifiche applicative.

Stage 7 — Quality and Operational Hardening

Sicurezza, integrità, auditabilità, performance e gestione degli errori secondo i requisiti approvati.

Le fasi descrivono progressione logica e non introducono date, sprint o scheduling.

Candidate Features
Feature — Authentication and User Access

Summary: Accesso autenticato e gestione dell'identità applicativa.

Purpose: Consentire accesso controllato agli utenti Mainty.

Functional Scope: Login, utenti attivi/disattivati e associazione del ruolo.

Out of Scope: Google, Microsoft e SSO aziendale nella prima versione.

Functional Rules: Gli utenti disattivati non possono accedere; i dati storici restano conservati.

Related Governance: Governata dalle specifiche di autenticazione, autorizzazione e sicurezza.

Expected Delivery Derivation: Flussi di autenticazione e gestione della sessione/accesso.

Classification Reason: È una capacità funzionale stabile offerta dal sistema, mentre le regole di sicurezza che la governano appartengono alle Specification.

Feature — User and Role Administration

Summary: Gestione degli utenti e dei relativi ruoli.

Purpose: Permettere all'Administrator di amministrare gli accessi al sistema.

Functional Scope: Creazione/modifica utenti, ruolo, attivazione/disattivazione.

Functional Rules: Il Technician non dispone delle funzioni amministrative.

Related Governance: Autorizzazione backend e conservazione storica.

Expected Delivery Derivation: Interfacce e servizi amministrativi per utenti e ruoli.

Classification Reason: Rappresenta una capacità applicativa permanente, non una regola trasversale.

Feature — Facility Management

Summary: Gestione delle strutture fisiche dell'organizzazione.

Purpose: Organizzare Asset e manutenzione rispetto alle strutture gestite.

Functional Scope: Creazione, modifica, consultazione e disattivazione Facility.

Functional Rules: Le Facility inattive restano nello storico e non sono normalmente utilizzate per nuove attività.

Related Governance: Asset Management e conservazione storica.

Expected Delivery Derivation: CRUD e consultazione Facility con gestione dello stato.

Classification Reason: È una capacità funzionale autonoma del dominio.

Feature — Asset Management

Summary: Gestione degli asset fisici soggetti a manutenzione.

Purpose: Identificare gli elementi mantenuti e collegarne lo storico.

Functional Scope: Creazione, modifica, consultazione, associazione a Facility, disattivazione e storico.

Functional Rules: Ogni Asset appartiene a una Facility; gli Asset disattivati mantengono lo storico.

Related Governance: Facility Management, Work Orders e storico manutentivo.

Expected Delivery Derivation: Gestione Asset e relativa consultazione storica.

Classification Reason: Modella una capacità funzionale stabile relativa a un'entità centrale del dominio.

Feature — Maintenance Request Management

Summary: Segnalazione e gestione iniziale dei problemi manutentivi.

Purpose: Acquisire problemi che possono richiedere un intervento.

Functional Scope: Creazione e consultazione delle segnalazioni, priorità, Facility, Asset opzionale e fotografie.

Functional Rules: Una richiesta può esistere senza Asset; Critical deve essere distinguibile.

Related Governance: Work Order Management, Attachment Handling e prioritizzazione.

Expected Delivery Derivation: Flussi di segnalazione e gestione Maintenance Request.

Classification Reason: È una capacità utente stabile distinta dal lavoro pianificato rappresentato dal Work Order.

Feature — Work Order Management

Summary: Gestione del lavoro manutentivo pianificato ed eseguito.

Purpose: Trasformare necessità manutentive in attività operative controllabili.

Functional Scope: Creazione, modifica, priorità, stato, pianificazione, assegnazione e completamento.

Out of Scope: Pianificazione avanzata delle risorse.

Functional Rules: Lifecycle principale Open, Assigned, In Progress, Completed, Cancelled; transizioni incompatibili devono essere impedite.

Related Governance: Assignment, Work Execution, History e lifecycle Work Order.

Expected Delivery Derivation: Gestione completa del Work Order.

Classification Reason: Rappresenta una capacità funzionale centrale; le regole esatte delle transizioni appartengono alle Specification/Open Point quando irrisolte.

Feature — Technician Assignment and Work Queue

Summary: Assegnazione del lavoro e visualizzazione delle attività del Technician.

Purpose: Coordinare responsabilità e priorità operative.

Functional Scope: Assegnazione del Technician e visualizzazione di lavoro assegnato, priorità, attività odierne e ritardi.

Functional Rules: L'assegnazione è effettuata dal Maintenance Manager.

Related Governance: Work Order Management e Role Authorization.

Expected Delivery Derivation: Flussi di assegnazione e vista operativa Technician.

Classification Reason: È una capacità funzionale riconoscibile separatamente dalle regole che governano autorizzazione e stato.

Feature — Work Execution

Summary: Esecuzione sul campo di un Work Order.

Purpose: Consentire al Technician di documentare e completare il lavoro.

Functional Scope: Avvio, note, fotografie, consultazione Asset, registrazione del lavoro e completamento.

Functional Rules: L'avvio porta il Work Order a In Progress; il completamento registra autore, momento e descrizione.

Related Governance: Work Order Management, Attachments e History.

Expected Delivery Derivation: Esperienza operativa Technician durante l'intervento.

Classification Reason: È una capacità funzionale stabile dedicata all'esecuzione del lavoro.

Feature — Comments and Maintenance History

Summary: Consultazione e registrazione della storia operativa.

Purpose: Rendere ricostruibili attività e interventi nel tempo.

Functional Scope: Commenti/note e storico delle principali operazioni e degli interventi sugli Asset.

Functional Rules: Le informazioni storiche completate non devono andare perse.

Related Governance: Auditability, Asset Management e Work Orders.

Expected Delivery Derivation: Timeline/storico e commenti.

Classification Reason: È una capacità funzionale consultabile dagli utenti; i requisiti di audit sono invece vincoli di Governance.

Feature — Attachment Management

Summary: Gestione delle fotografie associate a segnalazioni e interventi.

Purpose: Documentare visivamente problemi e lavori.

Functional Scope: Upload e consultazione di fotografie per Maintenance Request e Work Order.

Functional Rules: I file caricati sono contenuto non affidabile.

Related Governance: Security e unresolved attachment policy.

Expected Delivery Derivation: Upload, associazione e consultazione allegati.

Classification Reason: L'upload e consultazione sono capacità funzionali; limiti e sicurezza sono Specification/Open Point.

Feature — Work Order Search and Filtering

Summary: Ricerca e filtraggio degli interventi.

Purpose: Consentire a Manager e Administrator di individuare rapidamente il lavoro rilevante.

Functional Scope: Filtri per stato, priorità, Technician, Facility, Asset, periodo e ricerca testuale.

Functional Rules: I filtri possono essere combinati.

Related Governance: Work Order Management e performance.

Expected Delivery Derivation: Query, filtri e UI di ricerca.

Classification Reason: È una capacità funzionale permanente.

Feature — Operational Dashboard

Summary: Vista sintetica dello stato della manutenzione.

Purpose: Fornire visibilità operativa ad Administrator e Maintenance Manager.

Functional Scope: Work Order aperti, in corso, completati, Critical e in ritardo.

Out of Scope: Business Intelligence avanzata.

Functional Rules: Accessibile ai ruoli gestionali previsti.

Related Governance: Work Order Management.

Expected Delivery Derivation: Dashboard e relative aggregazioni.

Classification Reason: È una capacità funzionale user-facing.

Feature — In-App Operational Notifications

Summary: Evidenziazione nell'applicazione di eventi operativi importanti.

Purpose: Portare all'attenzione degli utenti assegnazioni e condizioni rilevanti.

Functional Scope: Nuove assegnazioni, condizioni importanti dei Work Order e attenzione ai Critical.

Out of Scope: Il canale esterno non è ancora definito.

Functional Rules: Gli eventi indicati devono essere resi evidenti nell'applicazione.

Related Governance: Assignment e Work Orders.

Expected Delivery Derivation: Meccanismo e UI delle notifiche interne.

Classification Reason: La notifica interna è una capacità richiesta; l'eventuale notifica esterna rimane un'incertezza separata.

Candidate Specifications
Specification — Backend Authorization Enforcement

Rule or Constraint: Le autorizzazioni devono essere applicate dal backend e non affidate esclusivamente alla UI.

Scope: Tutte le operazioni protette.

Governed Features: Authentication and User Access, User and Role Administration e tutte le capacità soggette a ruoli.

Rationale: Requisito esplicito di sicurezza e accesso.

Related Decisions: Architettura client/server.

Classification Reason: È un vincolo di sicurezza trasversale, non una capacità funzionale.

Specification — Historical Data Preservation

Rule or Constraint: Dati storici associati a utenti, Facility, Asset e interventi devono essere preservati quando le entità vengono disattivate o non sono più operative.

Scope: Entità con riferimenti storici.

Governed Features: User Administration, Facility Management, Asset Management, Work Order Management, Maintenance History.

Rationale: Il Brief richiede ripetutamente conservazione dello storico.

Related Decisions: Persistenza relazionale.

Classification Reason: È una regola stabile di integrità e conservazione dati.

Specification — Asset–Facility Relationship

Rule or Constraint: Ogni Asset deve appartenere a una Facility.

Scope: Asset.

Governed Features: Facility Management, Asset Management.

Rationale: Relazione esplicitamente richiesta.

Related Decisions: Persistenza relazionale.

Classification Reason: È una regola stabile del modello di dominio.

Specification — Maintenance Request Association

Rule or Constraint: Ogni Maintenance Request riguarda una Facility e può opzionalmente riferirsi a un Asset.

Scope: Maintenance Request.

Governed Features: Maintenance Request Management.

Rationale: Requisito esplicito del Brief.

Related Decisions: Persistenza relazionale.

Classification Reason: È una regola di modello che governa la Feature.

Specification — Maintenance Priority Model

Rule or Constraint: Le priorità iniziali sono Low, Medium, High e Critical; Critical deve essere chiaramente distinguibile.

Scope: Maintenance Request e Work Order dove applicabile.

Governed Features: Maintenance Request Management, Work Order Management, Dashboard, Technician Work Queue.

Rationale: Modello di priorità esplicitamente definito.

Related Decisions: Nessuna decisione separata necessaria.

Classification Reason: È un modello/regola trasversale e non una capacità autonoma.

Specification — Work Order Lifecycle Baseline

Rule or Constraint: Gli stati principali sono Open, Assigned, In Progress, Completed e Cancelled; transizioni chiaramente incompatibili devono essere impedite; iniziare un intervento porta a In Progress.

Scope: Work Order.

Governed Features: Work Order Management, Work Execution.

Rationale: Lifecycle esplicitamente descritto.

Related Decisions: La riapertura di Completed resta unresolved.

Classification Reason: È una regola di lifecycle che governa Feature funzionali; la parte non definita viene preservata come Open Point.

Specification — Work Completion Record

Rule or Constraint: Il completamento registra chi ha completato, quando e la descrizione del lavoro effettuato.

Scope: Work Order completion.

Governed Features: Work Execution, Maintenance History.

Rationale: Requisito esplicito per lo storico manutentivo.

Related Decisions: Nessuna.

Classification Reason: È un contratto stabile sui dati e comportamento di completamento.

Specification — Work Order Activity Traceability

Rule or Constraint: Devono essere ricostruibili almeno creazione, assegnazione, cambio stato, modifica priorità e completamento; quando possibile va distinta l'origine automatica dalle azioni utente.

Scope: Work Order history.

Governed Features: Work Order Management, Comments and Maintenance History.

Rationale: Requisito esplicito di tracciabilità.

Related Decisions: Audit scope permanente resta distinto e parzialmente unresolved.

Classification Reason: È una regola di tracciabilità, non una Feature.

Specification — Responsive Role-Oriented Web UI

Rule or Constraint: La web UI deve adattarsi a desktop, tablet e smartphone; Administrator/Manager privilegiano desktop e Technician smartphone/tablet; l'esperienza Technician deve minimizzare ragionevolmente le interazioni frequenti.

Scope: UI user-facing.

Governed Features: Tutte le Feature user-facing.

Rationale: Requisiti UX espliciti.

Related Decisions: Web application, nessuna mobile app nativa.

Classification Reason: È un quality/compatibility constraint trasversale.

Specification — Relational Persistence

Rule or Constraint: I dati strutturati principali devono essere persistiti in PostgreSQL mantenendo l'integrità delle relazioni di dominio.

Scope: Persistenza applicativa strutturata.

Governed Features: Tutte le Feature con dati persistenti.

Rationale: PostgreSQL e database relazionale sono requisiti espliciti.

Related Decisions: ADR PostgreSQL.

Classification Reason: È un vincolo architetturale/data model, non una capacità funzionale.

Specification — Secure Credential and Upload Handling

Rule or Constraint: Password non in chiaro; secret e credenziali infrastrutturali fuori dal repository; file caricati trattati come contenuto non affidabile.

Scope: Authentication, configuration e attachments.

Governed Features: Authentication and User Access, Attachment Management.

Rationale: Requisiti di sicurezza espliciti.

Related Decisions: Architettura backend.

Classification Reason: È un insieme coerente di vincoli di sicurezza permanenti.

Specification — Transactional Consistency of Critical Operations

Rule or Constraint: Le operazioni principali non devono lasciare stati incoerenti; particolare attenzione ad assegnazioni, lifecycle Work Order, associazioni Asset/Facility e storico.

Scope: Operazioni mutative principali.

Governed Features: Work Order Management, Assignment, Asset Management, History.

Rationale: Requisito esplicito di reliability/data integrity.

Related Decisions: Persistenza relazionale.

Classification Reason: È un reliability constraint trasversale.

Specification — Honest Operation Failure Feedback

Rule or Constraint: Un errore backend non deve essere presentato all'utente come operazione completata con successo.

Scope: Operazioni mutative user-facing.

Governed Features: Tutte le Feature applicative che modificano dati.

Rationale: Requisito esplicito di affidabilità.

Related Decisions: Client/server architecture.

Classification Reason: È una regola di affidabilità dell'interfaccia e del contratto client/server.

Specification — Large List Data Access

Rule or Constraint: Liste potenzialmente grandi non devono richiedere necessariamente il caricamento dell'intero dataset in una singola richiesta.

Scope: Work Order list e storico.

Governed Features: Search and Filtering, Maintenance History, Dashboard dove applicabile.

Rationale: Requisito prestazionale esplicito.

Related Decisions: API HTTP.

Classification Reason: È un quality/performance constraint.

Candidate ADRs
ADR — Client/Server Web Architecture

Decision: Utilizzare una web application con frontend e backend separati comunicanti tramite API HTTP.

Context: Mainty deve servire esperienze desktop e mobile-web mantenendo business logic e sicurezza lato server.

Rationale: Il Project Brief prescrive esplicitamente questa direzione.

Alternatives: Architettura monolitica senza separazione frontend/backend; applicazioni native; altre forme di integrazione non richieste.

Consequences: Il backend diventa responsabile di business logic, autorizzazione, validazione, persistenza e lifecycle; frontend e backend possono evolvere separatamente.

Affected Features or Specifications: Tutte le Feature applicative; Backend Authorization Enforcement; Honest Operation Failure Feedback.

Resolved Open Points: Nessuno.

Classification Reason: È una decisione architetturale esplicitamente confermata con conseguenze permanenti e quindi richiede rationale tracciabile.

ADR — PostgreSQL for Structured Persistence

Decision: Utilizzare PostgreSQL per i dati strutturati principali.

Context: Il dominio contiene numerose relazioni persistenti e richiede integrità e storico.

Rationale: PostgreSQL è esplicitamente richiesto dal Brief.

Alternatives: Altri database relazionali o modelli non relazionali, non selezionati.

Consequences: Il modello persistente strutturato deve essere compatibile con PostgreSQL e con l'integrità relazionale richiesta.

Affected Features or Specifications: Relational Persistence e tutte le Feature persistenti.

Resolved Open Points: Nessuno.

Classification Reason: È una scelta tecnologica concreta già confermata che deve rimanere tracciabile nel tempo.

ADR — Web-Only First Version

Decision: La prima versione utilizza responsive web UI e non include applicazioni native iOS/Android.

Context: Technician lavora principalmente da smartphone/tablet, mentre ruoli gestionali privilegiano desktop.

Rationale: Il Brief esclude esplicitamente una mobile app nativa nella prima versione.

Alternatives: App native iOS/Android; combinazione web/native.

Consequences: Le esperienze desktop e sul campo devono essere supportate dalla web application.

Affected Features or Specifications: Responsive Role-Oriented Web UI e tutte le Feature user-facing.

Resolved Open Points: Nessuno.

Classification Reason: È una decisione di piattaforma esplicitamente definita con conseguenze durature sulla soluzione.

Candidate Open Points
Open Point — Reopening Completed Work Orders

Problem: Non è definito se un Work Order completato possa essere riaperto eccezionalmente e da quali ruoli.

Source of Uncertainty: Il Brief vieta il ritorno accidentale a In Progress ma dichiara esplicitamente irrisolta la riapertura eccezionale.

Project Impact: Influenza il lifecycle operativo e la gestione delle correzioni post-completamento.

Technical Impact: Influenza transizioni di stato, autorizzazioni e storico.

Proposed Resolution: Definire se la riapertura è consentita, a quali ruoli e verso quale stato.

Alternatives: Nessuna riapertura; riapertura solo Manager; riapertura Administrator/Manager con tracciamento.

Recommendation: Definire esplicitamente la policy prima di considerare completo il lifecycle.

Affected Governance Areas: Work Order Lifecycle Baseline, Work Order Management, History, Authorization.

Classification Reason: È un'incertezza esplicita con impatto significativo sul dominio e non può essere inferita.

Open Point — Attachment Policy

Problem: Limiti, formati e retention degli allegati non sono definiti.

Source of Uncertainty: Il Brief identifica esplicitamente questi valori come non definiti.

Project Impact: Influenza esperienza di upload e gestione dei contenuti.

Technical Impact: Influenza validazione, sicurezza, storage, trasferimento e retention.

Proposed Resolution: Definire formati supportati, dimensione massima, quantità massima e retention.

Alternatives: Policy restrittiva; policy più permissiva; limiti differenziati per contesto.

Recommendation: Stabilire una policy minima verificabile prima della finalizzazione dell'Attachment Management.

Affected Governance Areas: Attachment Management, Security, Performance.

Classification Reason: È un'incertezza esplicita con impatto tecnico e operativo significativo.

Open Point — External Notification Scope

Problem: Non è definito se la prima versione includa notifiche esterne.

Source of Uncertainty: Il Brief richiede evidenza in-app ma lascia aperti email, push o sole notifiche interne.

Project Impact: Può ampliare il perimetro della Notification Feature.

Technical Impact: Può richiedere provider esterni, delivery channels e gestione failure.

Proposed Resolution: Decidere se la prima versione rimane in-app only o include un canale esterno specifico.

Alternatives: Solo in-app; email; push; combinazione.

Recommendation: Mantenere separata la capacità in-app già confermata dalla decisione sul canale esterno.

Affected Governance Areas: In-App Operational Notifications e futura notification architecture.

Classification Reason: È una decisione di scope esplicitamente irrisolta.

Open Point — Offline Operation Scope

Problem: Non è definito se Mainty debba permettere operazioni durante interruzioni di rete.

Source of Uncertainty: Il Brief riconosce connettività instabile ma non decide se offline faccia parte della prima versione.

Project Impact: Può modificare significativamente l'esperienza Technician e lo scope della prima versione.

Technical Impact: Può introdurre storage locale, sincronizzazione e gestione conflitti.

Proposed Resolution: Decidere se la prima versione sia online-only con gestione esplicita degli errori oppure supporti un insieme definito di operazioni offline.

Alternatives: Online-only; resilienza temporanea senza editing offline; subset offline; supporto offline più ampio.

Recommendation: Non introdurre implicitamente offline finché non viene deciso il perimetro.

Affected Governance Areas: Work Execution, UI, Reliability, Architecture.

Classification Reason: È un'incertezza esplicita con elevato impatto potenziale e non può essere trattata come semplice dettaglio implementativo.

Open Point — Performance Acceptance Criteria

Problem: “Buona reattività” e “quantità realistiche” non hanno criteri quantitativi verificabili.

Source of Uncertainty: Volumi, response time e SLA non sono definiti.

Project Impact: Rende ambigua la validazione dei requisiti prestazionali.

Technical Impact: Influenza test, query, pagination e dimensionamento.

Proposed Resolution: Definire almeno dataset/volumi di riferimento e criteri di risposta per le schermate principali.

Alternatives: Mantenere criteri qualitativi; definire target minimi; introdurre SLA più formali.

Recommendation: Definire criteri verificabili prima della validazione prestazionale finale.

Affected Governance Areas: Large List Data Access, Search, History, Dashboard.

Classification Reason: È un'incertezza misurabile che influenza la conformità a un requisito di qualità.

Open Point — Permanent Audit Scope

Problem: Non è definito quali operazioni richiedano audit permanente.

Source of Uncertainty: Il Brief prescrive auditabilità per operazioni importanti ma lascia aperto il loro insieme.

Project Impact: Influenza responsabilità e capacità di ricostruzione degli eventi.

Technical Impact: Influenza modello audit, retention e copertura degli eventi.

Proposed Resolution: Identificare l'insieme minimo di eventi soggetti ad audit permanente.

Alternatives: Solo eventi security-sensitive; eventi di dominio principali; audit esteso delle mutazioni.

Recommendation: Partire dagli eventi con impatto su accesso, assegnazioni, lifecycle e storico, lasciando la decisione finale al Human Owner.

Affected Governance Areas: Activity Traceability, Security, Work Orders, User Administration.

Classification Reason: Il requisito esiste ma il suo confine è esplicitamente irrisolto e materialmente significativo.

Open Point — Future Multi-Organization Architectural Boundary

Problem: La prima versione è single-organization, ma viene richiesto che l'architettura non impedisca una futura evoluzione multi-organizzazione senza specificare cosa ciò richieda oggi.

Source of Uncertainty: Il Brief combina uno scope corrente single-organization con un obiettivo architetturale futuro non formalizzato.

Project Impact: Può causare overengineering oppure rendere costosa l'evoluzione futura.

Technical Impact: Può influenzare modello dati, ownership, isolamento e autenticazione.

Proposed Resolution: Definire il livello minimo di compatibilità futura richiesto alla prima versione senza implementare multi-tenancy.

Alternatives: Nessun requisito corrente oltre a evitare dipendenze palesemente irreversibili; predisposizione strutturale minima; modellazione organization-aware fin dalla prima versione.

Recommendation: Definire esplicitamente il confine per evitare che “non impedire” venga interpretato come implementazione anticipata del multi-tenancy.

Affected Governance Areas: Blueprint, Relational Persistence, Authentication, Facility/Asset ownership, Architecture.

Classification Reason: È un'incertezza architetturale reale derivante da due indicazioni confermate ma non sufficienti a determinare una singola soluzione.

4. Delivery Seed
Initial Epics
Authentication and Access Foundation
Realizzare autenticazione, utenti, ruoli e enforcement delle autorizzazioni.
Facility and Asset Registry
Realizzare gestione Facility, Asset, relazioni e conservazione dello storico.
Maintenance Request Intake
Realizzare segnalazioni, priorità e fotografie.
Work Order Management
Realizzare creazione, lifecycle, priorità, pianificazione basilare e gestione Work Order.
Technician Assignment and Field Execution
Realizzare assegnazione, work queue Technician, esecuzione, note, fotografie e completamento.
Maintenance History and Traceability
Realizzare storico manutentivo, commenti e tracciamento delle attività richieste.
Search and Operational Visibility
Realizzare ricerca, filtri e dashboard operativa.
Operational Notifications
Realizzare le notifiche applicative confermate, mantenendo eventuali canali esterni subordinati alla risoluzione dell'Open Point.
Quality, Security and Reliability Hardening
Applicare e verificare i vincoli trasversali di sicurezza, integrità, responsive UX, error handling e performance approvati.
5. Explicitly Out of Scope

Per la prima versione:

applicazioni native iOS/Android;
gestione economica e fatturazione;
ricambi e magazzino;
acquisti;
IoT;
manutenzione predittiva;
AI per diagnosi;
ERP;
fornitori esterni;
pianificazione avanzata delle risorse;
Business Intelligence avanzata;
autenticazione tramite provider aziendali esterni;
multi-organizzazione come capacità funzionale corrente;
qualsiasi elemento della Future Evolution non successivamente approvato come Governance corrente;
Stories, Tasks, Bugs e Sprints durante Phase 1.1.
6. Analysis Confidence

Confidence Level: High

Reason: Il Project Brief è sostanzialmente completo e definisce chiaramente dominio, utenti, principali capacità, numerose regole, vincoli architetturali e scope della prima versione. Le principali aree non determinate sono esplicitamente riconoscibili e possono essere conservate come Open Point senza impedire la materializzazione di una Governance iniziale utile. Alcuni dettagli di policy e qualità rimangono deliberatamente irrisolti e richiederanno decisioni successive del Human Owner.

7. User Approval Required

Il Human Owner deve approvare, rigettare o richiedere modifiche a questo Initialization Plan prima della materializzazione della Governance e del Delivery Seed nel repository. Le Candidate Feature, Specification, ADR e Open Point qui definite sono proposte analitiche e non costituiscono ancora artifact persistenti o decisioni Governance approvate.