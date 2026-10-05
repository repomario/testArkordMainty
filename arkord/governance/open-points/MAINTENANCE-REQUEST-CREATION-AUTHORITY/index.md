---
id: 'MAINTENANCE-REQUEST-CREATION-AUTHORITY'
type: 'open-point'
title: 'Maintenance Request Creation Authority'
status: 'OPEN'
summary: 'Which roles may create Maintenance Requests is not established.'
relations:
  relatedTo:
    - MAINTENANCE-REQUEST-MANAGEMENT
    - ROLE-BASED-AUTHORIZATION
metadata:
  revision: 1
  lastUpdated: 2026-10-05T00:00:00Z
  createdDuring: INITIAL_GOVERNANCE_MATERIALIZATION
---

# Maintenance Request Creation Authority

## Problem

Which roles may create Maintenance Requests is not established.

## Source of Uncertainty

The approved project understanding identifies this decision as unresolved and provides no Human Owner resolution.

## Project Impact

Request creation access affects how each role participates in problem reporting.

## Technical Impact

Backend authorization and role rules cannot finalize request-creation permissions until this is resolved.
