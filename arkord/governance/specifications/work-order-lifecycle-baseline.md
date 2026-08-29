---
{
  "nodeId": "work-order-lifecycle-baseline",
  "nodeType": "SPECIFICATION",
  "title": "Work Order Lifecycle Baseline",
  "status": "PROPOSED",
  "summary": "Gli stati principali sono Open, Assigned, In Progress, Completed e Cancelled; transizioni chiaramente incompatibili devono essere impedite; iniziare un intervento porta a In Progress.",
  "relations": {
    "updatedBy": [],
    "governs": [
      "work-order-management",
      "work-execution"
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

# Work Order Lifecycle Baseline

## Rule or Constraint

Gli stati principali sono Open, Assigned, In Progress, Completed e Cancelled; transizioni chiaramente incompatibili devono essere impedite; iniziare un intervento porta a In Progress.

## Scope

Work Order.

## Governed Features

- `work-order-management`
- `work-execution`

## Rationale

Lifecycle esplicitamente descritto.

## Related Decisions

None.

## Resolved Open Points


## Notes

Classification reason: È una regola di lifecycle che governa Feature funzionali; la parte non definita viene preservata come Open Point.

## Changelog

- Revision 1: Initial Phase 1.1 materialization.
