---
id: 'AUDIT-SCOPE'
type: 'hybrid-agile.open-point'
title: 'Permanent Audit Scope'
summary: 'Which important operations require permanent audit recording.'
status: 'OPEN'
relations:
  relatedTo:
    - 'AUDITABILITY'
    - 'ACTIVITY-HISTORY'
metadata:
  revision: 1
  createdDuring: 'INITIALIZATION'
  lastUpdated: '2026-10-05T19:02:58.927Z'
---

# Permanent Audit Scope

## Problem

The operations important enough to require permanent audit recording have not been identified.

## Source of Uncertainty

Auditability requires actor, action, and time for important operations, but the approved proposal intentionally leaves the exact audit-event scope undecided.

## Project Impact

The uncertainty affects which operational actions users and stakeholders can expect to reconstruct permanently beyond ordinary activity history.

## Technical Impact

The set of events subject to protected audit capture, permanent retention, and non-modifiability cannot be delimited until the important operations are identified.
