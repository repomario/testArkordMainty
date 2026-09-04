---
nodeId: authentication-and-user-access
nodeType: FEATURE
title: Authentication and User Access
status: APPROVED
summary: Accesso autenticato e gestione dell’identità applicativa.
relations:
  updatedBy: [
    ]
  governedBy:
  - backend-authorization-enforcement
  - responsive-role-oriented-web-ui
  - relational-persistence
  - secure-credential-and-upload-handling
  - honest-operation-failure-feedback
  relatedTo: [
    ]
metadata:
  revision: 1
  createdDuring: PHASE-1-1-PROJECT-INITIALIZATION
  lastUpdated: '2026-08-29T00:00:00Z'
---

# Authentication and User Access

## Purpose

Consentire accesso controllato agli utenti Mainty.

## Functional Scope

Login, utenti attivi/disattivati e associazione del ruolo.

## Out of Scope

Google, Microsoft e SSO aziendale nella prima versione.

## Functional Rules

Gli utenti disattivati non possono accedere; i dati storici restano conservati.

## Related Governance

Governata dalle specifiche di autenticazione, autorizzazione e sicurezza.

## Expected Delivery Derivation

Flussi di autenticazione e gestione della sessione/accesso.

## Classification Reason

È una capacità funzionale stabile offerta dal sistema, mentre le regole di sicurezza che la governano appartengono alle Specification.

## Changelog

- Revision 1: Initial Phase 1.1 materialization.
