---
{
  "nodeId": "maintenance-request-management",
  "nodeType": "FEATURE",
  "title": "Maintenance Request Management",
  "status": "PROPOSED",
  "summary": "Segnalazione e gestione iniziale dei problemi manutentivi.",
  "relations": {
    "updatedBy": [],
    "governedBy": [
      "maintenance-request-association",
      "maintenance-priority-model",
      "responsive-role-oriented-web-ui",
      "relational-persistence",
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

# Maintenance Request Management

## Purpose

Acquisire problemi che possono richiedere un intervento.

## Functional Scope

Creazione e consultazione delle segnalazioni, priorità, Facility, Asset opzionale e fotografie.

## Out of Scope

Not specified.

## Functional Rules

Una richiesta può esistere senza Asset; Critical deve essere distinguibile.

## Related Governance

Work Order Management, Attachment Handling e prioritizzazione.

## Expected Delivery Derivation

Flussi di segnalazione e gestione Maintenance Request.

## Classification Reason

È una capacità utente stabile distinta dal lavoro pianificato rappresentato dal Work Order.

## Changelog

- Revision 1: Initial Phase 1.1 materialization.
