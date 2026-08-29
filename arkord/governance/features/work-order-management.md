---
{
  "nodeId": "work-order-management",
  "nodeType": "FEATURE",
  "title": "Work Order Management",
  "status": "PROPOSED",
  "summary": "Gestione del lavoro manutentivo pianificato ed eseguito.",
  "relations": {
    "updatedBy": [],
    "governedBy": [
      "historical-data-preservation",
      "maintenance-priority-model",
      "work-order-lifecycle-baseline",
      "work-order-activity-traceability",
      "responsive-role-oriented-web-ui",
      "relational-persistence",
      "transactional-consistency-of-critical-operations",
      "honest-operation-failure-feedback"
    ],
    "relatedTo": []
  },
  "metadata": {
    "revision": 1,
    "createdDuring": "PHASE-1-1-PROJECT-INITIALIZATION",
    "lastUpdated": "2026-08-29T00:00:00Z"
  }
}
---

# Work Order Management

## Purpose

Trasformare necessità manutentive in attività operative controllabili.

## Functional Scope

Creazione, modifica, priorità, stato, pianificazione, assegnazione e completamento.

## Out of Scope

Pianificazione avanzata delle risorse.

## Functional Rules

Lifecycle principale Open, Assigned, In Progress, Completed, Cancelled; transizioni incompatibili devono essere impedite.

## Related Governance

Assignment, Work Execution, History e lifecycle Work Order.

## Expected Delivery Derivation

Gestione completa del Work Order.

## Classification Reason

Rappresenta una capacità funzionale centrale; le regole esatte delle transizioni appartengono alle Specification/Open Point quando irrisolte.

## Changelog

- Revision 1: Initial Phase 1.1 materialization.
