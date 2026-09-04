---
nodeId: SPEC-REST-COMMUNICATION
nodeType: SPECIFICATION
title: REST Communication Constraint
status: APPROVED
summary: Frontend e backend devono comunicare mediante API REST.
relations:
  updatedBy: [
    ]
  governs:
  - FEATURE-TASK-MANAGEMENT
  - FEATURE-TASK-FILTERING
  supportedBy: [
    ]
  resolves: [
    ]
  relatedTo:
  - OPEN-POINT-REST-DECISION
metadata:
  revision: 1
  createdDuring: PHASE-1-1-PROJECT-INITIALIZATION
  lastUpdated: '2026-09-04'
---

# REST Communication Constraint

## Rule or Constraint

Frontend e backend devono comunicare mediante API REST.

## Scope

Comunicazione client/server.

## Governed Features

- `FEATURE-TASK-MANAGEMENT`
- `FEATURE-TASK-FILTERING`

## Rationale

Modalità di comunicazione esplicitamente definita dal brief.

## Related Decisions

Un eventuale ADR REST rimane oggetto di `OPEN-POINT-REST-DECISION`.

## Resolved Open Points

Nessuno.

## Notes

### Classification Reason

È una Specification perché rappresenta un interface/architectural constraint stabile, non una capability funzionale.

## Changelog

- Revisione 1: materializzazione iniziale durante la Phase 1.1.
