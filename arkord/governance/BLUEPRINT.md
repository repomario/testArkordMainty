---
{
  "nodeId": "mainty-blueprint",
  "nodeType": "BLUEPRINT",
  "title": "Mainty Project Blueprint",
  "summary": "Identità, obiettivi, ambito e direzione architetturale approvati per Mainty.",
  "relations": {
    "updatedBy": [],
    "relatedTo": []
  },
  "metadata": {
    "revision": 1,
    "createdDuring": "PHASE-1-1-PROJECT-INITIALIZATION",
    "lastUpdated": "2026-08-29T00:00:00Z"
  }
}
---

# Mainty Project Blueprint

## Project Identity

Mainty è una web application per la gestione centralizzata della manutenzione di Facility e Asset di una singola organizzazione.

Project ID: `a900660b-19ba-48da-b0c6-1f0491e963e1`.

## Purpose

Gestire l’intero flusso operativo dalla segnalazione di un problema alla pianificazione, assegnazione, esecuzione e storicizzazione dell’intervento.

## Goals

- Centralizzazione delle attività di manutenzione.
- Tracciabilità del lavoro.
- Coordinamento tra ruoli gestionali e Technician.
- Conservazione dello storico.
- Accesso rapido alle informazioni operative.
- Esperienza adeguata sia alla gestione desktop sia al lavoro sul campo.

## Scope

Autenticazione, utenti e ruoli, Facility, Asset, Maintenance Request, Work Order, assegnazioni, esecuzione, commenti, fotografie, ricerca, filtri, dashboard, notifiche applicative e storico.

## Exclusions

Multi-organizzazione, offline completo, notifiche esterne e altre evoluzioni future non sono automaticamente incluse nello scope corrente.

## Target Users and Stakeholders

Administrator, Maintenance Manager e Technician di una singola organizzazione.

## Major Capabilities

Autenticazione e amministrazione degli accessi; gestione Facility e Asset; Maintenance Request; Work Order, assegnazione ed esecuzione; commenti, fotografie e storico; ricerca, filtri, dashboard e notifiche applicative.

## Principal Constraints

Web application client/server, API HTTP, PostgreSQL, autenticazione, autorizzazione backend, conservazione dei dati storici e responsive UI.

## Architectural Direction

Frontend e backend separati; backend responsabile delle regole applicative e della persistenza; database relazionale PostgreSQL.

## Related Governance

Le Feature, Specification, Decision e Open Point materializzate durante `PHASE-1-1-PROJECT-INITIALIZATION` dettagliano le capacità, i vincoli, le decisioni e le incertezze approvate.

## Notes

L’evolution boundary impedisce di trattare automaticamente come scope corrente multi-organizzazione, offline completo, notifiche esterne e altre evoluzioni future.
