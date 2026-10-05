---
id: 'CLIENT-SERVER-ARCHITECTURE'
type: 'hybrid-agile.specification'
title: 'Client/Server HTTP Architecture'
summary: 'Separate frontend and backend through HTTP APIs, with business and data responsibilities governed by the backend.'
status: 'PROPOSED'
relations: {}
metadata:
  revision: 1
  createdDuring: 'INITIALIZATION'
  lastUpdated: '2026-10-05T19:02:58.927Z'
---

# Client/Server HTTP Architecture

## Constraint

The frontend and backend must be clearly separated and communicate through HTTP APIs. The backend governs business logic, authorization, validation, persistence, and state transitions.

## Scope and Rationale

The boundary applies to application operations initiated through the web interface. A client request is not authoritative until the backend has applied the relevant rules and accepted it.
