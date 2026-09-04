# Arkord Codex Handoff

## Project Metadata

- project id: 411f8899-a5cb-49d2-988a-965f53be30a7
- project name: Mainty test 2
- project description: Mainty test 2
- target repository reference: the current project repository configured in Arkord
- target repository root: use the current project repository configured in Arkord; all paths below are repository-relative
- methodology id: arkord-hybrid-agile
- phase id: PHASE-1-1-PROJECT-INITIALIZATION

## Approved Materialization Payload

3. Governance Proposal
Blueprint Outline
Identity

TaskFlow Lite.

Purpose

Applicazione web per la gestione semplice delle attività personali.

Goals
Gestione delle attività personali.
Organizzazione rapida.
Semplicità d'uso.
Major capabilities
Gestione attività.
Filtraggio attività.
Persistenza.
Scope

Gestione e visualizzazione persistente delle attività personali.

Exclusions
Autenticazione.
Collaborazione.
Notifiche.
Applicazione mobile.
Constraints
Web application.
Client/server.
REST API.
Database relazionale.
Persistenza.
Architectural direction

Client/server con comunicazione REST e persistenza relazionale, come già definito nel Project Brief.

Roadmap Outline
Initial evolution area

Realizzazione delle capability necessarie a TaskFlow Lite:

gestione attività;
filtraggio;
persistenza;
esperienza web responsive e semplice.

La sequenza tra queste aree non viene determinata durante l'analisi.

La definizione dell'organizzazione/sequenza della Roadmap è preservata come Candidate Open Point.

Candidate Features
Feature — Task Management

Summary: capacità di gestire il ciclo operativo delle attività personali.

Purpose: permettere all'utente di mantenere il proprio elenco di attività.

Functional Scope:

creare attività;
modificare titolo e descrizione;
completare attività;
eliminare attività;
visualizzare attività.

Out of Scope:

collaborazione;
notifiche;
autenticazione.

Functional Rules: le operazioni sopra elencate devono essere disponibili sulle attività.

Related Governance: vincoli di persistenza, responsive UI e architettura applicativa.

Expected Delivery Derivation: futura Delivery relativa alla gestione delle attività, da determinare in Phase 1.2.

Classification Reason: è una Feature perché rappresenta una capability stabile che il sistema deve fornire, non una regola, una decisione o un'incertezza. La metodologia definisce infatti le Features come capacità funzionali permanenti.

Feature — Task Filtering

Summary: capacità di filtrare l'elenco delle attività in base al loro stato.

Purpose: consentire una rapida organizzazione e consultazione delle attività.

Functional Scope:

tutte;
completate;
da completare.

Out of Scope: criteri di filtro ulteriori non definiti dal brief.

Functional Rules: devono essere disponibili esattamente le categorie di filtro confermate dal brief.

Related Governance: Task Management.

Expected Delivery Derivation: futura Delivery relativa alla visualizzazione filtrata, da determinare in Phase 1.2.

Classification Reason: è una Feature perché rappresenta un comportamento funzionale richiesto al sistema. Non viene classificata come Specification perché descrive cosa il prodotto deve poter fare e non un vincolo che governa altre capability.

Candidate Specifications
Specification — Responsive User Interface

Rule or Constraint: l'applicazione deve essere responsive.

Scope: interfaccia web user-facing.

Governed Features: Task Management; Task Filtering.

Rationale: requisito non funzionale esplicitamente stabilito dal Project Brief.

Related Decisions: nessuna relazione decisionale viene inferita.

Classification Reason: è una Specification perché rappresenta un quality constraint stabile che le capability user-facing devono rispettare; la metodologia cita esplicitamente Responsive UI come esempio di Specification.

Specification — Simple and Easily Usable Interface

Rule or Constraint: l'interfaccia deve essere semplice e facilmente utilizzabile.

Scope: interfaccia delle capability user-facing.

Governed Features: Task Management; Task Filtering.

Rationale: requisito non funzionale confermato dal Project Brief.

Related Decisions: nessuna.

Classification Reason: rappresenta una condizione qualitativa permanente che governa le capability, anziché una capability autonoma.

Specification — Low-interaction Primary Operations

Rule or Constraint: le operazioni principali devono essere eseguibili con pochi clic.

Scope: interazioni principali dell'applicazione.

Governed Features: principalmente Task Management e Task Filtering.

Rationale: requisito non funzionale esplicitamente dichiarato.

Related Decisions: nessuna.

Classification Reason: è un vincolo di qualità/usabilità che deve rimanere valido indipendentemente dalla specifica implementazione.

Specification — Relational Persistence

Rule or Constraint: la persistenza dei dati deve utilizzare un database relazionale.

Scope: dati persistenti dell'applicazione.

Governed Features: Task Management e capability che utilizzano dati persistenti.

Rationale: vincolo tecnico esplicitamente definito.

Related Decisions: la relazione con un eventuale ADR viene mantenuta irrisolta nel Candidate Open Point dedicato.

Classification Reason: è una Specification perché stabilisce un vincolo persistente sul modello di persistenza. La metodologia identifica esplicitamente il Relational Persistence Model come esempio di Specification.

Specification — REST Communication Constraint

Rule or Constraint: frontend e backend devono comunicare mediante API REST.

Scope: comunicazione client/server.

Governed Features: capability che richiedono comunicazione tra frontend e backend.

Rationale: modalità di comunicazione esplicitamente definita dal brief.

Related Decisions: eventuale ADR REST rimane oggetto di Open Point.

Classification Reason: è una Specification perché rappresenta un interface/architectural constraint stabile, non una capability funzionale.

Candidate ADRs

Nessun Candidate ADR completo viene proposto in questa fase.

Il brief dichiara già definite tre direzioni architetturali:

client/server;
database relazionale;
REST.

Tuttavia, un ADR deve preservare anche contesto, alternative e rationale. La metodologia vieta di inventare tali elementi quando non sono disponibili.

Le tre questioni vengono quindi mantenute come Candidate Open Points, anziché produrre ADR artificialmente completi.

Candidate Open Points
Open Point — Target User Definition

Problem: il brief parla genericamente di utenti e attività personali senza definire esplicitamente il target user.

Source of Uncertainty: Project Brief.

Project Impact: può influenzare interpretazione dello scope, aspettative UX e futura evoluzione delle Features.

Technical Impact: nessun impatto tecnico specifico può essere stabilito con le informazioni disponibili.

Proposed Resolution: definire esplicitamente il target user previsto.

Alternatives:

utilizzatore individuale generico;
altro target user definito dal Human Owner.

Recommendation: formalizzare il target senza introdurre nuovi segmenti utente non richiesti.

Affected Governance Areas: Blueprint; Task Management; Task Filtering.

Classification Reason: l'informazione non è un Fact né una deduzione inevitabile; richiede chiarificazione umana e può influenzare futura Governance. Soddisfa quindi i criteri di Open Point.

Open Point — Roadmap Sequencing

Problem: il Project Brief richiede una Roadmap iniziale ma non specifica la sequenza evolutiva delle capability.

Source of Uncertainty: assenza di sequencing intent nel Project Brief.

Project Impact: influenza la rappresentazione dell'evoluzione prevista del progetto.

Technical Impact: nessun ordine tecnico può essere stabilito senza introdurre pianificazione.

Proposed Resolution: determinare il livello di articolazione della Roadmap.

Alternatives:

unico incremento iniziale;
più aree/incrementi evolutivi;
roadmap senza sequencing ulteriore rispetto allo scope confermato.

Recommendation: mantenere la Roadmap al livello minimo supportato dai Facts finché il Human Owner non stabilisce una sequenza.

Affected Governance Areas: Roadmap.

Classification Reason: esiste una decisione di Governance non risolvibile mediante inferenza affidabile; inventare la sequenza violerebbe il confine tra analisi e design/pianificazione.

Open Point — Governance Treatment of Relational Database Decision

Problem: il database relazionale è dichiarato sia come vincolo tecnico sia come decisione architetturale già definita, ma non sono forniti rationale e alternative necessari per determinarne una rappresentazione ADR completa.

Source of Uncertainty: Project Brief incompleto rispetto alla struttura decisionale ADR.

Project Impact: influenza la completezza della Governance relativa alla persistenza.

Technical Impact: riguarda direttamente il modello di persistenza e future decisioni tecniche.

Proposed Resolution: stabilire se la decisione debba essere preservata tramite ADR e, in caso positivo, fornire il relativo rationale e le alternative considerate.

Alternatives:

mantenerla esclusivamente come Specification/vincolo architetturale;
creare successivamente un ADR con decision history confermata.

Recommendation: non inventare rationale o alternative; mantenere intanto il vincolo confermato come Specification.

Affected Governance Areas: Blueprint; Relational Persistence Specification; eventuale ADR.

Classification Reason: la scelta tecnica è confermata, ma le informazioni necessarie per rappresentarne correttamente la decision history sono irrisolte. L'incertezza deve quindi essere preservata invece di completare artificialmente un ADR.

Open Point — Governance Treatment of Client/Server Architecture

Problem: client/server è indicata come decisione architetturale già definita, ma il Project Brief non contiene rationale e alternative.

Source of Uncertainty: Project Brief.

Project Impact: influenza la documentazione permanente della direzione architetturale.

Technical Impact: influenza la struttura generale del sistema.

Proposed Resolution: stabilire se client/server debba essere rappresentata tramite ADR e acquisire l'eventuale decision history.

Alternatives:

mantenerla come direzione/vincolo architetturale confermato;
formalizzarla successivamente mediante ADR.

Recommendation: preservare la direzione nel Blueprint senza inventare una decision history.

Affected Governance Areas: Blueprint; eventuale ADR.

Classification Reason: non è in discussione il Fact che l'architettura sia client/server; è irrisolto come debba essere rappresentata la relativa decisione nella Governance permanente.

Open Point — Governance Treatment of REST Decision

Problem: REST è una modalità di comunicazione confermata e contemporaneamente indicata tra le decisioni architetturali già definite, ma manca la relativa decision history.

Source of Uncertainty: Project Brief.

Project Impact: influenza la completezza e traceability della Governance.

Technical Impact: riguarda il contratto di comunicazione frontend/backend.

Proposed Resolution: determinare se la scelta REST debba avere anche una rappresentazione ADR e, in caso positivo, acquisire rationale e alternative.

Alternatives:

rappresentarla esclusivamente come Specification;
rappresentarla anche tramite ADR dopo aver consolidato la decision history.

Recommendation: mantenere il vincolo REST come Specification fino alla risoluzione dell'Open Point.

Affected Governance Areas: REST Communication Specification; Blueprint; eventuale ADR.

Classification Reason: il vincolo REST è confermato, mentre la corretta rappresentazione della decisione e del suo rationale resta irrisolta e richiede intervento del Human Owner.

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
