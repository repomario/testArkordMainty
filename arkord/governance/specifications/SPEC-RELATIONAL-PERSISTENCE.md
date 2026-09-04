---
nodeId: SPEC-RELATIONAL-PERSISTENCE
nodeType: SPECIFICATION
title: Relational Persistence
status: PROPOSED
summary: La persistenza dei dati deve utilizzare un database relazionale.
relations:
  updatedBy: []
  governs:
    - FEATURE-TASK-MANAGEMENT
  supportedBy: []
  resolves: []
  relatedTo:
    - OPEN-POINT-RELATIONAL-DATABASE-DECISION
metadata:
  revision: 1
  createdDuring: PHASE-1-1-PROJECT-INITIALIZATION
  lastUpdated: "2026-09-04"
---

# Relational Persistence

## Rule or Constraint

La persistenza dei dati deve utilizzare un database relazionale.

## Scope

Dati persistenti dell’applicazione.

## Governed Features

- `FEATURE-TASK-MANAGEMENT`

## Rationale

Vincolo tecnico esplicitamente definito.

## Related Decisions

La relazione con un eventuale ADR è mantenuta irrisolta in `OPEN-POINT-RELATIONAL-DATABASE-DECISION`.

## Resolved Open Points

Nessuno.

## Notes

### Classification Reason

È una Specification perché stabilisce un vincolo persistente sul modello di persistenza. La metodologia identifica il Relational Persistence Model come esempio di Specification.

## Changelog

- Revisione 1: materializzazione iniziale durante la Phase 1.1.
