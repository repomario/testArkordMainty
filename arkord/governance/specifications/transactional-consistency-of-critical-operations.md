---
{
  "nodeId": "transactional-consistency-of-critical-operations",
  "nodeType": "SPECIFICATION",
  "title": "Transactional Consistency of Critical Operations",
  "status": "PROPOSED",
  "summary": "Le operazioni principali non devono lasciare stati incoerenti; particolare attenzione ad assegnazioni, lifecycle Work Order, associazioni Asset/Facility e storico.",
  "relations": {
    "updatedBy": [],
    "governs": [
      "work-order-management",
      "technician-assignment-and-work-queue",
      "asset-management",
      "comments-and-maintenance-history"
    ],
    "supportedBy": [
      "postgresql-for-structured-persistence"
    ],
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

# Transactional Consistency of Critical Operations

## Rule or Constraint

Le operazioni principali non devono lasciare stati incoerenti; particolare attenzione ad assegnazioni, lifecycle Work Order, associazioni Asset/Facility e storico.

## Scope

Operazioni mutative principali.

## Governed Features

- `work-order-management`
- `technician-assignment-and-work-queue`
- `asset-management`
- `comments-and-maintenance-history`

## Rationale

Requisito esplicito di reliability/data integrity.

## Related Decisions

- `postgresql-for-structured-persistence`

## Resolved Open Points


## Notes

Classification reason: È un reliability constraint trasversale.

## Changelog

- Revision 1: Initial Phase 1.1 materialization.
