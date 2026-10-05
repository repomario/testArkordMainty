---
id: 'APPLICATION-SECURITY'
type: 'specification'
title: 'Application Security'
status: 'PROPOSED'
summary: 'Protect credentials, APIs, uploads, and infrastructure secrets.'
relations: {}
metadata:
  revision: 1
  lastUpdated: 2026-10-05T00:00:00Z
  createdDuring: INITIAL_GOVERNANCE_MATERIALIZATION
---

# Application Security

## Rule

Passwords are never stored in plaintext. APIs verify authentication and authorization. Uploaded files are treated as untrusted input. Infrastructure secrets and credentials are not committed to the repository.
