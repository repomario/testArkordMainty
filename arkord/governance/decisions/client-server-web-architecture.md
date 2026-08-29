---
{
  "nodeId": "client-server-web-architecture",
  "nodeType": "DECISION",
  "title": "Client/Server Web Architecture",
  "status": "PROPOSED",
  "summary": "Utilizzare una web application con frontend e backend separati comunicanti tramite API HTTP.",
  "relations": {
    "updatedBy": [],
    "resolves": [],
    "supports": [
      "backend-authorization-enforcement",
      "honest-operation-failure-feedback"
    ],
    "impacts": [],
    "supersedes": [],
    "supersededBy": [],
    "relatedTo": []
  },
  "metadata": {
    "revision": 1,
    "createdDuring": "PHASE-1-1-PROJECT-INITIALIZATION",
    "lastUpdated": "2026-08-29T00:00:00Z"
  }
}
---

# Client/Server Web Architecture

## Decision

Utilizzare una web application con frontend e backend separati comunicanti tramite API HTTP.

## Context

Mainty deve servire esperienze desktop e mobile-web mantenendo business logic e sicurezza lato server.

## Rationale

Il Project Brief prescrive esplicitamente questa direzione.

## Alternatives

Architettura monolitica senza separazione frontend/backend; applicazioni native; altre forme di integrazione non richieste.

## Consequences

Il backend diventa responsabile di business logic, autorizzazione, validazione, persistenza e lifecycle; frontend e backend possono evolvere separatamente.

## Affected Features or Specifications

- `backend-authorization-enforcement`
- `honest-operation-failure-feedback`

## Resolved Open Points

None.

## Classification Reason

È una decisione architetturale esplicitamente confermata con conseguenze permanenti e quindi richiede rationale tracciabile.

## Changelog

- Revision 1: Initial Phase 1.1 materialization.
