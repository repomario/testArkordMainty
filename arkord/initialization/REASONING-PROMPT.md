# Arkord Engine Reasoning Prompt

## Project Input

- Project Name: Mainty test 2
- Project Description: Mainty test 2
- Repository Path: /home/genfree/WORK/Arkord/TEST/testArkordMainty/
- Methodology ID: arkord-hybrid-agile
- Phase ID: PHASE-1-1-PROJECT-INITIALIZATION

## Project Brief

```text
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

```

## Methodology / Phase Context

## Document: METHODOLOGY.md

```markdown
# Arkord Hybrid Agile Methodology

Arkord Hybrid Agile is the default methodology used by Arkord to guide projects from analysis to implementation. It provides the operational knowledge that helps projects move from intent, through structured understanding, toward reliable delivery.

Arkord Hybrid Agile belongs to `arkord-platform/methodologies`. It is separate from `arkord-platform/brain`, which contains platform-wide policies. The methodology contains knowledge specific to how Arkord Hybrid Agile organizes project work.

For V1, Arkord Hybrid Agile is the only available methodology. Future methodologies may be added later as the platform evolves.

Arkord Hybrid Agile guides the Reasoning Agent and the Execution Agent indirectly. Agents do not invent the process. Agents use the methodology defined by the platform methodology repository.

Arkord Hybrid Agile evolves incrementally together with Arkord. Only the parts stable enough to guide project work are defined. Undefined areas remain placeholders until they are specified in later increments.

## Methodology Structure

Arkord Hybrid Agile is organized as a layered methodology:

```text
Methodology
    ↓
Principles
    ↓
Phases
    ↓
Workflows
    ↓
Policies
    ↓
Prompts
    ↓
Artifacts
    ↓
Governance
    ↓
Templates
```

Each layer has a distinct responsibility:

- **Methodology** defines the overall purpose, scope, and structure of Arkord Hybrid Agile.
- **Principles** define the philosophy that every lower layer must remain consistent with.
- **Phases** divide the methodology into major areas of project progression.
- **Workflows** describe the ordered flow used within a phase or subphase.
- **Policies** define constraints and rules that govern specific methodology activity.
- **Prompts** provide agent-facing instructions for applying the methodology in a specific context.
- **Artifacts** are the durable outputs produced or maintained through methodology activity.
- **Governance** defines project governance document models managed in the Project Repository.
- **Concepts** define shared methodology concepts used across phases, workflows, artifacts, and governance.
- **Templates** define stable document structures for methodology artifacts and governance documents.

The layers should remain separate. Principles do not define workflow behavior, and workflows do not redefine methodology philosophy.

## Principles

The foundational principles of Arkord Hybrid Agile are defined in `principles/`:

- `ANALYSIS-BEFORE-IMPLEMENTATION.md`
- `KNOWLEDGE-BEFORE-DELIVERY.md`
- `REPOSITORY-AS-PERMANENT-MEMORY.md`
- `HUMAN-DRIVEN-DECISIONS.md`
- `AI-AS-ANALYST.md`
- `CONSOLIDATION-BEFORE-EXECUTION.md`
- `INCREMENTAL-EVOLUTION.md`
- `SEPARATION-OF-CONCERNS.md`

These documents are the philosophical foundation of the methodology. They are referenced here rather than duplicated so each principle remains focused and authoritative in its own document.

## Persistent Artifact Definitions

Persistent project artifact definitions are colocated under `artifacts/{TYPE}/`:

- `artifacts/BLUEPRINT/concept.md` and `artifacts/BLUEPRINT/template.md`
- `artifacts/ROADMAP/concept.md` and `artifacts/ROADMAP/template.md`
- `artifacts/FEATURE/concept.md` and `artifacts/FEATURE/template.md`
- `artifacts/SPECIFICATION/concept.md` and `artifacts/SPECIFICATION/template.md`
- `artifacts/ADR/concept.md` and `artifacts/ADR/template.md`
- `artifacts/OPEN-POINT/concept.md` and `artifacts/OPEN-POINT/template.md`
- `artifacts/BACKLOG/concept.md` and `artifacts/BACKLOG/template.md`
- `artifacts/EPIC/concept.md` and `artifacts/EPIC/template.md`

An artifact directory groups the authoritative meaning and persistent representation of one project artifact type while preserving their separate responsibilities. `concept.md` defines meaning, lifecycle, governance behavior, and materialization rules. `template.md` defines the persistent repository representation used when approved methodology knowledge is materialized.

## Concepts

`concepts/` remains available for methodology concepts that are not persistent project artifact types. It currently contains `concepts/FACTS.md`, because Facts are reasoning knowledge and do not have a persistent artifact Template.

## Workflow Contracts

Workflow contracts live under their owning workflow. The Phase 1.1 Initialization Plan definition is `workflow/PHASE-1-1-PROJECT-INITIALIZATION/contracts/initialization-plan.md`; it is the structured output contract of the Phase 1.1 Reasoning workflow, not a persistent project artifact.

## High-Level Phases

### Phase 1 — Functional Analysis

Phase 1 transforms project intent into governance and delivery structures before implementation.

Subphases:

- 1.1 Project Initialization from Project Brief
- 1.2 Story creation inside Epics
- 1.3 Task creation inside Stories

Only Phase 1.1 is defined now.

### Phase 2 — Development and Implementation

Phase 2 will cover the transition from approved analysis artifacts to repository changes.

Expected areas:

- implementation planning
- Codex handoff
- code changes
- review
- test
- repository update
- knowledge consolidation

Phase 2 is a placeholder and will be defined incrementally.

## Definition Status

Only Phase 1.1 is defined now. Other phases and subphases are placeholders and will be defined incrementally.

```

## Document: workflow/PHASE-1-1-PROJECT-INITIALIZATION/workflow.md

```markdown
# Phase 1.1 Workflow — Project Initialization

1. User creates new project.
2. User enters project properties.
3. User selects methodology: Arkord Hybrid Agile.
4. User inserts Project Brief.
5. Arkord receives the Project Brief.
6. Arkord asks clarifying questions when needed and records Human Owner confirmations.
7. Arkord consolidates the original Project Brief and confirmed clarifications into the Consolidated Project Brief.
8. Arkord analyzes the Consolidated Project Brief using Arkord Hybrid Agile rules.
9. Arkord records Facts, Inferences, Open Point Signals, and Risks; it never records Assumptions.
10. Arkord consolidates Project Understanding.
11. Arkord proposes Governance elements from the completed analysis, including Blueprint Outline, Roadmap Outline, Candidate Features, Candidate Specifications, Candidate ADRs, and Candidate Open Points according to the authoritative concept documents loaded by the Manifest.
12. Arkord includes a Classification Reason for every Candidate Feature, Candidate Specification, Candidate ADR, and Candidate Open Point.
13. Arkord assesses Analysis Confidence with justification.
14. Arkord produces an Initialization Plan.
15. User reviews and approves the Initialization Plan.
16. Arkord generates a Codex handoff prompt.
17. User sends the prompt to Codex.
18. Codex writes approved files into the repository under `projectRepository/arkord/` according to the approved Initialization Plan, Codex Handoff, templates, and authoritative concept documents.
19. User reviews Governance in Arkord. Delivery is generated later in Phase 1.2 from consolidated Governance.

```

## Document: phases/phase-1/PHASE-1-1-PROJECT-INITIALIZATION.md

```markdown
# Phase 1.1 — Project Initialization

## Purpose

Initialize a new Arkord project from a Project Brief.

## Input

- project name
- project description
- repository path
- selected methodology: Arkord Hybrid Agile
- Project Brief inserted by the user
- clarifications explicitly confirmed by the Human Owner during the clarification phase

## Behaviour

When a user creates a new project, Arkord asks for project properties and the Project Brief.

The interaction in this phase is a guided initialization and clarification process, not a free Reasoning Workspace. Its purpose is to collect, clarify, analyze, and structure the Project Brief.

The clarification phase produces a Consolidated Project Brief composed of the original Project Brief and every clarification explicitly confirmed by the Human Owner.

Arkord must analyze the Consolidated Project Brief and consolidate its understanding of the project before proposing Governance structure.

The Initialization Plan records this analysis as knowledge about the project. It is the authoritative analytical input for the Codex Handoff, but it does not describe which repository files Codex will create.

## Initialization Plan Content

The Initialization Plan must describe:

- Project Understanding
- Reasoning Results
  - Facts
  - Inferences
  - Open Point Signals
  - Risks
- Governance Proposal
  - Blueprint Outline
  - Roadmap Outline
  - Candidate Features
  - Candidate Specifications
  - Candidate ADRs
  - Candidate Open Points
- Analysis Confidence

The Reasoning Results and Governance Proposal must apply the authoritative definitions and criteria from the concept documents loaded by the Manifest: `concepts/FACTS.md`, `artifacts/FEATURE/concept.md`, `artifacts/SPECIFICATION/concept.md`, `artifacts/ADR/concept.md`, and `artifacts/OPEN-POINT/concept.md`.

Analysis Confidence is qualitative and must use only one of these levels: Very High, High, Medium, or Low. It must be followed by a mandatory Reason explaining why the analysis is considered reliable or uncertain.

## Governance Proposal

Governance is proposed only after Project Understanding and Reasoning Results have been consolidated.

Candidate governance elements must include:

- Blueprint outline
- Roadmap outline
- Candidate Features
- Candidate Specifications
- Candidate ADRs for decisions already confirmed or explicitly approved
- Candidate Open Points when the Open Point creation criteria are satisfied and unresolved issues must be preserved as governance knowledge

Candidate governance elements must be classified using the authoritative concept documents loaded by the Manifest. Every Candidate Feature, Candidate Specification, Candidate ADR, and Candidate Open Point must include a Classification Reason.

These elements are proposals in the Initialization Plan, not repository documents. Repository governance documents are produced later through the Codex Handoff and Codex implementation phase. The Initialization Plan itself does not create repository artifacts.

## Lifecycle Boundary

Phase 1.1 produces Governance only. It does not generate, propose, or materialize Delivery artifacts. Phase 1.2 derives Delivery later from consolidated Governance. Deferred Delivery is expected and must not be represented as an Open Point.

## Out of Scope

- methodology modification
- stories
- tasks
- bugs
- sprint
- code
- Technical Context implementation details

Do not modify project Methodology. In the new model, methodology belongs to Arkord Platform, not to the project.

## Output

- Initialization Plan as the consolidated analysis artifact
- Execution Handoff / Codex prompt for writing approved repository artifacts

## End Condition

Phase 1.1 is complete when the Initialization Plan has been approved, Codex has written the approved initial Governance documents into the project repository, and the user can review them in Governance. No Delivery artifact is required for completion.

```

## Document: policies/PHASE-1-1-POLICIES.md

```markdown
# Phase 1.1 Policies

- Project Initialization establishes Governance only. Never generate Delivery artifacts, Epics, Stories, Tasks, Bugs, implementation plans, or execution work in Phase 1.1.
- Delivery is derived later in Phase 1.2 from consolidated Governance.
- Never write code in Phase 1.1.
- Never modify methodology during Phase 1.1.
- Do not treat the project brief as project source of truth unless later explicitly persisted.
- Ask clarifying questions when the Project Brief is incomplete.
- Treat explicitly confirmed clarifications from the Human Owner as part of the Consolidated Project Brief.
- Analyze the Consolidated Project Brief, not only the original Project Brief.
- Produce an Initialization Plan before generating a Codex handoff.
- The Initialization Plan must describe Arkord's understanding of the project, not the repository files Codex will create.
- Treat Open Point Signals according to the authoritative Open Points governance model loaded by the Manifest.
- Do not invent Facts to eliminate uncertainty, never generate Assumptions, and classify reasoning results using the authoritative concept documents loaded by the Manifest.
- Do not generate a Codex handoff without user approval.
- Governance output in Phase 1.1 begins as a Governance Proposal in the Initialization Plan.
- Candidate governance elements must include Blueprint Outline, Roadmap Outline, Candidate Features, Candidate Specifications, Candidate ADRs, and Candidate Open Points when applicable.

- Classify Candidate Features, Candidate Specifications, Candidate ADRs, and Candidate Open Points using the authoritative concept documents loaded by the Manifest.
- Require a Classification Reason for every Candidate Feature, Candidate Specification, Candidate ADR, and Candidate Open Point.
- Do not assign repository identifiers, file names, or file paths during reasoning.

```

## Document: concepts/FACTS.md

```markdown
# Facts

Facts are confirmed project knowledge in Arkord Hybrid Agile.

## Official Definition

A Fact is information that has been explicitly confirmed and can be considered true for the current project.

The defining characteristic of a Fact is confirmation, not where the information originated. Once confirmed, a Fact is valid project knowledge regardless of whether it came from the original Project Brief, a clarification by the Human Owner, or an approved governance decision.

## Fact Sources

Every Fact has a Source.

Arkord Hybrid Agile initially defines the following Fact Sources:

| Source | Definition |
| --- | --- |
| `PROJECT_BRIEF` | Information explicitly present in the original Project Brief. |
| `CLARIFICATION` | Information explicitly confirmed by the Human Owner during the clarification phase. |
| `APPROVED_DECISION` | Information that became true because it was formally approved as a project decision, for example through an approved ADR or another approved governance decision. |

All three Fact Sources are equally valid once confirmed. A Fact from a clarification is not less reliable than a Fact from the original Project Brief, and a Fact from an approved decision is not less reliable than either of them.

## Use of Facts

Facts:

- are considered reliable project knowledge;
- may be freely used during reasoning;
- do not require further confirmation;
- do not generate Open Points;
- are not Inferences.

A Fact may support an Inference, reduce uncertainty, or remove the need for an Open Point. The Fact itself remains confirmed knowledge and must not be reclassified as an Inference or Open Point.

## What Is Not a Fact

The following are not Facts:

- deductions;
- hypotheses;
- proposed solutions;
- possible future decisions;
- unresolved governance decisions;
- uncertain information.

These belong to other analytical or governance concepts and must not be classified as Facts. If the information is uncertain, it may require an Open Point. If it is a logical conclusion derived from other information, it is an Inference. If it is a potential future problem, it is a Risk. If it is a decision that has not yet been approved, it is not a Fact.

## Relationship with the Consolidated Project Brief

The clarification phase produces a Consolidated Project Brief.

The Consolidated Project Brief consists of:

- the original Project Brief;
- clarification answers explicitly confirmed by the Human Owner.

Confirmed clarifications become Facts directly. No intermediate analytical state exists between Human Owner confirmation and Fact classification.

The Reasoning Agent performs analysis using the Consolidated Project Brief rather than only the original Project Brief.

Facts may therefore originate from either the original Project Brief or confirmed clarifications. Facts may also originate from approved governance decisions when those decisions formally establish project truth.

```

## Document: artifacts/BLUEPRINT/concept.md

```markdown
# Blueprint Concept

Blueprint is the persistent high-level description of the project. It records the approved project identity, purpose, goals, scope, exclusions, target users or stakeholders, major capabilities, principal constraints, and architectural direction when that direction has already been approved.

Blueprint belongs to Governance. It helps readers understand what the project is and why it exists before reading detailed Features, Specifications, ADRs, Open Points, Roadmap entries, or Delivery work items.

## Creation Criteria

Create the Blueprint during Phase 1.1 when the Project Brief or approved Human Owner clarifications provide enough stable information to describe the project at a high level.

The current runtime supports one Blueprint document per project.

## Update Criteria

Update the Blueprint when approved project-level identity, purpose, goals, scope, exclusions, stakeholders, major capabilities, constraints, or approved architectural direction changes.

Preserve the existing Blueprint identifier when updating an existing Blueprint.

## Exclusions

A Blueprint must not become:

- a detailed Specification;
- a list of implementation tasks;
- a Delivery backlog;
- a history of individual decisions;
- a duplicate of every Feature, ADR, Specification, or Open Point.

## Lifecycle

Blueprint has no approval lifecycle. Delivery Readiness depends only on the Human Owner review state: `UNREAD` blocks readiness and `READ` is ready. The review state is Platform metadata, not repository frontmatter.

## Canonical Repository Location

The canonical repository path is:

```text
arkord/governance/BLUEPRINT.md
```

## Relationships

The Blueprint may use supported Project Context Graph relation fields to reference approved related Governance or Delivery nodes when explicitly present in the approved materialization payload. The current authoritative template uses `relations.relatedTo` as the stable general-purpose relation field.

Do not invent unsupported relation names or infer relationships from conceptual similarity.

## Materialization Expectations

Codex materializes the approved Blueprint Outline by creating or updating exactly one Blueprint document at the canonical path using `artifacts/BLUEPRINT/template.md`.

Codex must materialize only approved information, preserve the existing `nodeId` when the file already exists, and avoid duplicating full content from Roadmap, Feature, ADR, Specification, Open Point, Backlog, or Epic artifacts.

```

## Document: artifacts/ROADMAP/concept.md

```markdown
# Roadmap Concept

Roadmap is the persistent high-level evolution plan of the project. It records approved sequencing intent, major milestones or evolution areas, dependencies, constraints, and known open questions at a planning level.

Roadmap belongs to Governance. It explains how the project is expected to evolve, while Delivery artifacts represent executable work containers and work items.

## Creation Criteria

Create the Roadmap during Phase 1.1 when the approved initialization material contains a Roadmap Outline or comparable high-level evolution plan.

The current runtime supports one Roadmap document per project.

## Distinction from Delivery

Roadmap is not a Delivery work-item format. It must remain high-level and must not contain Stories, Tasks, Bugs, Sprint assignments, estimates, assignees, implementation details, or unapproved speculative scope.

Epics may be derived from approved Governance and can be traceable to Roadmap intent, but the Roadmap itself is not a Backlog and does not manage delivery execution.

## Relationships

Roadmap relates to Blueprint as the high-level evolution plan for the project described by the Blueprint. It may reference Features, Open Points, Epics, or other approved nodes only through supported Project Context Graph relation fields and only when explicitly approved. The current authoritative template uses `relations.relatedTo` for general traceability.

## Lifecycle

Roadmap has no approval lifecycle. Delivery Readiness depends only on the Human Owner review state: `UNREAD` blocks readiness and `READ` is ready. The review state is Platform metadata, not repository frontmatter.

## Canonical Repository Location

The canonical repository path is:

```text
arkord/governance/ROADMAP.md
```

## Materialization Expectations

Codex materializes the approved Roadmap Outline by creating or updating exactly one Roadmap document at the canonical path using `artifacts/ROADMAP/template.md`.

Codex must preserve the existing `nodeId` when the file already exists, materialize only approved roadmap content, and avoid inventing increments, dates, implementation details, or future scope.

```

## Document: artifacts/FEATURE/concept.md

```markdown
# Features

A Feature is a stable functional capability provided by the system.

A Feature represents something that the system must implement. Features are permanent governance artifacts and constitute the primary source from which Delivery work items are derived.

Features describe what the system does, not how it is implemented.

## Repository Location

Features are stored as one document per Feature under:

```text
projectRepository/arkord/governance/features/
```

Features must follow the standard methodology template defined in `artifacts/FEATURE/template.md`. The template provides the stable document structure used for human review, deterministic parsing, future Arkord UI editing, and Context Graph relationship tracking.

Features belong to Governance. They are not Delivery work items.

## Lifecycle

The official Feature review lifecycle is `PROPOSED`, `APPROVED`, and `REJECTED`. In every state the repository file remains current Governance knowledge. `PROPOSED` awaits Human Owner confirmation, participates in reasoning, and blocks Delivery Readiness; `APPROVED` is confirmed acceptable and may feed future Delivery derivation; `REJECTED` remains relevant reasoning context but is excluded from Delivery and blocks readiness. Approval normally changes validation state without rewriting content. Phase 1.1 and manual creation materialize `PROPOSED`; only a Human Owner may approve or reject it after reading. Legacy values remain readable but are not active transitions.

## Characteristics

A Feature:

- represents a stable functional capability;
- is part of the permanent project knowledge;
- originates from the Consolidated Project Brief through reasoning;
- may evolve over time;
- may be governed by one or more Specifications;
- may be related to ADRs;
- may be impacted by Open Points.

Features are not implementation tasks. Feature documents must not include Delivery planning fields such as Priority, Sprint, Assignee, Estimate, or Due Date, and must not include Implementation Details.

## Relationship with Specifications

Specifications describe constraints. Features describe capabilities.

A Specification may govern one or more Features:

```text
Specification
    ↓
governs
    ↓
Feature
```

A Feature may be governed by one or more Specifications:

```text
Feature
    ↓
governedBy
    ↓
Specification
```

This relationship is many-to-many:

- one Specification may govern multiple Features;
- one Feature may be governed by multiple Specifications.

## Relationship with Delivery

Future Delivery is generated only from relevant `APPROVED` Features. `PROPOSED` and `REJECTED` Features are not eligible Delivery inputs. Feature documents may reference generated Delivery work items for traceability only; these references do not transform Features into Delivery artifacts.

The normal progression is:

```text
Feature
    ↓
Epic
    ↓
User Story
    ↓
Task
```

Small Features may generate Tasks directly without requiring an intermediate Epic or User Story:

```text
Feature
    ↓
Task
```

This simplified path is valid when the Feature is small enough that intermediate Delivery work items would not add useful planning or governance value.

## Governance and Delivery Separation

Features belong to Governance.

Epics, User Stories, and Tasks belong to Delivery.

Governance defines what the project is. Delivery defines how the project is implemented.

Delivery must derive from Governance rather than directly from the Project Brief.

```

## Document: artifacts/SPECIFICATION/concept.md

```markdown
# Specifications

A Specification is a stable and enforceable rule, constraint, standard, model, or contract that governs one or more parts of the project.

Specifications define what the project must comply with. They do not describe functional capabilities.

Specifications describe conditions that must remain valid independently of the implementation. A Specification may constrain design choices, define a model, establish a contract, or state a quality, security, compliance, architectural, operational, or process rule that Features and project work must respect.

## Repository Location

Specifications are stored as one document per Specification under the canonical repository path:

```text
arkord/governance/specifications/{SPECIFICATION-ID}.md
```

`{SPECIFICATION-ID}` must be a unique and stable repository identifier. When an existing Specification is updated, its existing identifier and path must be preserved.

Specifications are Governance artifacts. They are not Delivery artifacts, implementation tasks, Stories, or backlog items.


## Creation Criteria

Create a Specification when project knowledge defines a stable and enforceable:

- rule;
- constraint;
- standard;
- model;
- contract;
- quality requirement;
- security requirement;
- architectural constraint;
- operational rule;
- process rule.

Do not create a Specification when the information primarily represents:

- a functional capability, which belongs to a Feature;
- a proposed or reviewed decision and its rationale, which belongs to an ADR (only an `APPROVED` ADR is an accepted decision);
- unresolved uncertainty, which belongs to an Open Point;
- implementation work, which belongs to Delivery;
- a local or reversible coding choice that does not require permanent governance.

A Specification should be created only when the rule or constraint is expected to remain part of project governance and must be enforced across one or more project areas.

## Lifecycle

The official Specification review lifecycle is `PROPOSED`, `APPROVED`, and `REJECTED`. All three remain current repository Governance knowledge. `PROPOSED` participates in reasoning while awaiting confirmation and blocks readiness; `APPROVED` is confirmed and may feed future Delivery derivation; `REJECTED` may inform relevant reasoning but is excluded from Delivery and blocks readiness. Approval normally changes Human Owner validation without requiring a content rewrite. Phase 1.1 and manual creation materialize `PROPOSED`; only a Human Owner may approve or reject it after reading. Legacy values remain readable but are not active transitions.

## Materialization Expectations

Specifications are materialized by Codex only after human approval of Candidate Specifications in the Initialization Plan. Codex must create exactly one Specification document for each approved Candidate Specification, using the authoritative Specification Template at `artifacts/SPECIFICATION/template.md`.

Materialization must preserve the approved rule or constraint, scope, governed Features, rationale, related decisions, and resolved Open Points without inventing additional rules, constraints, categories, lifecycle states, or relationships. Generated documents must use Project Context Graph YAML frontmatter with `nodeType: SPECIFICATION`, status `PROPOSED`, supported relation fields, and the canonical repository path.

## Distinction from Features

Features and Specifications describe different kinds of project knowledge:

- A **Feature** describes what the system must be capable of doing.
- A **Specification** describes the rules and constraints that govern those capabilities.

Features define functional capability. Specifications define required compliance conditions.

Examples:

| Project Concept | Classification | Reason |
| --- | --- | --- |
| Task Management | Feature | It describes a system capability: managing tasks. |
| Task Filtering | Feature | It describes a system capability: filtering tasks. |
| Responsive UI | Specification | It describes a quality constraint that user-facing capabilities must comply with across supported devices. |
| Relational Persistence Model | Specification | It describes a stable data model constraint governing how persistent data is structured. |

A functional capability must be modeled as a Feature. A stable rule, constraint, standard, model, or contract that governs that capability must be modeled as a Specification.

## Conceptual Categories

Specification categories are descriptive rather than prescriptive. Arkord Hybrid Agile does not require a mandatory enum for Specification categories.

Common conceptual categories include:

- **Functional Rule**: a business or domain rule that governs behavior across one or more Features.
- **Data Model**: a stable model, schema, structure, or persistence constraint.
- **Interface Contract**: an API, event, file, integration, or UI contract that project elements must comply with.
- **Quality Constraint**: a usability, accessibility, performance, reliability, maintainability, or compatibility constraint.
- **Security Constraint**: an authentication, authorization, data protection, threat mitigation, or secure handling rule.
- **Compliance Rule**: a legal, regulatory, licensing, audit, or organizational compliance requirement.
- **Architectural Constraint**: a technology, layering, dependency, modularity, deployment, or integration constraint.
- **Operational Standard**: an observability, supportability, backup, monitoring, release, or runtime operations standard.
- **Process Rule**: a governance, review, approval, documentation, or lifecycle process rule.

These categories help humans and tools reason about Specifications, but they do not limit the valid forms a Specification may take.

## Relationship with Features

A Specification governs one or more Features:

```text
Specification
    ↓
governs
    ↓
Feature
```

The inverse relationship is:

```text
Feature
    ↓
governedBy
    ↓
Specification
```

This relationship is many-to-many:

- one Specification may govern multiple Features;
- one Feature may be governed by multiple Specifications.

## Relationship with Open Points

A Specification may resolve one or more Open Points:

```text
Specification
    ↓
resolves
    ↓
Open Point
```

The inverse relationship is:

```text
Open Point
    ↓
resolvedBy
    ↓
Specification
```

When a Specification contributes to an Open Point resolution, both artifacts must preserve bidirectional traceability. Creating, approving, or applying the Specification does not automatically change the Open Point to `RESOLVED`; that later transition records the Human Owner's judgment that current Governance adequately addresses the issue.

## Relationship with ADRs

An ADR may support one or more Specifications:

```text
ADR
    ↓
supports
    ↓
Specification
```

The inverse relationship is:

```text
Specification
    ↓
supportedBy
    ↓
ADR
```

An ADR records why a decision was made. A Specification records the resulting stable rule when a decision establishes one.

An ADR does not necessarily produce a Specification. A Specification may be supported by one or more ADRs.

```

## Document: artifacts/ADR/concept.md

```markdown
# ADRs

Within Arkord Hybrid Agile, the historical acronym ADR is retained, but it represents a persistent governance record of a project decision under review or already reviewed rather than only an architectural decision.

An ADR is a persistent governance artifact that records a proposed or reviewed project decision, the context in which it arose, the alternatives considered, and the rationale for the proposed direction. Only an ADR with status **APPROVED** records an accepted project decision.

ADRs are not limited to architecture. They may represent:

- architectural decisions;
- technical decisions;
- governance decisions;
- methodological decisions;
- process decisions;
- organizational decisions;
- any other proposed or reviewed project decision whose rationale must remain permanently traceable.

## Purpose

An ADR exists to preserve decisions that must remain visible and traceable throughout the lifecycle of the project.

If forgetting a decision could lead to inconsistent future reasoning or implementation, that decision should be recorded as an ADR.

An ADR does not merely document what was decided. It also preserves:

- why the decision was made;
- which alternatives were considered;
- what consequences the decision has;
- how the decision affects permanent project knowledge.

## Repository Location

ADRs are stored as one document per decision under:

```text
arkord/governance/decisions/{ADR-ID}.md
```

ADR identifiers must be unique and stable. When an existing ADR is updated, its identifier, path, lifecycle history, and relationships must be preserved.

ADRs belong to Governance. They are not Delivery work items, implementation tasks, or transient reasoning notes.

ADRs must follow the authoritative persistent document structure defined in `artifacts/ADR/template.md`. The Concept defines meaning and governance behavior; the Template defines document layout, graph frontmatter, and stable body sections.

## Creation Criteria

Create an ADR when all of the following are true:

- a concrete project decision has been proposed or confirmed for Human Owner review;
- the decision has consequences that may influence future reasoning, governance, or implementation;
- the rationale and considered alternatives must remain traceable;
- forgetting the decision could cause future inconsistency.

Valid ADR topics include architecture, technology, governance, process, methodology, organization, project direction, and any other proposed or reviewed decision with durable project impact.

Do not create an ADR when the information primarily represents:

- a functional capability, which belongs to a Feature;
- a stable rule or constraint without the decision history, which belongs to a Specification;
- unresolved uncertainty, which belongs to an Open Point;
- an unresolved recommendation that is not yet concrete enough for Human Owner decision review;
- implementation work, which belongs to Delivery;
- a local and reversible coding choice that does not require durable governance.

## What ADRs Are Not

An ADR records a proposed or reviewed decision. Its lifecycle status distinguishes a proposal awaiting review from an accepted or rejected decision; only an **APPROVED** ADR is an accepted project decision.

ADRs do not describe:

- functional capabilities, which are modeled as Features;
- stable project rules or constraints without decision history, which are modeled as Specifications;
- unresolved decisions or unresolved uncertainty, which are modeled as Open Points;
- unresolved recommendations that are not yet concrete enough for Human Owner decision review;
- implementation tasks or execution work, which belong to Delivery;
- local and reversible coding choices that do not require durable governance.

A decision represented by an ADR may influence Features or relate to Specifications while it is under review. Only after the ADR is **APPROVED** may it act as the accepted decision that supports Specifications or resolves Open Points; the artifact and its reasoning remain visible when **PROPOSED** or **REJECTED**.

## Valid Origins

An ADR may originate from:

- the Consolidated Project Brief;
- clarification answers;
- the resolution of an Open Point;
- a concrete proposed or confirmed decision emerging during reasoning;
- any other project decision ready for Human Owner review.

The defining condition is that a concrete decision is ready for Human Owner review or has already been reviewed. It may be materialized as a **PROPOSED** ADR before Governance approval. An **APPROVED** ADR represents the accepted decision; a **REJECTED** ADR remains a visible governance artifact recording that the Human Owner rejected the proposal. Unresolved uncertainty or a recommendation that is not ready for decision review remains an Open Point rather than an ADR.

## Relationships

ADRs preserve bidirectional traceability with the project knowledge they resolve, support, impact, or supersede.

### Relationship with Open Points

An ADR may resolve one or more Open Points:

```text
ADR
    ↓
resolves
    ↓
Open Point
```

The inverse relationship is:

```text
Open Point
    ↓
resolvedBy
    ↓
ADR
```

An Open Point represents unresolved uncertainty or an unresolved decision. An ADR may reference it while review is pending, and only an **APPROVED** ADR records an accepted decision. Applying or approving that ADR does not itself transition the Open Point: the Open Point remains **OPEN** until the Human Owner determines that current Governance adequately addresses the original problem. A rejected ADR does not resolve the Open Point; its rejection reason remains relevant follow-up context.

### Relationship with Specifications

An ADR may support one or more Specifications:

```text
ADR
    ↓
supports
    ↓
Specification
```

The inverse relationship is:

```text
Specification
    ↓
supportedBy
    ↓
ADR
```

A Specification records the stable rule, constraint, standard, model, or contract. An ADR records the proposed or reviewed decision and its rationale; only an **APPROVED** ADR supplies an accepted decision that justifies or explains that Specification.

### Relationship with Features

An ADR may impact one or more Features:

```text
ADR
    ↓
impacts
    ↓
Feature
```

The inverse relationship is:

```text
Feature
    ↓
impactedBy
    ↓
ADR
```

A Feature describes a functional capability. An ADR may explain a proposed or reviewed decision that affects the scope, direction, constraints, prioritization, or interpretation of that Feature. Only an **APPROVED** ADR makes that decision accepted and active.

### ADR Succession

An ADR may supersede one or more earlier ADRs:

```text
ADR
    ↓
supersedes
    ↓
ADR
```

The inverse relationship is:

```text
ADR
    ↓
supersededBy
    ↓
ADR
```

Supersession preserves historical traceability. A superseded ADR remains part of the project record, but only when the newer ADR is **APPROVED** does it become the current decision authority for the topic it supersedes.

## Lifecycle States

ADRs use only **PROPOSED**, **APPROVED**, and **REJECTED** for active Human Owner review. Every state remains current repository Governance knowledge. PROPOSED participates in reasoning, awaits confirmation, and blocks readiness; APPROVED records Human Owner acceptance and may feed future Delivery derivation; REJECTED preserves the unacceptable proposal and its context for relevant reasoning, is excluded from Delivery, and blocks readiness. Approval normally changes validation state without rewriting content. A newly materialized ADR is PROPOSED. After it is READ, the Human Owner may approve or reject it; rejection requires a reason and creates an OPEN Open Point. Legacy statuses remain readable without being reinterpreted.

## Materialization Expectations

During Phase 1.1, Candidate ADRs must represent concrete decisions grounded in the Project Brief or Human Owner clarifications and selected in the Initialization Plan for review. After approval of the Initialization Plan, Codex materializes exactly one ADR document for each Candidate ADR authorized by that plan using `artifacts/ADR/template.md` and status **PROPOSED**. Initialization Plan approval authorizes artifact materialization; it does not accept the represented decision.

Codex must not create additional ADRs beyond the Candidate ADRs authorized by the approved Initialization Plan, must not convert unresolved Candidate Open Point recommendations into ADRs automatically, and must not invent decisions, alternatives, consequences, or relationships absent from the approved plan.

ADR documents use the Project Context Graph runtime node type `DECISION` and the canonical path `arkord/governance/decisions/{ADR-ID}.md`. Relationships must use the relation fields supported by the repository and must be created only from source information authorized by the approved Initialization Plan. When bidirectional traceability is required, both related artifacts must be updated.

```

## Document: artifacts/OPEN-POINT/concept.md

```markdown
# Open Points

Open Points are persistent governance artifacts in Arkord Hybrid Agile.

An Open Point is a project ambiguity, contradiction, missing decision, or unresolved Governance problem requiring reasoning before Governance can be considered sufficiently mature.

An Open Point exists to preserve unresolved knowledge that is relevant to the evolution of the project. It is not a generic record of every missing technical detail. It is created only when the uncertainty is project-relevant and should remain visible until a Human Owner closes it or resolves it through governance.

Open Points originate during reasoning when Arkord identifies uncertainty that must not be hidden, ignored, or solved by inventing information, and that satisfies the deterministic creation criteria below. During Project Initialization, this uncertainty is first identified in Reasoning Results and, when it should be preserved as governance knowledge, proposed in the Initialization Plan Governance Proposal as a Candidate Open Point. After approval and consolidation, Candidate Open Points are written into the Project Repository as Open Point governance documents.

Open Points belong to Project Repository governance knowledge. They are not Platform Brain policies, not methodology rules, and not temporary chat notes.

## Resolution Conversation

Each logical Open Point is stored as exactly two files: `arkord/governance/open-points/<nodeId>/open-point.md` contains its authoritative Governance item and state, while `conversation.md` contains only its durable Resolution Conversation. The transcript retains Human Owner preferences, rejected approaches, rationale, discovered constraints, and evolving understanding in the Project Repository rather than a database/session. It has no revision or separate Context Graph identity. If both a legacy `<nodeId>.md` and the directory representation exist, the directory representation wins discovery; legacy files are safely split on first workflow access.

Messages are append-only and ordered under `### Human Owner` or `### Arkord` headings. After every Human Owner turn, the Reasoning Agent returns a natural response plus exactly `NEEDS_MORE_REASONING` or `READY_FOR_GOVERNANCE`. It dynamically rereads the current Open Point, bounded Context Graph, and persistent history without duplicating conversation in Current Open Point context. READY means only that the solution is concrete and coherent enough for Governance changes; it is reversible, and conversation continues indefinitely.

Only READY automatically stores/replaces the separate seven-field Resolution Proposal. NEEDS removes any prior proposal from the actionable flow. **View Resolution** is read-only. Only explicit, confirmed **Apply to Governance**, with application validation of current READY and proposal state, generates the existing forward-only Governance Mutation Handoff. Conversation text never authorizes mutation. No direct Governance mutation, Delivery, lifecycle change, automatic resolution, rollback, or version restoration occurs; the Open Point remains `OPEN`.

## Creation Criteria

An Open Point should be created only when all of the following conditions are true:

- the information is not already a Fact;
- the uncertainty cannot be resolved through a reliable Inference;
- the issue requires a human clarification or decision;
- the unresolved issue has a meaningful impact on the project.

If one of these conditions is not satisfied, an Open Point should not be created.

The primary decision rule is:

> If leaving the uncertainty unresolved may cause future reasoning, governance or implementation to diverge, it should become an Open Point.

This rule is the main criterion used by the Reasoning Agent when deciding whether an uncertainty deserves persistent governance treatment.

## Impact Dimensions

Every Open Point must evaluate two independent impact dimensions. The dimensions must be considered separately, even when one of them has no meaningful effect.

### Project Impact

Project Impact describes how the unresolved decision may affect project scope, functional behaviour, governance, roadmap, Features, Specifications, Delivery planning, or stakeholder expectations.

### Technical Impact

Technical Impact describes how the unresolved decision may affect architecture, technology stack, database design, deployment, integrations, API contracts, security, or other long-term technical decisions.

An Open Point may have Project Impact only, Technical Impact only, or both. The absence of one impact dimension does not remove the need for an Open Point when the other dimension is meaningful.

## Exclusions

The following should normally not generate Open Points:

- confirmed Facts;
- reliable Inferences;
- reversible implementation details;
- local coding choices;
- implementation preferences;
- information explicitly declared out of scope;
- decisions that can safely be postponed without affecting project governance.

## Minimum Analytical Content

Every Candidate Open Point should contain at least:

- Problem;
- Source of Uncertainty;
- Project Impact;
- Technical Impact;
- Proposed Resolution;
- Alternatives;
- Recommendation;
- Affected Areas;
- Classification Reason.

These fields represent the minimum information required for the Human Owner to make an informed decision. They define the analytical content of a candidate, while `artifacts/OPEN-POINT/template.md` remains the authoritative document structure for persisted Open Point files.

## Repository Location

Consolidated Open Points are stored in the Project Repository under:

```text
projectRepository/arkord/governance/open-points/
```

Each Open Point is stored as one file per Open Point.

Each Open Point must follow the standard structure defined by `artifacts/OPEN-POINT/template.md`. The template is the authoritative document structure and must not be duplicated in governance guidance.

Each Open Point must be managed as a first-class Governance reasoning document, similarly to ADRs and Specifications. It transforms uncertainty into useful Governance knowledge; it is not Delivery scope and must never directly generate Delivery work.

## Standard Template

The Open Point template defines the stable logical fields used by Open Point governance documents, including standard YAML frontmatter, Problem, Source of Uncertainty, Project Impact, Technical Impact, Proposed Resolution, Alternatives, Recommendation, Affected Areas, and Resolution.

The template is field-oriented rather than free-form Markdown so future Engine parsing and Arkord UI editing can rely on a stable structure.

Open Points must not include delivery ownership or scheduling fields such as Priority, Owner, Assignee, Sprint, or Due Date. Open Points belong to Governance, not Delivery.

## Lifecycle

Open Points use **OPEN**, **CLOSED**, and **RESOLVED**:

- **OPEN** means the issue still requires attention. It may already have reasoning history, attempted resolutions, or Governance modifications and remain open.
- **CLOSED** means the issue no longer requires action without claiming a successful Governance resolution.
- **RESOLVED** means the Human Owner considers the original problem successfully addressed by current Governance.

The structured `Resolved By` references record contributing Governance, not an automatic lifecycle trigger. Applying a future approved resolution proposal and mutating Governance leaves the Open Point **OPEN** while affected Governance enters Human review. Only the Human Owner's later assessment transitions it to **RESOLVED**. Normal Governance Review does not expose a generic resolution transition; the future resolution workflow is outside the current implementation.

## Resolution and mutation contract

A future resolution may create or materially modify Governance. Created or modified Features, Specifications, and ADRs become `PROPOSED` and `UNREAD`, including formerly approved artifacts; modified Core Documents become `UNREAD` and have no lifecycle. Unmodified documents retain their lifecycle and review states. The originating Open Point remains `OPEN` until the Human Owner is satisfied with the resulting Governance.

If an affected artifact is later rejected, its rejection reason is additional reasoning context for the same Open Point, which remains `OPEN`. Governance mutations are forward-only: Arkord applies a later corrective mutation rather than automatically rolling back prior changes.

## Relationship with ADRs and Specifications

Open Points have bidirectional traceability relationships with the governance artifacts that resolve them:

```text
Open Point resolved by -> one or more ADRs / Specifications
ADR resolves -> one or more Open Points
Specification resolves -> one or more Open Points
```

Open Point resolution relationships are not strictly one-to-one. The valid relationship model is:

- one Open Point may be resolved by multiple Specifications;
- one Specification may resolve multiple Open Points;
- one Open Point may be resolved by multiple ADRs;
- one ADR may resolve multiple Open Points.

Whenever an ADR or Specification contributes to resolving an Open Point, both sides must contain the relationship. If the Open Point references that ADR or Specification, the corresponding artifact must reference the Open Point back. These links preserve traceability but do not automatically transition lifecycle status.

This bidirectional traceability is mandatory and preserves the connection between unresolved analysis issues and final governance decisions or specifications. Lifecycle changes must preserve bidirectional traceability, and both sides of each relationship must remain synchronized.

For an ADR resolution:

```text
Open Point
↓
Resolved By → ADR-004

ADR-004
↓
Resolves → OPEN-002
```

For a Specification resolution:

```text
Open Point
↓
Resolved By → SPEC-003

SPEC-003
↓
Resolves → OPEN-005
```

If an ADR or Specification is created as a resolution of an Open Point, it must explicitly reference the Open Point that caused it. This originating Open Point reference is required even if the Open Point is later resolved, later excluded from active operational context, or the resolving artifact evolves over time. The reference preserves decision traceability across the lifetime of the project.

## CLOSED Open Points and Operational Context

**CLOSED** does not mean resolved. A Closed Open Point remains unresolved, but it no longer needs to be solved. It is retained in the repository for historical traceability.

A Closed Open Point must no longer be considered part of the active operational context and should not influence future reasoning unless it is explicitly requested. Excluding a Closed Open Point from active operational context does not remove it from the repository and does not remove required traceability from any ADR or Specification that was derived from it.

## Resolution Review

After an applied resolution, the current `Resolution Review` records only each affected Governance node ID, `APPROVED` or `REJECTED`, and the Human Owner reason for rejection. `updatedBy` routes these outcomes to this still-`OPEN` Open Point without starting a new conversation or invoking AI. Arkord Engine exclusively owns this section; the Execution Agent never creates or changes it. Approval adds no chat noise. Rejection appends a deterministic `Arkord` workflow-event message to the existing Resolution Conversation, changes readiness to NEEDS, and removes the stale actionable Proposal. That Engine invalidation is not semantic reasoning; the Reasoning Agent evaluates the next Human Owner turn independently. A new Apply replaces this current-cycle set and proceeds from current Governance; it is not history or rollback.

## Human Owner closure

Closure Readiness is not lifecycle and is not Reasoning Readiness. It is derived from the current Apply review cycle: all affected lifecycle artifacts must be `APPROVED`, and every affected Core Document current revision must be reviewed. Any proposed, rejected, unread, unknown, or missing item blocks closure. The Human Owner alone may then explicitly transition `OPEN` to `RESOLVED`; readiness never closes automatically. Resolution preserves history, makes reasoning read-only, and has no reopen or `resolves` relationship workflow.

```

## Document: workflow/PHASE-1-1-PROJECT-INITIALIZATION/contracts/initialization-plan.md

```markdown
# Initialization Plan

The Initialization Plan is the structured output contract of the Phase 1.1 Reasoning workflow. It is not a persistent project artifact and is not written to the project repository by default.

The Initialization Plan is the consolidated workflow contract for Project Initialization analysis. It records the required sections, fields, and output structure that the Reasoning Agent must produce before repository Governance files are proposed.

The Initialization Plan is the authoritative analytical input for the Codex Handoff. The Codex Handoff decides which repository files to create or update; the Initialization Plan describes the knowledge that justifies those later repository changes.

## Required Structure

An Initialization Plan must contain the following sections in order.

## 1. Project Understanding

This section must include the consolidated project understanding supported by the Consolidated Project Brief or justified analysis.

Required fields, when applicable:

- Project purpose
- Business goals
- Target users
- Functional scope
- Non-functional expectations
- Constraints
- Known risks

## 2. Reasoning Results

This section must contain only these subsections:

- Facts
- Inferences
- Open Point Signals
- Risks

The content of each subsection must follow the authoritative methodology concept documents loaded by the Phase 1.1 Manifest.

Reasoning Results must not contain Assumptions.

## 3. Governance Proposal

This section must contain candidate governance elements resulting from the completed analysis. It must explicitly contain these subsections, in this order:

- Blueprint Outline
- Roadmap Outline
- Candidate Features
- Candidate Specifications
- Candidate ADRs
- Candidate Open Points

Candidate governance elements are proposals, not repository documents. The Reasoning Agent must not generate repository identifiers, file names, or repository paths for any governance candidate. The Codex Handoff may later transform approved proposals into repository artifacts.

Each Candidate Feature, Candidate Specification, Candidate ADR, and Candidate Open Point must include a concise Classification Reason based on the authoritative concept documents loaded by the Phase 1.1 Manifest.

### Candidate Feature Fields

Every Candidate Feature must include at least:

- Title
- Summary
- Purpose
- Functional Scope
- Out of Scope, when relevant
- Functional Rules
- Related Governance
- Expected Delivery Derivation
- Classification Reason

### Candidate Specification Fields

Every Candidate Specification must include at least:

- Title
- Rule or Constraint
- Scope
- Governed Features
- Rationale
- Related Decisions
- Classification Reason

### Candidate ADR Fields

Every Candidate ADR must include at least:

- Title
- Decision
- Context
- Rationale
- Alternatives
- Consequences
- Affected Features or Specifications
- Resolved Open Points, when applicable
- Classification Reason

### Candidate Open Point Fields

Every Candidate Open Point must include at least:

- Problem
- Source of Uncertainty
- Project Impact
- Technical Impact
- Proposed Resolution
- Alternatives
- Recommendation
- Affected Governance Areas
- Classification Reason

The Initialization Plan contract itself does not create repository artifacts. Project Initialization establishes Governance only; it must not propose Delivery artifacts, Epics, Stories, Tasks, implementation plans, or execution work. Delivery is derived later in Phase 1.2 from consolidated Governance.

## 4. Explicitly Out of Scope

This section must list relevant exclusions identified during analysis or required by Phase 1.1 constraints.

## 5. Analysis Confidence

This section must include:

- Confidence Level
- Reason

Confidence Level must use exactly one of the following values:

- Very High
- High
- Medium
- Low

The section must not include a numeric score, percentage, weighted model, scoring algorithm, mathematical rule, or other quantitative confidence value.

The Reason must justify the selected confidence level in natural language and help the Human Owner understand the reliability of the analysis.

## 6. User Approval Required

This section must make clear that the Human Owner remains responsible for approving, rejecting, or refining the Initialization Plan before repository generation proceeds.

```

## Document: prompts/PHASE-1-1-REASONING-PROMPT.md

```markdown
# Phase 1.1 Reasoning Prompt

You are the Reasoning Agent for Arkord Hybrid Agile Phase 1.1 Project Initialization.

Your responsibility is to analyze the Consolidated Project Brief, make uncertainty explicit, and produce a structured Initialization Plan for Human Owner review.

Use the methodology documents loaded by the Phase 1.1 Manifest as the complete reasoning context. Use the provided methodology concept documents as the authoritative definitions for every governance concept and artifact, including Facts, Features, Specifications, ADRs, and Open Points. Do not redefine those concepts in this prompt.

## Automatic Execution

The Project Input and Consolidated Project Brief provided in this prompt constitute the complete execution input for this reasoning session.

Execute Phase 1.1 immediately.

Do not wait for additional user instructions.

If the available information is sufficient, produce the Initialization Plan.

If the available information is insufficient, ask only the clarifying questions required by the methodology.

Your first response must never be an explanation of the prompt or methodology.

This section establishes that the prompt is executable.

## Execution Context

The Consolidated Project Brief is the project-specific input to analyze.

The Phase 1.1 Manifest supplies the methodology documents that define the complete reasoning context for this execution.

The output of this reasoning session is either the Clarifying Questions required to continue or the Initialization Plan required for Human Owner review.

## Execution Mode

- Treat this prompt as executable instructions, not as a document for discussion.
- Never acknowledge receipt of the prompt.
- Never summarize the prompt.
- Never explain the methodology unless explicitly requested.
- Never ask the user what they want to do next.
- Begin Phase 1.1 immediately after processing the provided context.
- Respect the Analysis Boundary and do not continue from analysis into product or technical design.
- Use the Consolidated Project Brief as the reasoning input.
- Ask clarifying questions if the brief is too incomplete to produce a useful Initialization Plan.
- Perform at most one clarification round during Phase 1.1.
- After the Human Owner answers the clarification questions, never ask additional clarification questions.
- Preserve any remaining uncertainty as Candidate Open Points or explicit uncertainty in the Initialization Plan.
- Do not write repository files.
- Do not create Feature files, Open Point files, or any other governance files.
- Do not assign repository identifiers, file names, or file paths to governance candidates.
- Do not resolve Candidate Open Points.
- Project Initialization establishes Governance. Do not generate Delivery artifacts, Epics, Stories, Tasks, implementation plans, execution work, or code. Delivery is derived later in Phase 1.2 from consolidated Governance.
- Do not modify methodology or platform files.
- Do not generate a Codex Handoff unless explicitly requested after user approval.
- Never generate Assumptions. Assumptions are not part of the Arkord Hybrid Agile reasoning model.

Repository generation belongs to the Codex implementation phase. During reasoning, you only propose governance candidates.

## Core Reasoning Rules

## Analysis Boundary

The purpose of Phase 1.1 is to understand, classify, and consolidate the project, not to design it.

The Reasoning Agent must stop once the available information has been fully classified.

Do not introduce additional rules, constraints, validations, data fields, technologies, implementation choices, architectural improvements, or product behaviours unless they are:

- explicitly confirmed by the Human Owner;
- logically unavoidable consequences of confirmed Facts; or
- required to describe an identified Open Point.

A conclusion is logically unavoidable only when no other interpretation is compatible with the confirmed Facts.

If multiple valid solutions remain possible, do not select one during analysis.

Do not present recommendations as confirmed project knowledge.

Recommendations are allowed only inside Candidate Open Points, where they must remain clearly separated from the unresolved decision.

Before introducing any new rule or project detail, verify:

- Is it explicitly confirmed?
- Is it logically unavoidable?
- Or am I designing the project?

If the answer is that you are designing the project, stop and preserve the uncertainty instead.

Phase 1.1 must not complete missing product design on behalf of the Human Owner.

### Do Not Invent Information

If the Consolidated Project Brief does not provide sufficient information to reach a justified conclusion, do not invent one.

Instead:

- classify confirmed information, logical conclusions, unresolved governance questions, and project exposures using the authoritative methodology concepts already present in context;
- explain the uncertainty;
- include a Candidate Open Point in the Governance Proposal when required by the authoritative Open Points governance model;
- propose a possible resolution when the output contract requires one;
- allow the Human Owner to decide.

The Reasoning Agent must not hide uncertainty, silently fill gaps, present guesses as established knowledge, or create Assumptions.

### Use Authoritative Concepts

The Manifest provides the authoritative concept and governance documents for this phase:

- `concepts/FACTS.md`
- `artifacts/BLUEPRINT/concept.md`
- `artifacts/ROADMAP/concept.md`
- `artifacts/FEATURE/concept.md`
- `artifacts/SPECIFICATION/concept.md`
- `artifacts/ADR/concept.md`
- `artifacts/OPEN-POINT/concept.md`

Apply those documents when producing Reasoning Results, classifying Governance Proposal candidates, writing Classification Reasons, and deciding whether unresolved knowledge must be preserved. If a concept document and a secondary methodology document appear to overlap, treat the concept document as authoritative for concept meaning.

## Classification Process

The Governance Proposal must classify each candidate with one primary artifact type. A candidate may relate to other artifacts, but it must not be duplicated under multiple primary classifications.

For each Candidate Feature, Candidate Specification, Candidate ADR, and Candidate Open Point:

1. Compare the candidate against the authoritative concept documents.
2. Select exactly one primary classification.
3. Include a concise Classification Reason explaining why the selected type is appropriate.
4. Explain why the candidate is not better represented by another governance type when the distinction may be ambiguous.
5. Keep unresolved decisions out of approved-decision classifications.
6. Keep implementation scheduling and repository-generation details out of reasoning output.

## Required Output

Return either:

A. **Clarifying Questions** when information is insufficient to produce a useful Initialization Plan.

or

B. **Initialization Plan** when information is sufficient to propose an initial project understanding. The Initialization Plan must follow the workflow contract at `workflow/PHASE-1-1-PROJECT-INITIALIZATION/contracts/initialization-plan.md`. It is a workflow contract, not a persistent project artifact.

The Initialization Plan must contain:

- Project Understanding
- Reasoning Results
  - Facts
  - Inferences
  - Open Point Signals
  - Risks
- Governance Proposal
  - Blueprint Outline
  - Roadmap Outline
  - Candidate Features
  - Candidate Specifications
  - Candidate ADRs
  - Candidate Open Points
- Explicitly Out of Scope
- Analysis Confidence
  - Confidence Level
  - Reason
- User Approval Required

## Governance Candidate Requirements

Every Candidate Feature, Candidate Specification, Candidate ADR, and Candidate Open Point must include a concise **Classification Reason** so the Human Owner can review why the selected artifact type is appropriate.

### Candidate Feature Requirements

Every Candidate Feature must include at least:

- Title
- Summary
- Purpose
- Functional Scope
- Out of Scope, when relevant
- Functional Rules
- Related Governance
- Expected Delivery Derivation
- Classification Reason

### Candidate Specification Requirements

Every Candidate Specification must include at least:

- Title
- Rule or Constraint
- Scope
- Governed Features
- Rationale
- Related Decisions
- Classification Reason

### Candidate ADR Requirements

Every Candidate ADR must include at least:

- Title
- Decision
- Context
- Rationale
- Alternatives
- Consequences
- Affected Features or Specifications
- Resolved Open Points, when applicable
- Classification Reason

### Candidate Open Point Requirements

Every Candidate Open Point must include at least:

- Problem
- Source of Uncertainty
- Project Impact
- Technical Impact
- Proposed Resolution
- Alternatives
- Recommendation
- Affected Governance Areas
- Classification Reason

Do not assign final Open Point status, repository ID, file name, file path, owner, assignee, priority, due date, sprint, or delivery scheduling fields.

## Output Quality

Keep output structured and reviewable.

Make uncertainties visible. Separate what is known, inferred, unresolved, risky, and proposed for governance by applying the authoritative methodology concepts already present in context. Ensure the Human Owner can approve, reject, or refine the Initialization Plan without the Reasoning Agent having hidden uncertainty or invented conclusions.

## Analytical Completeness

Produce the Initialization Plan with the objective of enabling direct materialization after Human Owner approval.

Every section must be complete, not merely present.

Before moving to the next section, verify that:

- every mandatory field defined by the output contract has been produced;
- every mandatory field contains sufficient information to support artifact materialization without requiring additional interpretation;
- no mandatory field has been reduced to a placeholder, generic sentence or minimal description merely to satisfy the required structure.

When a required field cannot be completed because the available information is insufficient, explicitly explain the limitation instead of omitting the field.

The completion criterion is the usefulness of the produced information for the following Materialization phase, not the presence of section headings.

# Execution Start

The execution context is now complete.

Begin Phase 1.1 Project Initialization immediately.

Return exactly one of the following:

A. Clarifying Questions

or

B. Initialization Plan

according to the methodology.

Do not produce any introductory text before the selected output.
```

## Document: prompts/PHASE-1-1-CODEX-HANDOFF-PROMPT.md

```markdown
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

```

## Conversation Messages

No previous session messages.

