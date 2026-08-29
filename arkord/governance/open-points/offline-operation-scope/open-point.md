---
{
  "nodeId": "offline-operation-scope",
  "nodeType": "OPEN_POINT",
  "title": "Offline Operation Scope",
  "status": "OPEN",
  "summary": "Non è definito se Mainty debba permettere operazioni durante interruzioni di rete.",
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

# Offline Operation Scope

## Problem

Non è definito se Mainty debba permettere operazioni durante interruzioni di rete.

## Source of Uncertainty

Il Brief riconosce connettività instabile ma non decide se offline faccia parte della prima versione.

## Project Impact

Può modificare significativamente l’esperienza Technician e lo scope della prima versione.

## Technical Impact

Può introdurre storage locale, sincronizzazione e gestione conflitti.

## Proposed Resolution

Decidere se la prima versione sia online-only con gestione esplicita degli errori oppure supporti un insieme definito di operazioni offline.

## Alternatives

Online-only; resilienza temporanea senza editing offline; subset offline; supporto offline più ampio.

## Recommendation

Non introdurre implicitamente offline finché non viene deciso il perimetro.

## Affected Areas

Work Execution, UI, Reliability, Architecture.

## Classification Reason

È un’incertezza esplicita con elevato impatto potenziale e non può essere trattata come semplice dettaglio implementativo.

## Resolution

Unresolved.

## Changelog

- Revision 1: Initial Phase 1.1 materialization.
