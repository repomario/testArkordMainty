---
{
  "nodeId": "honest-operation-failure-feedback",
  "nodeType": "SPECIFICATION",
  "title": "Honest Operation Failure Feedback",
  "status": "PROPOSED",
  "summary": "Un errore backend non deve essere presentato all’utente come operazione completata con successo.",
  "relations": {
    "updatedBy": [],
    "governs": [
      "authentication-and-user-access",
      "user-and-role-administration",
      "facility-management",
      "asset-management",
      "maintenance-request-management",
      "work-order-management",
      "technician-assignment-and-work-queue",
      "work-execution",
      "comments-and-maintenance-history",
      "attachment-management",
      "work-order-search-and-filtering",
      "operational-dashboard",
      "in-app-operational-notifications"
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

# Honest Operation Failure Feedback

## Rule or Constraint

Un errore backend non deve essere presentato all’utente come operazione completata con successo.

## Scope

Operazioni mutative user-facing.

## Governed Features

- `authentication-and-user-access`
- `user-and-role-administration`
- `facility-management`
- `asset-management`
- `maintenance-request-management`
- `work-order-management`
- `technician-assignment-and-work-queue`
- `work-execution`
- `comments-and-maintenance-history`
- `attachment-management`
- `work-order-search-and-filtering`
- `operational-dashboard`
- `in-app-operational-notifications`

## Rationale

Requisito esplicito di affidabilità.

## Related Decisions

- `client-server-web-architecture`

## Resolved Open Points


## Notes

Classification reason: È una regola di affidabilità dell’interfaccia e del contratto client/server.

## Changelog

- Revision 1: Initial Phase 1.1 materialization.
