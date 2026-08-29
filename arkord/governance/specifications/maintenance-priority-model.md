---
{
  "nodeId": "maintenance-priority-model",
  "nodeType": "SPECIFICATION",
  "title": "Maintenance Priority Model",
  "status": "PROPOSED",
  "summary": "Le priorità iniziali sono Low, Medium, High e Critical; Critical deve essere chiaramente distinguibile.",
  "relations": {
    "updatedBy": [],
    "governs": [
      "maintenance-request-management",
      "work-order-management",
      "operational-dashboard",
      "technician-assignment-and-work-queue"
    ],
    "supportedBy": [],
    "resolves": [],
    "relatedTo": []
  },
  "metadata": {
    "revision": 1,
    "createdDuring": "PHASE-1-1-PROJECT-INITIALIZATION",
    "lastUpdated": "2026-08-29T00:00:00Z"
  }
}
---

# Maintenance Priority Model

## Rule or Constraint

Le priorità iniziali sono Low, Medium, High e Critical; Critical deve essere chiaramente distinguibile.

## Scope

Maintenance Request e Work Order dove applicabile.

## Governed Features

- `maintenance-request-management`
- `work-order-management`
- `operational-dashboard`
- `technician-assignment-and-work-queue`

## Rationale

Modello di priorità esplicitamente definito.

## Related Decisions

None.

## Resolved Open Points


## Notes

Classification reason: È un modello/regola trasversale e non una capacità autonoma.

## Changelog

- Revision 1: Initial Phase 1.1 materialization.
