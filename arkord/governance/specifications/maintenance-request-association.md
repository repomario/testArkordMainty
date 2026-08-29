---
{
  "nodeId": "maintenance-request-association",
  "nodeType": "SPECIFICATION",
  "title": "Maintenance Request Association",
  "status": "PROPOSED",
  "summary": "Ogni Maintenance Request riguarda una Facility e può opzionalmente riferirsi a un Asset.",
  "relations": {
    "updatedBy": [],
    "governs": [
      "maintenance-request-management"
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

# Maintenance Request Association

## Rule or Constraint

Ogni Maintenance Request riguarda una Facility e può opzionalmente riferirsi a un Asset.

## Scope

Maintenance Request.

## Governed Features

- `maintenance-request-management`

## Rationale

Requisito esplicito del Brief.

## Related Decisions

- `postgresql-for-structured-persistence`

## Resolved Open Points


## Notes

Classification reason: È una regola di modello che governa la Feature.

## Changelog

- Revision 1: Initial Phase 1.1 materialization.
