---
{
  "nodeId": "historical-data-preservation",
  "nodeType": "SPECIFICATION",
  "title": "Historical Data Preservation",
  "status": "PROPOSED",
  "summary": "Dati storici associati a utenti, Facility, Asset e interventi devono essere preservati quando le entità vengono disattivate o non sono più operative.",
  "relations": {
    "updatedBy": [],
    "governs": [
      "user-and-role-administration",
      "facility-management",
      "asset-management",
      "work-order-management",
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

# Historical Data Preservation

## Rule or Constraint

Dati storici associati a utenti, Facility, Asset e interventi devono essere preservati quando le entità vengono disattivate o non sono più operative.

## Scope

Entità con riferimenti storici.

## Governed Features

- `user-and-role-administration`
- `facility-management`
- `asset-management`
- `work-order-management`
- `comments-and-maintenance-history`

## Rationale

Il Brief richiede ripetutamente conservazione dello storico.

## Related Decisions

- `postgresql-for-structured-persistence`

## Resolved Open Points


## Notes

Classification reason: È una regola stabile di integrità e conservazione dati.

## Changelog

- Revision 1: Initial Phase 1.1 materialization.
