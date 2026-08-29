---
{
  "nodeId": "backend-authorization-enforcement",
  "nodeType": "SPECIFICATION",
  "title": "Backend Authorization Enforcement",
  "status": "PROPOSED",
  "summary": "Le autorizzazioni devono essere applicate dal backend e non affidate esclusivamente alla UI.",
  "relations": {
    "updatedBy": [],
    "governs": [
      "authentication-and-user-access",
      "user-and-role-administration"
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

# Backend Authorization Enforcement

## Rule or Constraint

Le autorizzazioni devono essere applicate dal backend e non affidate esclusivamente alla UI.

## Scope

Tutte le operazioni protette.

## Governed Features

- `authentication-and-user-access`
- `user-and-role-administration`

## Rationale

Requisito esplicito di sicurezza e accesso.

## Related Decisions

- `client-server-web-architecture`

## Resolved Open Points


## Notes

Classification reason: È un vincolo di sicurezza trasversale, non una capacità funzionale.

## Changelog

- Revision 1: Initial Phase 1.1 materialization.
