# Clinic Appointments - Implementation Plan

## 1. Source Artifacts

- Architecture document: `../03-architectural-documentation/architecture-document.md`
- Design decisions: `../02-architectural-design/design-decisions.md`
- Traceability matrix: Architecture document section 11.
- Scrum handoff: Architecture document section 10.

## 2. Stack And Libraries

| Area | Choice | Constraint |
| --- | --- | --- |
| Frontend | Browser web app | Follow `design-system.md`; support patient and staff flows. |
| Backend | API service | Booking consistency enforced server-side. |
| Database | Relational DB | Unique slot key is mandatory. |
| Notifications | Email/SMS provider adapter | Calls run through outbox worker. |
| Tests | Unit + integration tests | Include duplicate booking and auth tests. |
| Observability | Logs/metrics | Failed booking and notification attempts are visible. |

## 3. Implementation Order

| Order | Slice | Why now |
| --- | --- | --- |
| 1 | Project skeleton | Establish modules and CI early. |
| 2 | Appointment domain and DB | Core consistency model. |
| 3 | Booking consistency flow | Highest risk driver. |
| 4 | Availability projection | Fast search. |
| 5 | Notification outbox | External provider isolation. |
| 6 | Auth and monitoring checks | Privacy and operations readiness. |

## 4. Implementation Slices

### Slice 1 - Project Skeleton

| Field | Value |
| --- | --- |
| Goal | Create web app, API service and module/package boundaries. |
| Related drivers / ADRs | ADR-001, CON-2 |
| Story/use case | Initial system skeleton. |
| Modules/files expected | web shell, API app, appointment module, availability module, notification module. |
| Acceptance criteria | App/API start locally; health endpoint works. |
| Minimum tests | API startup test; web build test. |
| Architecture constraints | Do not create distributed services for MVP. |
| Done when | Later slices can be added without restructuring. |

### Slice 2 - Appointment Domain And DB

| Field | Value |
| --- | --- |
| Goal | Implement patient, doctor, clinic, slot and appointment persistence. |
| Related drivers / ADRs | QA-1, ADR-002 |
| Story/use case | Appointment model foundation. |
| Modules/files expected | domain model, repositories, DB migration/schema, seed fixtures. |
| Acceptance criteria | Appointment can be stored with doctor/clinic/start time/status. |
| Minimum tests | Repository test; slot key uniqueness test. |
| Architecture constraints | Unique slot key must be enforced by DB. |
| Done when | Booking flow can rely on persistence. |

### Slice 3 - Booking Consistency Flow

| Field | Value |
| --- | --- |
| Goal | Implement `POST /appointments` with double-booking protection. |
| Related drivers / ADRs | QA-1, ADR-002 |
| Story/use case | CA-3 Book appointment. |
| Modules/files expected | booking controller, booking service, transaction handling, conflict response. |
| Acceptance criteria | Same doctor/clinic/startTime cannot be confirmed twice. |
| Minimum tests | Successful booking; duplicate booking rejected; transaction rollback on duplicate. |
| Architecture constraints | No optimistic check without DB constraint. |
| Done when | Double booking is impossible in accepted bookings. |

### Slice 4 - Availability Projection

| Field | Value |
| --- | --- |
| Goal | Implement `GET /availability` using read-optimized projection. |
| Related drivers / ADRs | QA-2, ADR-003 |
| Story/use case | CA-2 Search availability. |
| Modules/files expected | availability controller, projection table/model, projection updater. |
| Acceptance criteria | Search returns available slots by specialty/location/date. |
| Minimum tests | Search by date; booked slot removed from availability; empty result state. |
| Architecture constraints | Search must not scan all raw appointments for normal query path. |
| Done when | Availability search is separated from booking transaction model. |

### Slice 5 - Notification Outbox

| Field | Value |
| --- | --- |
| Goal | Queue and send appointment notifications through provider adapter. |
| Related drivers / ADRs | QA-5, ADR-005 |
| Story/use case | CA-7 Send notification request. |
| Modules/files expected | outbox table, worker, provider adapter, retry status. |
| Acceptance criteria | Booking succeeds even when provider is down. |
| Minimum tests | Outbox event created; provider failure recorded; retry attempted. |
| Architecture constraints | Provider call cannot run inside booking transaction. |
| Done when | Notifications are decoupled from booking confirmation. |

### Slice 6 - Auth And Monitoring Checks

| Field | Value |
| --- | --- |
| Goal | Add role/ownership authorization and operational logs/metrics. |
| Related drivers / ADRs | QA-4, QA-5, ADR-004 |
| Story/use case | Secure patient access and booking failure monitoring. |
| Modules/files expected | auth checks, role policy, audit log, metrics hooks. |
| Acceptance criteria | Users cannot access unauthorized appointments; failures are traceable. |
| Minimum tests | Patient ownership access test; staff role access test; failure log/metric test. |
| Architecture constraints | Authorization must run in API. |
| Done when | Security and monitoring gates are enforceable. |

## 5. Code Agent Prompt

```text
Implement only the selected slice from this file.
Use related drivers/ADRs and architecture constraints.
Do not implement unrelated slices.
Run the minimum tests listed for the slice.
```
