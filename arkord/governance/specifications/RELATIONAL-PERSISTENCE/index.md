---
id: 'RELATIONAL-PERSISTENCE'
type: 'hybrid-agile.specification'
title: 'Relational Data Persistence'
summary: 'Persist primary structured data in PostgreSQL with relational integrity across core maintenance entities.'
status: 'PROPOSED'
relations: {}
metadata:
  revision: 1
  createdDuring: 'INITIALIZATION'
  lastUpdated: '2026-10-05T19:02:58.927Z'
---

# Relational Data Persistence

## Constraint

Primary structured data must be persisted in PostgreSQL. Relational integrity must be preserved among users, Facilities, Assets, Maintenance Requests, and Work Orders.

## Scope and Rationale

This applies to the core operational records and their associations. Consistent relational references are necessary so current operations and historical maintenance records remain interpretable.
