---
{
  "nodeId": "relational-persistence",
  "nodeType": "SPECIFICATION",
  "title": "Relational Persistence",
  "status": "PROPOSED",
  "summary": "I dati strutturati principali devono essere persistiti in PostgreSQL mantenendo l’integrità delle relazioni di dominio.",
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

# Relational Persistence

## Rule or Constraint

I dati strutturati principali devono essere persistiti in PostgreSQL mantenendo l’integrità delle relazioni di dominio.

## Scope

Persistenza applicativa strutturata.

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

PostgreSQL e database relazionale sono requisiti espliciti.

## Related Decisions

- `postgresql-for-structured-persistence`

## Resolved Open Points


## Notes

Classification reason: È un vincolo architetturale/data model, non una capacità funzionale.

## Changelog

- Revision 1: Initial Phase 1.1 materialization.
