# Arkord Codex Handoff

## Project Metadata

- project id: a900660b-19ba-48da-b0c6-1f0491e963e1
- project name: Mainty
- project description: Mainty Test
- target repository reference: the current project repository configured in Arkord
- target repository root: use the current project repository configured in Arkord; all paths below are repository-relative
- methodology id: arkord-hybrid-agile
- phase id: PHASE-1-1-PROJECT-INITIALIZATION

## Approved Materialization Payload

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

## Materialization Context: artifacts/SPECIFICATION/template.md

---
nodeId: <unique-specification-id>
nodeType: SPECIFICATION
title: <short descriptive title>
status: PROPOSED
summary: <concise summary>
relations:
  updatedBy: []
  governs: []
  supportedBy: []
  resolves: []
  relatedTo: []
metadata:
  revision: 1
  createdDuring: <methodology phase or workflow>
  lastUpdated: <last modification timestamp>
---

# <Specification Title>

Canonical repository path: `arkord/governance/specifications/{SPECIFICATION-ID}.md`.

Use a unique, stable `{SPECIFICATION-ID}`. Preserve the existing identifier and path when updating an existing Specification.

Official lifecycle values are `PROPOSED`, `APPROVED`, and `REJECTED`. New manual Specifications use `PROPOSED`.

## Rule or Constraint

Describe the stable and enforceable requirement. State what the project must comply with.

## Scope

Describe the project areas governed by this Specification.

## Governed Features

Reference governed Features by repository identifier when identifiers exist.

## Rationale

Explain why the rule or constraint exists. Do not duplicate full ADR rationale when an ADR is referenced.

## Related Decisions

Reference ADRs that support or explain this Specification.

## Resolved Open Points

Reference Open Points resolved by this Specification. Leave this section empty when the Specification does not resolve an Open Point.

## Notes

Record additional relevant context that does not belong in the structured sections above.

## Changelog

Record meaningful document changes according to current repository conventions.


## Materialization Context: artifacts/ADR/template.md

---
nodeId: <unique-adr-id>
nodeType: DECISION
title: <short descriptive title>
status: PROPOSED
summary: <concise decision summary>
relations:
  updatedBy: []
  resolves: []
  supports: []
  impacts: []
  supersedes: []
  supersededBy: []
  relatedTo: []
metadata:
  revision: 1
  createdDuring: <methodology phase or workflow>
  lastUpdated: <last modification timestamp>
---

# <ADR Title>

Canonical repository path: `arkord/governance/decisions/{ADR-ID}.md`.

Use a unique, stable `{ADR-ID}`. Preserve the existing identifier, path, lifecycle state, and historical relationships when updating an existing ADR.

The runtime-supported Project Context Graph node type for ADR documents is `DECISION`.

Official ADR review lifecycle values are `PROPOSED`, `APPROVED`, and `REJECTED`. Phase 1.1 materializes `PROPOSED`; Human Owner review is required.


## Materialization Context: artifacts/BLUEPRINT/template.md

# Blueprint Template

Canonical path: `arkord/governance/BLUEPRINT.md`

```yaml
---
nodeId: <unique-blueprint-id>
nodeType: BLUEPRINT
title: <project blueprint title>
summary: <concise project summary>
relations:
  updatedBy: []
  relatedTo: []
metadata:
  revision: 1
  createdDuring: <methodology phase or workflow>
  lastUpdated: <timestamp>
---
```

# <project blueprint title>

## Project Identity

<project name and stable identity information>

## Purpose

<approved project purpose>

## Goals

<approved high-level goals>

## Scope

<approved project scope>

## Exclusions

<approved exclusions or `No exclusions currently defined.`>

## Target Users and Stakeholders

<approved users, roles, stakeholders, or `Not specified.`>

## Major Capabilities

<approved high-level capabilities>

## Principal Constraints

<approved constraints>

## Architectural Direction

<approved architectural direction or `No architectural direction currently approved.`>

## Related Governance

<approved related Governance references without duplicating their full content>

## Notes

<additional approved notes or `Not applicable.`>


## Materialization Context: artifacts/ROADMAP/template.md

# Roadmap Template

Canonical path: `arkord/governance/ROADMAP.md`

```yaml
---
nodeId: <unique-roadmap-id>
nodeType: ROADMAP
title: <project roadmap title>
summary: <concise roadmap summary>
relations:
  updatedBy: []
  relatedTo: []
metadata:
  revision: 1
  createdDuring: <methodology phase or workflow>
  lastUpdated: <timestamp>
---
```

# <project roadmap title>

## Roadmap Overview

<approved high-level evolution plan>

## Evolution Areas

<approved major roadmap areas>

## Sequencing Notes

<approved sequencing notes or `No sequencing constraints currently defined.`>

## Dependencies and Constraints

<approved roadmap dependencies and constraints>

## Open Questions

<approved roadmap-level open questions or `No roadmap open questions currently defined.`>

## Related Governance and Delivery

<approved references to related Blueprint, Features, Open Points, Epics, or other nodes without duplicating their full content>

## Notes

<additional approved notes or `Not applicable.`>


## Repository Materialization Instructions

# Phase 1.1 Codex Handoff Prompt

## Execution

Treat this handoff as executable instructions.
Inspect the target repository.
Materialize exactly the approved Governance artifacts.
Do not perform new product reasoning.
Every persistent artifact must be created or updated using its authoritative Concept and Template from the Materialization context or methodology repository.

Materialize only the Governance artifacts defined by this Phase 1.1 initialization result. Do not generate or modify Delivery artifacts. Delivery generation belongs exclusively to Phase 1.2 and is derived from consolidated Governance.

## Artifact Mapping

Blueprint Outline
→ create or update exactly one file at `arkord/governance/BLUEPRINT.md` using `artifacts/BLUEPRINT/template.md`.

Roadmap Outline
→ create or update exactly one file at `arkord/governance/ROADMAP.md` using `artifacts/ROADMAP/template.md`.

Candidate Feature
→ one file under `arkord/governance/features/` using the authoritative Feature concept and template.

Candidate Specification
→ one file under `arkord/governance/specifications/` using `artifacts/SPECIFICATION/template.md`.

Candidate ADR
→ one file under `arkord/governance/decisions/` using `artifacts/ADR/template.md`.

Candidate Open Point
→ one directory under `arkord/governance/open-points/<nodeId>/` containing exactly `open-point.md` from the authoritative item template and `conversation.md` initialized with `# Resolution Conversation`. Never create a legacy `<nodeId>.md` file or place transcript messages in `open-point.md`.

## Template Loading Expectations

The assembled handoff conditionally includes required Governance templates based on the approved materialization payload:

```text
Blueprint Outline → artifacts/BLUEPRINT/template.md
Roadmap Outline → artifacts/ROADMAP/template.md
Candidate Specification → artifacts/SPECIFICATION/template.md
Candidate ADR → artifacts/ADR/template.md
```

If a required template is missing, handoff assembly must fail instead of producing an incomplete or truncated prompt. Preserve the 95,000-character safe limit and fail instead of truncating required content.

## Repository revision rules

Every newly materialized Governance artifact must include `metadata.revision: 1`. Revision is repository/Engine metadata; do not ask the Reasoning Agent to choose it. Never write `reviewState` to Governance Markdown.

## State Rules

Feature → `PROPOSED`
ADR → `PROPOSED`
Open Point → `OPEN`
Specification → `PROPOSED`
Blueprint / Roadmap → no Governance lifecycle status; Platform review begins `UNREAD`

Do not introduce new lifecycle values.

## Runtime Contracts

For every generated Governance document, inspect and follow the existing target repository conventions before writing. Use the current Project Context Graph document schema with valid YAML frontmatter, including at minimum `nodeId`, `nodeType`, `title`, `summary`, and `relations`, plus `status` for artifacts with a repository lifecycle. Use existing node types, repository paths, naming conventions, lifecycle states, and relation names. Preserve existing identifiers and graph consistency when updating equivalent documents; create unique node identifiers only for new documents.

Blueprint and Roadmap materialization are Template-driven. Create or update one of each, preserve existing identifiers, do not add an approval lifecycle, materialize only approved outline content, and do not invent dates or future scope.

ADR and Specification materialization are Template-driven. Create exactly one file for every approved candidate, assign a stable identifier and `PROPOSED` status, preserve approved content, and create only approved relationships using relation fields supported by the target repository schema. Do not turn unresolved recommendations into decisions or invent rules, relationships, node types, or lifecycle states.

## Scope Control

Codex must not:

```text
invent artifacts;
add product scope;
resolve Open Points;
generate or modify Delivery artifacts;
create Epics, Stories, Tasks, Bugs, Sprints, Delivery plans, or implementation work packages;
write source code;
modify arkord-platform;
modify the approved Initialization Plan.
```

Do not create or modify files under `arkord/delivery/`.

## Relationships

Materialize only relationships explicitly present in the approved materialization payload.
Do not infer relationships because two artifacts appear conceptually related.
Preserve bidirectional relationships when the target repository schema supports them. Do not invent alternative relation names or unsupported backlinks. Validate that generated graph frontmatter has no duplicate node IDs, invalid node types, broken references, invalid lifecycle states, or parser failures.

## Output

Return:

```text
Governance files created;
Governance files modified;
Governance artifacts materialized;
relationship validation;
unrepresentable approved relationships or conflicts.
```


# Execution Start

The execution context is complete.

Begin the approved repository materialization now.

Do not produce introductory text before inspecting and modifying the repository.
