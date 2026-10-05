---
id: 'WORK-ORDER-MANAGEMENT'
type: 'hybrid-agile.feature'
title: 'Work Order Management'
summary: 'Creation and management of maintenance interventions with operational data, priority, status, subject, and request linkage where applicable.'
status: 'PROPOSED'
relations: {}
metadata:
  revision: 1
  createdDuring: 'INITIALIZATION'
  lastUpdated: '2026-10-05T19:02:58.927Z'
---

# Work Order Management

## Capability

Mainty represents planned or active maintenance interventions as Work Orders and supports their operational lifecycle.

## Functional Scope

A Work Order includes relevant operational data, priority, status, and a Facility or Asset association. It may link to a Maintenance Request when the intervention originates from one.

## Boundaries and Rules

A Work Order's state must reflect its operational progress. A Maintenance Request linkage is required only where applicable and must remain traceable once established.
