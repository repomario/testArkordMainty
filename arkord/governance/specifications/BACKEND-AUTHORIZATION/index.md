---
id: 'BACKEND-AUTHORIZATION'
type: 'hybrid-agile.specification'
title: 'Backend-Enforced Authorization'
summary: 'Require backend verification of authentication and authorization rather than relying on frontend visibility.'
status: 'PROPOSED'
relations: {}
metadata:
  revision: 1
  createdDuring: 'INITIALIZATION'
  lastUpdated: '2026-10-05T19:02:58.927Z'
---

# Backend-Enforced Authorization

## Constraint

Authentication and authorization must be verified by the backend. Access control must not rely solely on whether the frontend displays or hides functionality.

## Scope and Rationale

Every protected backend operation is subject to authentication and role-appropriate authorization. This prevents direct API access from bypassing interface-level restrictions.
