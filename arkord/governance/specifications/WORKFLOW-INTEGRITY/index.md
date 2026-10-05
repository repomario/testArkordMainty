---
id: 'WORKFLOW-INTEGRITY'
type: 'hybrid-agile.specification'
title: 'Work Order Workflow Integrity'
summary: 'Reject incompatible Work Order transitions and protect critical operations from inconsistent states.'
status: 'PROPOSED'
relations: {}
metadata:
  revision: 1
  createdDuring: 'INITIALIZATION'
  lastUpdated: '2026-10-05T19:02:58.927Z'
---

# Work Order Workflow Integrity

## Constraint

The backend must reject clearly incompatible Work Order state transitions and protect critical operations from inconsistent states.

## Scope and Rationale

The rule applies whenever an operation changes Work Order lifecycle state or depends on that state. Acceptance must be based on the authoritative persisted state so contradictory lifecycle outcomes are not recorded.
