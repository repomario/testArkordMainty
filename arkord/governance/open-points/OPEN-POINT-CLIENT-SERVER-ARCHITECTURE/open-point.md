---
nodeId: OPEN-POINT-CLIENT-SERVER-ARCHITECTURE
nodeType: OPEN_POINT
title: Governance Treatment of Client/Server Architecture
status: OPEN
summary: Client/server è indicata come decisione architetturale già definita, ma il Project Brief non contiene rationale e alternative.
relations:
  updatedBy: []
  relatedTo:
    - BLUEPRINT-TASKFLOW-LITE
metadata:
  revision: 1
  createdDuring: PHASE-1-1-PROJECT-INITIALIZATION
  lastUpdated: "2026-09-04"
---

# Governance Treatment of Client/Server Architecture

## Problem

Client/server è indicata come decisione architetturale già definita, ma il Project Brief non contiene rationale e alternative.

## Source of Uncertainty

Project Brief.

## Project Impact

Influenza la documentazione permanente della direzione architetturale.

## Technical Impact

Influenza la struttura generale del sistema.

## Proposed Resolution

Stabilire se client/server debba essere rappresentata tramite ADR e acquisire l’eventuale decision history.

## Alternatives

- Mantenerla come direzione o vincolo architetturale confermato.
- Formalizzarla successivamente mediante ADR.

## Recommendation

Preservare la direzione nel Blueprint senza inventare una decision history.

## Affected Governance Areas

- `BLUEPRINT-TASKFLOW-LITE`

## Classification Reason

Non è in discussione il Fact che l’architettura sia client/server; è irrisolto come debba essere rappresentata la relativa decisione nella Governance permanente.

## Changelog

- Revisione 1: materializzazione iniziale durante la Phase 1.1.
