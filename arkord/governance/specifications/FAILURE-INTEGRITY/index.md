---
id: 'FAILURE-INTEGRITY'
type: 'hybrid-agile.specification'
title: 'Failure and Data Integrity'
summary: 'Prevent errors from presenting unpersisted operations as complete and prevent silent loss of entered data during connectivity problems.'
status: 'PROPOSED'
relations: {}
metadata:
  revision: 1
  createdDuring: 'INITIALIZATION'
  lastUpdated: '2026-10-05T19:02:58.927Z'
---

# Failure and Data Integrity

## Constraint

Errors must not make unpersisted operations appear completed, and connectivity problems must not silently discard user-entered data.

## Scope and Rationale

The application must communicate whether an operation was accepted and preserve the user's ability to recognize or recover from failure. This requirement applies to failure handling and does not, by itself, require full offline capability or an offline-first architecture.
