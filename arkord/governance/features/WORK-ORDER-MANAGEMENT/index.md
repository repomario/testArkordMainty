---
id: 'WORK-ORDER-MANAGEMENT'
type: 'feature'
title: 'Work Order Management'
status: 'PROPOSED'
summary: 'Manage planned and executed maintenance interventions throughout their operational lifecycle.'
relations:
  governedBy:
    - RELATIONAL-PERSISTENCE
    - DATA-INTEGRITY-AND-ATOMICITY
    - WORK-ORDER-STATE-INTEGRITY
    - AUDIT-IMMUTABILITY
metadata:
  revision: 1
  lastUpdated: 2026-10-05T00:00:00Z
  createdDuring: INITIAL_GOVERNANCE_MATERIALIZATION
---

# Work Order Management

## Capability

A Work Order represents planned or executed maintenance work and records priority, status, scheduling, assignment, operational dates, and notes. Request cardinality, standalone creation, assignment cardinality, Technician authority, and completed-order reopening remain Open Points.
