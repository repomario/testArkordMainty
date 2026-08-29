---
{
  "nodeId": "postgresql-for-structured-persistence",
  "nodeType": "DECISION",
  "title": "PostgreSQL for Structured Persistence",
  "status": "PROPOSED",
  "summary": "Utilizzare PostgreSQL per i dati strutturati principali.",
  "relations": {
    "updatedBy": [],
    "resolves": [],
    "supports": [
      "relational-persistence"
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

# PostgreSQL for Structured Persistence

## Decision

Utilizzare PostgreSQL per i dati strutturati principali.

## Context

Il dominio contiene numerose relazioni persistenti e richiede integrità e storico.

## Rationale

PostgreSQL è esplicitamente richiesto dal Brief.

## Alternatives

Altri database relazionali o modelli non relazionali, non selezionati.

## Consequences

Il modello persistente strutturato deve essere compatibile con PostgreSQL e con l’integrità relazionale richiesta.

## Affected Features or Specifications

- `relational-persistence`

## Resolved Open Points

None.

## Classification Reason

È una scelta tecnologica concreta già confermata che deve rimanere tracciabile nel tempo.

## Changelog

- Revision 1: Initial Phase 1.1 materialization.
