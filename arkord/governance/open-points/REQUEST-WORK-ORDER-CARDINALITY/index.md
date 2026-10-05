---
id: 'REQUEST-WORK-ORDER-CARDINALITY'
type: 'open-point'
title: 'Maintenance Request to Work Order Cardinality'
status: 'OPEN'
summary: 'It is unknown whether one Maintenance Request generates exactly one or multiple Work Orders.'
relations:
  relatedTo:
    - MAINTENANCE-REQUEST-MANAGEMENT
    - WORK-ORDER-MANAGEMENT
    - RELATIONAL-PERSISTENCE
metadata:
  revision: 1
  lastUpdated: 2026-10-05T00:00:00Z
  createdDuring: INITIAL_GOVERNANCE_MATERIALIZATION
---

# Maintenance Request to Work Order Cardinality

## Problem

It is unknown whether one Maintenance Request generates exactly one or multiple Work Orders.

## Source of Uncertainty

The approved project understanding identifies this decision as unresolved and provides no Human Owner resolution.

## Project Impact

The way reported problems are represented across planned and executed interventions remains undetermined.

## Technical Impact

The relational model, request-to-order workflows, and integrity validation must preserve this uncertainty.
