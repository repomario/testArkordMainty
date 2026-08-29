---
{
  "nodeId": "asset-facility-relationship",
  "nodeType": "SPECIFICATION",
  "title": "Asset–Facility Relationship",
  "status": "PROPOSED",
  "summary": "Ogni Asset deve appartenere a una Facility.",
  "relations": {
    "updatedBy": [],
    "governs": [
      "facility-management",
      "asset-management"
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

# Asset–Facility Relationship

## Rule or Constraint

Ogni Asset deve appartenere a una Facility.

## Scope

Asset.

## Governed Features

- `facility-management`
- `asset-management`

## Rationale

Relazione esplicitamente richiesta.

## Related Decisions

- `postgresql-for-structured-persistence`

## Resolved Open Points


## Notes

Classification reason: È una regola stabile del modello di dominio.

## Changelog

- Revision 1: Initial Phase 1.1 materialization.
