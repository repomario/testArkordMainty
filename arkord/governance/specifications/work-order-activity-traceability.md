---
{
  "nodeId": "work-order-activity-traceability",
  "nodeType": "SPECIFICATION",
  "title": "Work Order Activity Traceability",
  "status": "PROPOSED",
  "summary": "Devono essere ricostruibili almeno creazione, assegnazione, cambio stato, modifica priorità e completamento; quando possibile va distinta l’origine automatica dalle azioni utente.",
  "relations": {
    "updatedBy": [],
    "governs": [
      "work-order-management",
      "comments-and-maintenance-history"
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

# Work Order Activity Traceability

## Rule or Constraint

Devono essere ricostruibili almeno creazione, assegnazione, cambio stato, modifica priorità e completamento; quando possibile va distinta l’origine automatica dalle azioni utente.

## Scope

Work Order history.

## Governed Features

- `work-order-management`
- `comments-and-maintenance-history`

## Rationale

Requisito esplicito di tracciabilità.

## Related Decisions

None.

## Resolved Open Points


## Notes

Classification reason: È una regola di tracciabilità, non una Feature.

## Changelog

- Revision 1: Initial Phase 1.1 materialization.
