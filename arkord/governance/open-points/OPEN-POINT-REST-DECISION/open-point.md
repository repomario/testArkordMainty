---
nodeId: OPEN-POINT-REST-DECISION
nodeType: OPEN_POINT
title: Governance Treatment of REST Decision
status: OPEN
summary: REST è una modalità di comunicazione confermata e contemporaneamente indicata tra le decisioni architetturali già definite, ma manca la relativa decision history.
relations:
  updatedBy: []
  relatedTo:
    - SPEC-REST-COMMUNICATION
    - BLUEPRINT-TASKFLOW-LITE
metadata:
  revision: 1
  createdDuring: PHASE-1-1-PROJECT-INITIALIZATION
  lastUpdated: "2026-09-04"
---

# Governance Treatment of REST Decision

## Problem

REST è una modalità di comunicazione confermata e contemporaneamente indicata tra le decisioni architetturali già definite, ma manca la relativa decision history.

## Source of Uncertainty

Project Brief.

## Project Impact

Influenza la completezza e traceability della Governance.

## Technical Impact

Riguarda il contratto di comunicazione frontend/backend.

## Proposed Resolution

Determinare se la scelta REST debba avere anche una rappresentazione ADR e, in caso positivo, acquisire rationale e alternative.

## Alternatives

- Rappresentarla esclusivamente come Specification.
- Rappresentarla anche tramite ADR dopo aver consolidato la decision history.

## Recommendation

Mantenere il vincolo REST come Specification fino alla risoluzione dell’Open Point.

## Affected Governance Areas

- `SPEC-REST-COMMUNICATION`
- `BLUEPRINT-TASKFLOW-LITE`

## Classification Reason

Il vincolo REST è confermato, mentre la corretta rappresentazione della decisione e del suo rationale resta irrisolta e richiede intervento del Human Owner.

## Changelog

- Revisione 1: materializzazione iniziale durante la Phase 1.1.
