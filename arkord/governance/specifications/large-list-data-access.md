---
{
  "nodeId": "large-list-data-access",
  "nodeType": "SPECIFICATION",
  "title": "Large List Data Access",
  "status": "PROPOSED",
  "summary": "Liste potenzialmente grandi non devono richiedere necessariamente il caricamento dell’intero dataset in una singola richiesta.",
  "relations": {
    "updatedBy": [],
    "governs": [
      "work-order-search-and-filtering",
      "comments-and-maintenance-history",
      "operational-dashboard"
    ],
    "supportedBy": [
      "client-server-web-architecture"
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

# Large List Data Access

## Rule or Constraint

Liste potenzialmente grandi non devono richiedere necessariamente il caricamento dell’intero dataset in una singola richiesta.

## Scope

Work Order list e storico.

## Governed Features

- `work-order-search-and-filtering`
- `comments-and-maintenance-history`
- `operational-dashboard`

## Rationale

Requisito prestazionale esplicito.

## Related Decisions

- `client-server-web-architecture`

## Resolved Open Points


## Notes

Classification reason: È un quality/performance constraint.

## Changelog

- Revision 1: Initial Phase 1.1 materialization.
