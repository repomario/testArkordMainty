You are the Arkord Execution Agent/Codex operating on the selected Project Repository for project “Mainty test”.

Materialize the approved Governance Proposal described below. This is a repository mutation task, not a reasoning or approval task. Do not create Delivery artifacts or implementation work. Write Governance only under `arkord/governance/`.

The repository is the source of truth. Follow the canonical Hybrid Agile artifact contracts exactly. Preserve unresolved uncertainty as Open Points; do not invent missing decisions, requirements, implementation choices, relationships, or facts. The Human Owner retains authority over unresolved decisions. Testo incollato

Create the following canonical Governance structure:

- `arkord/governance/blueprint/index.md`
- `arkord/governance/roadmap/index.md`
- one `index.md` per Feature under `arkord/governance/features/<feature-id>/`
- one `index.md` per Specification under `arkord/governance/specifications/<specification-id>/`
- one `index.md` per Open Point under `arkord/governance/open-points/<open-point-id>/`

For every created document:
- write `metadata.revision: 1`;
- write `metadata.createdDuring: 'INITIALIZATION'`;
- write `metadata.lastUpdated` as the actual execution-time UTC ISO-8601 instant accepted by Java `Instant.parse`;
- use only the supported frontmatter fields and relations;
- do not invent alternative `type`, lifecycle/status, metadata, or relation values.

BLUEPRINT

Create `arkord/governance/blueprint/index.md` with exactly these protocol values:

- `id: 'BLUEPRINT'`
- `type: 'hybrid-agile.blueprint'`
- `status: 'ACTIVE'`
- `relations: {}`
- `metadata.revision: 1`
- `metadata.createdDuring: 'INITIALIZATION'`

Choose a project-specific title and concise summary faithful to the proposal.

The body must establish Mainty as a centralized maintenance-management web application replacing fragmented management through messages, spreadsheets, and informal communications.

Represent the established project understanding:
- V1 serves a single organization.
- Primary roles are Administrator, Maintenance Manager, and Technician.
- V1 covers authentication and authorization, Facility and Asset master data, Maintenance Requests, Work Orders, technician assignment and basic scheduling, field execution, attachments/comments, search/filtering, operational dashboard, notifications within the application, and maintenance history.
- The system is a responsive web application.
- Frontend and backend are separated and communicate through HTTP APIs.
- PostgreSQL is the relational persistence technology.
- Backend owns business logic, authorization, validation, persistence, and state transitions.
- Technician workflows require particular attention to simple and efficient mobile usage.
- Architecture must avoid unnecessarily blocking a future multi-organization evolution, but multi-tenancy is not a V1 functional requirement.

Explicitly distinguish current V1 scope from non-binding future possibilities including multi-organization support, suppliers, spare parts/inventory, preventive maintenance, external notifications, offline capabilities, QR codes, integrations, and advanced analytics.

Do not turn the Blueprint into detailed Specifications, Delivery planning, implementation tasks, or a duplication of every Governance artifact.

ROADMAP

Create `arkord/governance/roadmap/index.md` with exactly:

- `id: 'ROADMAP'`
- `type: 'hybrid-agile.roadmap'`
- `status: 'ACTIVE'`
- `relations: {}`
- `metadata.revision: 1`
- `metadata.createdDuring: 'INITIALIZATION'`

Choose an appropriate project-specific title and concise summary.

Express the V1 evolution through meaningful high-level milestones, covering:
1. access foundations and core master data;
2. Maintenance Request and Work Order management;
3. technician assignment, basic scheduling, field execution, and operational collaboration;
4. activity history, search/filtering, dashboard, notifications, and operational visibility;
5. responsive usability and V1 hardening across the established capabilities.

Represent multi-organization support, suppliers, spare parts, preventive maintenance, external notifications, offline support, QR codes, integrations, and advanced analytics only as possible future evolution, not committed V1 work.

Do not create Stories, Tasks, Bugs, Sprint assignments, estimates, assignees, implementation details, or other Delivery planning.

FEATURES

Create the following Feature documents under `arkord/governance/features/<feature-id>/index.md`.

Every Feature must use:
- its supplied stable ID;
- `type: 'hybrid-agile.feature'`;
- `status: 'PROPOSED'`;
- its supplied title;
- a concise summary faithful to the supplied summary;
- `metadata.revision: 1`;
- `metadata.createdDuring: 'INITIALIZATION'`.

Use `relations.governedBy` only where the relationship is directly supported by the approved proposal and can be established without inventing semantics. Otherwise use `relations: {}`. Never write `updatedBy` during initialization.

Create:

1. `AUTHENTICATION-ACCESS` — Authentication and Role-Based Access  
Authentication of users, active/inactive user state, and access to functionality according to Administrator, Maintenance Manager, and Technician roles.

2. `USER-MANAGEMENT` — User and Role Management  
Administrator management of users and role assignment while preserving historical references for deactivated users.

3. `FACILITY-MANAGEMENT` — Facility Management  
Creation, modification, consultation, and deactivation of managed physical facilities.

4. `ASSET-MANAGEMENT` — Asset Management  
Registration and management of Assets associated with Facilities, including identification, location, state, and maintenance-history consultation.

5. `MAINTENANCE-REQUESTS` — Maintenance Requests  
Reporting problems concerning Facilities or Assets with description, priority, status, and photographs.

6. `WORK-ORDER-MANAGEMENT` — Work Order Management  
Creation and management of maintenance interventions including operational data, priority, status, Facility/Asset association, and Maintenance Request linkage where applicable.

7. `ASSIGNMENT-SCHEDULING` — Technician Assignment and Basic Scheduling  
Assignment of Work Orders to Technicians, planned date, and operational views emphasizing assigned work, priority, today’s activities, and overdue work.

8. `WORK-EXECUTION` — Maintenance Work Execution  
Technician support for starting, updating, and completing interventions, including notes, photographs, Asset information, and recording performed work.

9. `ACTIVITY-HISTORY` — Maintenance Activity History  
Tracking significant Work Order operations and consulting intervention history while preserving relevant information over time.

10. `ATTACHMENTS-COMMENTS` — Attachments and Operational Comments  
Management of photographs, comments, and notes associated with Maintenance Requests and Work Orders during the operational lifecycle.

11. `WORK-ORDER-SEARCH` — Work Order Search and Filtering  
Text search and combinable filters for status, priority, Technician, Facility, Asset, and time interval.

12. `OPERATIONS-DASHBOARD` — Operational Maintenance Dashboard  
Operational dashboard for Administrator and Maintenance Manager showing indicators for open, in-progress, completed, Critical, and overdue Work Orders.

13. `IN-APP-NOTIFICATIONS` — Operational Notifications  
In-application visibility of new assignments, significant Work Order changes, and Critical situations.

Feature bodies must describe stable functional capability, functional scope, relevant boundaries, and intrinsic functional rules only. Do not add implementation details, scheduling, priority metadata, estimates, assignees, or Delivery work.

SPECIFICATIONS

Create the following Specification documents under `arkord/governance/specifications/<specification-id>/index.md`.

Every Specification must use:
- supplied stable ID;
- `type: 'hybrid-agile.specification'`;
- `status: 'PROPOSED'`;
- supplied title;
- concise summary faithful to the proposal;
- `relations: {}`;
- `metadata.revision: 1`;
- `metadata.createdDuring: 'INITIALIZATION'`.

Never persist `governs` and never write `updatedBy` during initialization.

Create:

1. `RELATIONAL-PERSISTENCE` — Relational Data Persistence  
Primary structured data must be persisted in PostgreSQL while preserving relational integrity among users, Facilities, Assets, Maintenance Requests, and Work Orders.

2. `CLIENT-SERVER-ARCHITECTURE` — Client/Server HTTP Architecture  
Frontend and backend must be clearly separated and communicate through HTTP APIs. Backend governs business logic, authorization, validation, persistence, and state transitions.

3. `BACKEND-AUTHORIZATION` — Backend-Enforced Authorization  
Authentication and authorization must be verified by the backend and must not rely solely on frontend feature visibility.

4. `CREDENTIAL-SECURITY` — Credential and Secret Security  
Passwords must never be stored in plaintext. Passwords, secrets, and infrastructure credentials must not be stored in the repository.

5. `UNTRUSTED-UPLOADS` — Untrusted File Handling  
User-uploaded files must be treated as untrusted content and upload handling must not compromise normal application use.

6. `HISTORICAL-DATA-PRESERVATION` — Historical Data Preservation  
Entities relevant to historical records should be deactivated rather than deleted where historical references exist, preserving past activity integrity.

7. `WORKFLOW-INTEGRITY` — Work Order Workflow Integrity  
Backend must reject clearly incompatible Work Order state transitions and protect critical operations from inconsistent states.

8. `AUDITABILITY` — Operational Auditability  
For important operations the system must be able to determine actor, action, and time. Audit information must not be modifiable through normal application functionality. Do not invent which exact operations require permanent audit; that remains an Open Point.

9. `RESPONSIVE-UI` — Responsive Web Interface  
Interface must adapt to desktop, tablet, and smartphone, prioritizing desktop for administrative functionality and simple, fast mobile use for Technicians.

10. `FAILURE-INTEGRITY` — Failure and Data Integrity  
Errors must not make unpersisted operations appear completed, and connectivity problems must not silently discard user-entered data. Do not infer full offline capability from this requirement.

11. `SCALABLE-LIST-ACCESS` — Scalable Operational Lists  
Potentially large lists such as Work Orders and historical records must be retrievable without requiring the entire dataset to be loaded in one request.

Each Specification body must express the stable enforceable rule or constraint, scope, relevant rationale, and conditions necessary to interpret it. Do not add tasks or implementation planning.

OPEN POINTS

Create the following Open Points under `arkord/governance/open-points/<open-point-id>/index.md`.

Every Open Point must use:
- supplied stable ID;
- `type: 'hybrid-agile.open-point'`;
- `status: 'OPEN'`;
- supplied title;
- concise unresolved-question summary;
- `metadata.revision: 1`;
- `metadata.createdDuring: 'INITIALIZATION'`.

Each body must contain exactly the required analytical structure:

`# <title>`

`## Problem`

`## Source of Uncertainty`

`## Project Impact`

`## Technical Impact`

Do not put resolution proposals, recommendations, alternatives, reasoning conversations, execution handoffs, ownership, priority, scheduling, or invented decisions into these sections.

Use `relations.relatedTo` only with existing Governance document IDs and only where the relationship is directly supported by the proposal. Multiple existing Governance IDs may be used where clearly appropriate. Do not invent relationships merely to populate the field.

Create:

1. `WORK-ORDER-REOPENING` — Completed Work Order Reopening Policy  
Unresolved: whether completed Work Orders can exceptionally be reopened, which roles may do so, and which transitions are allowed. Analyze impact on Work Order lifecycle, operational history, authorization, auditability, and workflow integrity without deciding the policy.

2. `ATTACHMENT-POLICY` — Attachment Limits and Retention  
Unresolved: maximum file size, maximum number of attachments, supported formats, and retention policy for photographic attachments. Analyze functional/storage/security/operational consequences without choosing values.

3. `EXTERNAL-NOTIFICATIONS` — V1 External Notification Scope  
Unresolved: whether V1 includes email/push notifications or remains limited to in-app notifications. Preserve external notifications as undecided; do not silently promote them into V1 scope.

4. `OFFLINE-SUPPORT` — V1 Offline and Unstable Connectivity Support  
Unresolved: whether and to what extent V1 supports operations during temporary connectivity interruptions. Preserve the established `FAILURE-INTEGRITY` requirement that entered data must not be silently lost, but do not interpret it as approval for an offline-first architecture.

5. `BACKEND-TECHNOLOGY` — Backend Technology Selection  
Unresolved: the specific backend technology/framework. Preserve the established client/server HTTP boundary, PostgreSQL persistence, and backend responsibilities while leaving the concrete backend technology undecided.

6. `PERFORMANCE-TARGETS` — Performance Volumes and Targets  
Unresolved: realistic/maximum data volumes, quantitative response-time targets, and whether formal SLAs are required. Do not invent thresholds.

7. `AUDIT-SCOPE` — Permanent Audit Scope  
Unresolved: which operations are important enough to require permanent audit recording. Preserve the established auditability constraint while leaving the exact audit-event scope undecided.

8. `FUTURE-MULTI-ORGANIZATION-BOUNDARY` — Multi-Organization Architectural Boundary  
Unresolved: which V1 architectural constraints are required to avoid blocking future multi-organization evolution without prematurely introducing multi-tenancy as a current functional requirement. Do not design or require multi-tenancy in V1.

For all Open Points, distinguish Project Impact from Technical Impact independently. An impact dimension may be limited if the approved proposal does not support stronger claims. Do not invent facts to make either section longer.

MATERIALIZATION CONSTRAINTS

Before finishing:
- verify every Governance document is under `arkord/governance/`;
- verify no Delivery or implementation artifact was created;
- verify Blueprint and Roadmap use `status: 'ACTIVE'`;
- verify every Feature and Specification uses `status: 'PROPOSED'`;
- verify every Open Point uses `status: 'OPEN'`;
- verify every document uses `metadata.revision: 1`;
- verify every document uses `metadata.createdDuring: 'INITIALIZATION'`;
- verify every `metadata.lastUpdated` is a valid UTC ISO-8601 instant parseable by `Instant.parse`;
- verify no initialization document contains `updatedBy`;
- verify Specifications do not persist `governs`;
- verify all `governedBy` and `relatedTo` references, if any, point only to Governance IDs created by this materialization and are supported by the approved proposal;
- verify Open Point bodies contain the required Problem, Source of Uncertainty, Project Impact, and Technical Impact sections;
- verify no unresolved question has been silently converted into an architectural or product decision;
- verify no unsupported frontmatter fields or relations were added.

Perform the repository mutation directly and report the files created or updated and any validation failure encountered.