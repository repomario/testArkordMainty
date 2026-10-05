---
id: 'BLUEPRINT'
type: 'blueprint'
title: 'Mainty Project Blueprint'
status: 'CURRENT'
summary: 'Centralized maintenance management for one organization’s Facilities and Assets.'
relations: {}
metadata:
  revision: 1
  lastUpdated: 2026-10-05T00:00:00Z
  createdDuring: INITIAL_GOVERNANCE_MATERIALIZATION
---

# Mainty Project Blueprint

## Purpose and goals

Mainty is a centralized web application for managing maintenance of the Facilities and Assets belonging to a single organization. Its goal is to give that organization one coherent operational record from the first report of a problem through planning, assignment, field execution, completion, history, and traceability.

## Users and responsibilities

- **Administrator:** administers users, access, and the managed operational structure, and can oversee maintenance operations.
- **Maintenance Manager:** plans, prioritizes, assigns, schedules, and monitors maintenance work.
- **Technician:** understands assigned work and performs field execution, including operational updates, notes, photographs, and completion records within authorized boundaries.

The precise creation and modification authorities that remain undecided are retained as Open Points rather than assumed here.

## Maintenance lifecycle

Problems are reported against a Facility and may also identify an Asset. Maintenance work is represented through Work Orders that can be planned, assigned, scheduled, executed, and completed. Comments, photographs, operational dates, and significant activity provide maintenance history and traceability. The allowed cardinality between reports and Work Orders, standalone Work Order creation, assignment cardinality, Technician authority, and reopening are not settled by this lifecycle description.

## V1 scope and boundaries

V1 consolidates authentication and roles; Facility and Asset management; Maintenance Requests and Work Orders; assignment and scheduling; Technician execution; comments, photographs, maintenance history, search, filtering, an operational dashboard, internal operational indications, and a responsive web interface. Facilities form the organization's managed physical structure, Assets belong to Facilities, Maintenance Requests concern Facilities and may concern Assets, and Work Orders represent planned or executed maintenance work.

V1 serves a single organization. It does not commit to suppliers or providers, spare-parts management, recurring preventive maintenance, external notification channels, offline operation, QR codes, integrations, advanced analytics, or native mobile applications. These may be considered in future evolution where identified in the Roadmap or an Open Point.

## System constraints

Mainty uses a separated frontend and backend communicating over HTTP APIs, with business rules, authorization, validation, persistence, and state transitions enforced by the backend. Structured operational data is relationally persisted in PostgreSQL. The system preserves relational and historical integrity, applies atomic and truthful persistence behavior to principal operations, and supports paginated access to potentially large collections.

Authentication is mandatory, role authorization cannot rely on the interface alone, deactivated users cannot access the system, passwords are not stored in plaintext, uploads are untrusted input, and secrets are excluded from the repository. Audit-relevant activity identifies user, action, and time and cannot be edited through normal functionality; its permanent scope remains open.

The responsive interface supports desktop, tablet, and smartphone use, with desktop-oriented administration and planning and simple field use for Technicians. Architectural choices must remain compatible with a possible future evolution to multiple organizations, without introducing multi-organization functionality into V1.
