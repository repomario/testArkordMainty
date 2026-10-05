---
id: 'CREDENTIAL-SECURITY'
type: 'hybrid-agile.specification'
title: 'Credential and Secret Security'
summary: 'Protect passwords from plaintext storage and exclude passwords, secrets, and infrastructure credentials from the repository.'
status: 'PROPOSED'
relations: {}
metadata:
  revision: 1
  createdDuring: 'INITIALIZATION'
  lastUpdated: '2026-10-05T19:02:58.927Z'
---

# Credential and Secret Security

## Constraint

Passwords must never be stored in plaintext. Passwords, secrets, and infrastructure credentials must not be stored in the repository.

## Scope and Rationale

The rule applies to user credentials and operational or infrastructure secrets across application source, configuration, fixtures, and documentation. Protected handling is required to avoid exposing credentials through persistence or source history.
