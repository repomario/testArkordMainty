---
id: 'HISTORICAL-DATA-PRESERVATION'
type: 'hybrid-agile.specification'
title: 'Historical Data Preservation'
summary: 'Deactivate historically referenced entities instead of deleting them so past activity retains its integrity.'
status: 'PROPOSED'
relations: {}
metadata:
  revision: 1
  createdDuring: 'INITIALIZATION'
  lastUpdated: '2026-10-05T19:02:58.927Z'
---

# Historical Data Preservation

## Constraint

Entities relevant to historical records should be deactivated rather than deleted where historical references exist.

## Scope and Rationale

The rule applies when deleting a user, Facility, Asset, or other referenced entity would make past maintenance activity incomplete or misleading. Deactivation may restrict current use, but the identity and references necessary to interpret history must remain available.
