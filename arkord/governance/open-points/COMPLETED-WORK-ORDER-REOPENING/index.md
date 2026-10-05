---
id: 'COMPLETED-WORK-ORDER-REOPENING'
type: 'open-point'
title: 'Completed Work Order Reopening'
status: 'OPEN'
summary: 'Whether a completed Work Order can be reopened, in which circumstances, and by which roles is unresolved.'
relations:
  relatedTo:
    - WORK-ORDER-MANAGEMENT
    - WORK-ORDER-STATE-INTEGRITY
    - AUDIT-IMMUTABILITY
metadata:
  revision: 1
  lastUpdated: 2026-10-05T00:00:00Z
  createdDuring: INITIAL_GOVERNANCE_MATERIALIZATION
---

# Completed Work Order Reopening

## Problem

Whether a completed Work Order can be reopened, in which circumstances, and by which roles is unresolved.

## Source of Uncertainty

The approved project understanding identifies this decision as unresolved and provides no Human Owner resolution.

## Project Impact

The operational lifecycle after completion and the roles able to alter it remain undetermined.

## Technical Impact

State-transition, authorization, history, and audit behavior cannot define a reopening path yet.
