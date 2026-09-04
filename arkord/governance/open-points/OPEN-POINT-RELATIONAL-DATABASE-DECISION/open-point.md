---
nodeId: OPEN-POINT-RELATIONAL-DATABASE-DECISION
nodeType: OPEN_POINT
title: Governance Treatment of Relational Database Decision
status: OPEN
summary: Il database relazionale è dichiarato sia come vincolo tecnico sia come decisione architetturale già definita, ma non sono forniti rationale e alternative necessari per determinarne una rappresentazione ADR completa.
relations:
  updatedBy: []
  relatedTo:
    - BLUEPRINT-TASKFLOW-LITE
    - SPEC-RELATIONAL-PERSISTENCE
metadata:
  revision: 1
  createdDuring: PHASE-1-1-PROJECT-INITIALIZATION
  lastUpdated: "2026-09-04"
---

# Governance Treatment of Relational Database Decision

## Problem

Il database relazionale è dichiarato sia come vincolo tecnico sia come decisione architetturale già definita, ma non sono forniti rationale e alternative necessari per determinarne una rappresentazione ADR completa.

## Source of Uncertainty

Project Brief incompleto rispetto alla struttura decisionale ADR.

## Project Impact

Influenza la completezza della Governance relativa alla persistenza.

## Technical Impact

Riguarda direttamente il modello di persistenza e future decisioni tecniche.

## Proposed Resolution

Stabilire se la decisione debba essere preservata tramite ADR e, in caso positivo, fornire il relativo rationale e le alternative considerate.

## Alternatives

- Mantenerla esclusivamente come Specification o vincolo architetturale.
- Creare successivamente un ADR con decision history confermata.

## Recommendation

Non inventare rationale o alternative; mantenere intanto il vincolo confermato come Specification.

## Affected Governance Areas

- `BLUEPRINT-TASKFLOW-LITE`
- `SPEC-RELATIONAL-PERSISTENCE`

## Classification Reason

La scelta tecnica è confermata, ma le informazioni necessarie per rappresentarne correttamente la decision history sono irrisolte. L’incertezza deve essere preservata invece di completare artificialmente un ADR.

## Changelog

- Revisione 1: materializzazione iniziale durante la Phase 1.1.
