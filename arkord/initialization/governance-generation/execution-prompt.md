Materialize the approved Mainty Governance Proposal into the selected Project Repository.
Operate only under arkord/governance/. Do not create Delivery artifacts, implementation tasks, Stories, Sprints, estimates, assignments, executable implementation plans, or files outside Governance.
Treat the repository as the authoritative source of current project knowledge. Before writing, inspect any existing Governance documents at the canonical paths below. Preserve existing logical artifact identifiers and canonical paths when updating an existing artifact. Do not create duplicate Governance artifacts for the same logical item. Governance mutation is forward-only; do not use rollback, snapshot restoration, historical-version selection, or Git history as mutation semantics.
Create or update the following Governance:
1. Blueprint at arkord/governance/blueprint/index.md.
2. Roadmap at arkord/governance/roadmap/index.md.
3. Features at arkord/governance/features/<feature-id>/index.md.
4. Specifications at arkord/governance/specifications/<specification-id>/index.md.
5. Open Points at arkord/governance/open-points/<open-point-id>/index.md.
Use the native Arkord Document frontmatter required by the corresponding methodology templates: id, type, title, status, summary, relations, and metadata. Preserve existing valid metadata where appropriate. Arkord owns metadata.revision and metadata.lastUpdated; methodology metadata includes createdDuring. New logical Governance items start at revision 1. Increment an existing logical item's revision exactly once only when this execution materially changes that item.
For newly created or materially changed Features and Specifications, use lifecycle status PROPOSED. Do not mark them APPROVED: approval is exclusively a Human Owner action. Blueprint and Roadmap have no approval lifecycle. Open Points use lifecycle OPEN unless authoritative current repository knowledge already establishes an explicit Human Owner resolution that must be preserved. Do not infer approval, review, or resolution from this execution.
Do not persist READ/UNREAD or reviewState in Governance Markdown. Human Owner logical-revision review is Platform metadata.
Use only relationships supported by the current methodology. Feature supports updatedBy and governedBy. Specification supports updatedBy; do not persist an inverse governs. Blueprint and Roadmap support updatedBy when applicable. Open Point supports relatedTo. Do not introduce resolves or resolvedBy.
The approved project understanding is:
Mainty is a web application for centralizing maintenance management for Facilities and Assets belonging to a single organization. V1 covers the operational cycle from reporting a problem through planning, assignment, execution, history, and traceability. Administrator, Maintenance Manager, and Technician have different responsibilities. The architecture must remain compatible with a possible future multi-organization evolution, but multi-organization support is not a V1 requirement.
BLUEPRINT
Create or update the Blueprint so that it expresses Mainty as the centralized maintenance-management system described above. Cover, using semantic Markdown organization rather than mechanically imposed sections where unnecessary:
- project purpose and goals;
- intended users and the Administrator, Maintenance Manager, and Technician roles;
- the main maintenance lifecycle;
- V1 scope and boundaries;
- explicit exclusions and future possibilities;
- established architectural, persistence, security, integrity, and responsive-interface constraints at the appropriate high level;
- the requirement that architectural choices remain compatible with a possible future multi-organization evolution without treating multi-organization functionality as current scope.
Do not duplicate detailed Feature or Specification content in the Blueprint and do not invent unresolved decisions.
ROADMAP
Create or update the Roadmap as a high-level Governance evolution plan, not an implementation backlog.
Represent V1 as consolidation of the operational core covering:
- authentication and roles;
- Facility management;
- Asset management;
- Maintenance Requests;
- Work Orders;
- assignment and scheduling;
- Technician execution;
- comments, photographs, and maintenance history;
- Work Order search and filtering;
- operational dashboard;
- responsive web interface.
Record separately as possible future evolution, not V1 commitments:
- multi-organization support;
- suppliers/providers;
- spare-parts management;
- recurring preventive maintenance;
- external notifications;
- offline capabilities;
- QR codes;
- integrations;
- advanced analytics.
Do not add Stories, Tasks, Sprint assignments, estimates, assignees, implementation details, or other Delivery planning.
FEATURES
Create or update these Feature documents, preserving the IDs exactly:
USER-AND-ACCESS-MANAGEMENT — User and Access Management
Manage authentication, users, active/inactive status, and Administrator, Maintenance Manager, and Technician roles, with functional access consistent with their responsibilities.
FACILITY-MANAGEMENT — Facility Management
Manage the organization's physical Facilities, including identifying information, address, description, status, and preservation of historical information for inactive Facilities.
ASSET-MANAGEMENT — Asset Management
Register and manage Assets belonging to Facilities, including identification, location, status, descriptive data, and access to maintenance history.
MAINTENANCE-REQUEST-MANAGEMENT — Maintenance Request Management
Create and manage problem reports concerning Facilities and optionally Assets, including priority, status, author, and photographs.
WORK-ORDER-MANAGEMENT — Work Order Management
Manage planned and executed maintenance interventions, including priority, status, scheduling, assignment, operational dates, and notes.
WORK-ASSIGNMENT-AND-SCHEDULING — Work Assignment and Scheduling
Support Maintenance Managers in assigning and scheduling Work Orders and Technicians in understanding their assigned work, priorities, today's activities, and overdue work.
TECHNICIAN-WORK-EXECUTION — Technician Work Execution
Support field execution of maintenance work, including starting work, consulting relevant information, adding notes and photographs, and recording completion and work performed.
MAINTENANCE-ACTIVITY-HISTORY — Maintenance Activity History
Allow consultation and reconstruction of significant Work Order activity and maintenance history associated with Assets.
ATTACHMENT-MANAGEMENT — Attachment Management
Support uploading and managing photographs associated with Maintenance Requests and Work Orders, particularly from mobile devices.
WORK-ORDER-SEARCH-AND-FILTERING — Work Order Search and Filtering
Provide text search and combinable filtering of Work Orders by status, priority, Technician, Facility, Asset, and time interval.
MAINTENANCE-DASHBOARD — Maintenance Dashboard
Provide Administrator and Maintenance Manager with a concise operational dashboard covering open, in-progress, completed, Critical, and overdue Work Orders.
OPERATIONAL-NOTIFICATIONS — Operational Notifications
Provide clear in-application indication of new assignments, important Work Order conditions, and Critical interventions requiring attention.
Features must describe stable functional capabilities, not implementation mechanisms. Do not add Delivery fields such as Priority, Sprint, Assignee, Estimate, Due Date, or implementation details.
SPECIFICATIONS
Create or update these Specification documents, preserving the IDs exactly:
ROLE-BASED-AUTHORIZATION — Role-Based Authorization
Authentication is mandatory. Authorization must also be enforced by the backend. Deactivated users cannot access the system. Access restrictions must not depend only on the UI.
HISTORICAL-DATA-PRESERVATION — Historical Data Preservation
Users, Facilities, Assets, and maintenance data with historical references must be preserved coherently. Where appropriate, deactivation must be preferred to permanent deletion.
RELATIONAL-PERSISTENCE — Relational Persistence Model
Primary structured data must use PostgreSQL and preserve relational integrity among users, Facilities, Assets, Maintenance Requests, and Work Orders.
CLIENT-SERVER-ARCHITECTURE — Client/Server HTTP API Architecture
Frontend and backend must be separated and communicate through HTTP APIs. The backend is responsible for business logic, authorization, validation, persistence, and state transitions.
APPLICATION-SECURITY — Application Security
Passwords must not be stored in plaintext. APIs must verify authentication and authorization. Uploaded files must be treated as untrusted input. Infrastructure secrets and credentials must not be committed to the repository.
DATA-INTEGRITY-AND-ATOMICITY — Data Integrity and Operation Consistency
Principal operations, including assignments, Work Order transitions, Asset-Facility associations, and history changes, must not leave the system in an inconsistent state or falsely report persistence that did not occur.
RESPONSIVE-WEB-INTERFACE — Responsive Web Interface
The UI must support desktop, tablet, and smartphone. Administrator and Maintenance Manager usage is primarily desktop-oriented, while Technician interaction must remain simple and effective in the field. A native mobile application is not required for V1.
WORK-ORDER-STATE-INTEGRITY — Work Order State Integrity
Work Order state transitions must be validated by the system to prevent transitions incompatible with the normal operational lifecycle. Reopening exceptions remain unresolved and must be represented by the corresponding Open Point rather than invented here.
PAGINATED-LARGE-DATA-ACCESS — Large Dataset Access
Potentially large collections, including Work Orders and maintenance history, must not require loading the entire dataset in a single request.
AUDIT-IMMUTABILITY — Audit Immutability
Operations subject to audit must allow determination of the user, action, and time, and their audit data must not be editable through normal application functionality. The exact permanent audit scope remains unresolved and belongs to the corresponding Open Point.
Specifications must remain stable enforceable rules, constraints, standards, models, or contracts. They must remain meaningful independently of any single Feature and must not contain Delivery planning.
Where a Feature is clearly governed by one or more of these Specifications based on the approved proposal, materialize appropriate Feature.relations.governedBy edges. Do not invent relationships that are not semantically supported.
OPEN POINTS
Create or update these Open Points with status OPEN, preserving IDs exactly:
MAINTENANCE-REQUEST-CREATION-AUTHORITY — Maintenance Request Creation Authority
Determine which roles may create Maintenance Requests.
REQUEST-WORK-ORDER-CARDINALITY — Maintenance Request to Work Order Cardinality
Determine whether one Maintenance Request can generate exactly one Work Order or multiple Work Orders.
STANDALONE-WORK-ORDER-CREATION — Standalone Work Order Creation
Determine whether a Work Order may be created without an originating Maintenance Request.
WORK-ORDER-TECHNICIAN-CARDINALITY — Work Order Technician Assignment Cardinality
Determine whether a Work Order can be assigned to one Technician or multiple Technicians.
TECHNICIAN-WORK-ORDER-AUTHORITY — Technician Work Order Authority
Determine precisely which Work Order fields and state transitions a Technician may modify beyond operational execution, notes, photographs, and completion.
COMPLETED-WORK-ORDER-REOPENING — Completed Work Order Reopening
Determine whether a completed Work Order may be reopened, under what circumstances, and by which roles.
ATTACHMENT-POLICY — Attachment Policy
Determine maximum attachment size, maximum number of attachments, supported formats, and retention policy.
EXTERNAL-NOTIFICATION-SCOPE — External Notification Scope
Determine whether V1 includes external notifications and, if so, which channels are supported. Internal in-application notifications remain required.
OFFLINE-SUPPORT-SCOPE — Offline Support Scope
Determine whether and to what extent support for brief connectivity interruptions is a V1 requirement.
PERMANENT-AUDIT-SCOPE — Permanent Audit Scope
Determine which operations must be permanently recorded in the audit trail.
PERFORMANCE-TARGETS — Quantitative Performance Targets
Determine, when needed, expected volumes, quantitative response objectives, and other measurable performance criteria.
Each Open Point index.md must use the required persisted analytical structure:
<Open Point title>
Problem
Source of Uncertainty
Project Impact
Technical Impact
Populate these sections only from the approved proposal and consequences that can be safely derived from it. Clearly express both impact dimensions independently. Do not invent a resolution, preferred alternative, numerical threshold, authority rule, cardinality, attachment limit, notification channel, offline behavior, audit scope, or performance target.
Do not place alternatives, recommendations, resolution proposals, reasoning conversation, closure-readiness state, or execution handoffs inside these four analytical sections.
Where supported by the proposal, use relatedTo to connect Open Points to relevant Governance Documents. Do not use relationships to imply resolution.
Do not create conversation.md, resolution-proposal.json, or execution-prompt.md merely to fill the Open Point directory. Those resources exist only when their corresponding workflow produces them.
CONSISTENCY AND MATERIALIZATION RULES
Ensure the resulting Governance is internally coherent:
- Facilities belong to the organization's managed physical structure.
- Assets belong to Facilities.
- Maintenance Requests concern Facilities and may concern Assets.
- Work Orders represent planned/executed maintenance work.
- Do not settle the unresolved relationship cardinalities represented by Open Points.
- Do not settle unresolved Technician authority.
- Do not define completed Work Order reopening behavior.
- Do not invent attachment limits or formats.
- Keep external notifications and offline support unresolved for V1 while preserving required internal operational notifications.
- Do not invent permanent audit coverage beyond the established audit constraints.
- Do not invent quantitative performance targets.
- Keep multi-organization support as architectural future compatibility/evolution, not V1 functionality.
Preserve meaningful uncertainty rather than filling gaps with assumptions. When the approved proposal does not support a detail, omit it or represent it through the specified Open Point instead of inventing it.
Perform the repository mutation directly after inspecting current Governance and applying these instructions. The result must be a coherent initial/current Governance representation suitable for subsequent Human Owner review and Phase 2 Governance consolidation. Do not treat successful materialization as Human Owner approval, Delivery Readiness, or authorization to begin Delivery.