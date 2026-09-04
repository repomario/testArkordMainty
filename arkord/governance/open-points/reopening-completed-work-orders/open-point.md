---
{
  "nodeId": "reopening-completed-work-orders",
  "nodeType": "OPEN_POINT",
  "title": "Reopening Completed Work Orders",
  "status": "OPEN",
  "summary": "Non è definito se un Work Order completato possa essere riaperto eccezionalmente e da quali ruoli.",
  "relations": {
    "updatedBy": [],
    "resolvedBy": [],
    "relatedTo": []
  },
  "metadata": {
    "revision": 1,
    "createdDuring": "PHASE-1-1-PROJECT-INITIALIZATION",
    "lastUpdated": "2026-08-29T00:00:00Z"
  }
}
---

# Reopening Completed Work Orders

## Problem

Non è definito se un Work Order completato possa essere riaperto eccezionalmente e da quali ruoli.

## Source of Uncertainty

Il Brief vieta il ritorno accidentale a In Progress ma dichiara esplicitamente irrisolta la riapertura eccezionale.

## Project Impact

Influenza il lifecycle operativo e la gestione delle correzioni post-completamento.

## Technical Impact

Influenza transizioni di stato, autorizzazioni e storico.

## Proposed Resolution

Definire se la riapertura è consentita, a quali ruoli e verso quale stato.

## Alternatives

Nessuna riapertura; riapertura solo Manager; riapertura Administrator/Manager con tracciamento.

## Recommendation

Definire esplicitamente la policy prima di considerare completo il lifecycle.

## Affected Areas

Work Order Lifecycle Baseline, Work Order Management, History, Authorization.

## Classification Reason

È un’incertezza esplicita con impatto significativo sul dominio e non può essere inferita.

## Resolution

Unresolved.

## Changelog

- Revision 1: Initial Phase 1.1 materialization.

## Reasoning Readiness

NEEDS_MORE_REASONING

