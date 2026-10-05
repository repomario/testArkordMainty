---
id: 'UNTRUSTED-UPLOADS'
type: 'hybrid-agile.specification'
title: 'Untrusted File Handling'
summary: 'Treat all user uploads as untrusted and prevent upload handling from compromising normal application use.'
status: 'PROPOSED'
relations: {}
metadata:
  revision: 1
  createdDuring: 'INITIALIZATION'
  lastUpdated: '2026-10-05T19:02:58.927Z'
---

# Untrusted File Handling

## Constraint

User-uploaded files must be treated as untrusted content. Accepting, storing, retrieving, or presenting an upload must not compromise normal application use.

## Scope and Rationale

The rule applies to photographic attachments and any other user-supplied files. Upload handling must preserve application security and availability regardless of a file's claimed type or content.
