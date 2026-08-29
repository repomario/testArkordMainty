---
{
  "nodeId": "permanent-audit-scope",
  "nodeType": "OPEN_POINT",
  "title": "Permanent Audit Scope",
  "status": "OPEN",
  "summary": "Non è definito quali operazioni richiedano audit permanente.",
  "relations": {
    "updatedBy": [],
    "resolvedBy": [],
    "relatedTo": []
  },
  "metadata": {
    "revision": 1,
    "createdDuring": "PHASE-1-1-PROJECT-INITIALIZATION",
    "lastUpdated": "2026-08-29T00:00:00Z"
  }
}
---

# Permanent Audit Scope

## Problem

Non è definito quali operazioni richiedano audit permanente.

## Source of Uncertainty

Il Brief prescrive auditabilità per operazioni importanti ma lascia aperto il loro insieme.

## Project Impact

Influenza responsabilità e capacità di ricostruzione degli eventi.

## Technical Impact

Influenza modello audit, retention e copertura degli eventi.

## Proposed Resolution

Identificare l’insieme minimo di eventi soggetti ad audit permanente.

## Alternatives

Solo eventi security-sensitive; eventi di dominio principali; audit esteso delle mutazioni.

## Recommendation

Partire dagli eventi con impatto su accesso, assegnazioni, lifecycle e storico, lasciando la decisione finale al Human Owner.

## Affected Areas

Activity Traceability, Security, Work Orders, User Administration.

## Classification Reason

Il requisito esiste ma il suo confine è esplicitamente irrisolto e materialmente significativo.

## Resolution

Unresolved.

## Changelog

- Revision 1: Initial Phase 1.1 materialization.
