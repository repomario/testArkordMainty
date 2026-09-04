---
nodeId: asset-management
nodeType: FEATURE
title: Asset Management
status: APPROVED
summary: Gestione degli asset fisici soggetti a manutenzione.
relations:
  updatedBy: [
    ]
  governedBy:
  - historical-data-preservation
  - asset-facility-relationship
  - responsive-role-oriented-web-ui
  - relational-persistence
  - transactional-consistency-of-critical-operations
  - honest-operation-failure-feedback
  relatedTo: [
    ]
metadata:
  revision: 1
  createdDuring: PHASE-1-1-PROJECT-INITIALIZATION
  lastUpdated: '2026-08-29T00:00:00Z'
---

# Asset Management

## Purpose

Identificare gli elementi mantenuti e collegarne lo storico.

## Functional Scope

Creazione, modifica, consultazione, associazione a Facility, disattivazione e storico.

## Out of Scope

Not specified.

## Functional Rules

Ogni Asset appartiene a una Facility; gli Asset disattivati mantengono lo storico.

## Related Governance

Facility Management, Work Orders e storico manutentivo.

## Expected Delivery Derivation

Gestione Asset e relativa consultazione storica.

## Classification Reason

Modella una capacità funzionale stabile relativa a un’entità centrale del dominio.

## Changelog

- Revision 1: Initial Phase 1.1 materialization.
