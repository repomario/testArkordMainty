---
id: 'AUTHENTICATION-ACCESS'
type: 'hybrid-agile.feature'
title: 'Authentication and Role-Based Access'
summary: 'Authentication of users, active or inactive user state, and role-appropriate access for Administrators, Maintenance Managers, and Technicians.'
status: 'PROPOSED'
relations: {}
metadata:
  revision: 1
  createdDuring: 'INITIALIZATION'
  lastUpdated: '2026-10-05T19:02:58.927Z'
---

# Authentication and Role-Based Access

## Capability

Mainty authenticates users and restricts functionality according to the Administrator, Maintenance Manager, and Technician roles.

## Functional Scope

The capability covers user sign-in, recognition of active and inactive user state, and role-based access to available functions.

## Boundaries and Rules

Only active, authenticated users may access protected functionality. Access is determined by the user's assigned role; hiding a function in the interface is not a substitute for enforcing access.
