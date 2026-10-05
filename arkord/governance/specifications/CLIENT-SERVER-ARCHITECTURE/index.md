---
id: 'CLIENT-SERVER-ARCHITECTURE'
type: 'specification'
title: 'Client/Server HTTP API Architecture'
status: 'PROPOSED'
summary: 'Separate frontend and backend behind HTTP APIs.'
relations: {}
metadata:
  revision: 1
  lastUpdated: 2026-10-05T00:00:00Z
  createdDuring: INITIAL_GOVERNANCE_MATERIALIZATION
---

# Client/Server HTTP API Architecture

## Rule

The frontend and backend are separate and communicate through HTTP APIs. The backend owns business logic, authorization, validation, persistence, and state transitions.
