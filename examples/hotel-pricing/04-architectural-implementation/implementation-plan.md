# Hotel Pricing System - Implementation Plan

## 1. Source Artifacts

- Architecture document: `../03-architectural-documentation/architecture-document.md`
- Design decisions: `../02-architectural-design/design-decisions.md`
- Traceability matrix: Architecture document section 13.
- Scrum handoff: Architecture document section 12.

## 2. Stack And Libraries

| Area | Choice | Constraint |
| --- | --- | --- |
| Frontend | Angular | Follow `design-system.md`; do not hide authorization only in UI. |
| Backend | Java API | Keep modular monolith boundaries explicit. |
| Database | Relational DB | Price updates and outbox entries must be atomic. |
| Messaging | Message broker | No synchronous CMS call inside price-change transaction. |
| Tests | Unit + integration tests | Include adapter mocks for external systems. |
| Observability | Metrics/logging/tracing | Track command latency, query latency, outbox lag and publication failures. |

## 3. Implementation Order

| Order | Slice | Why now |
| --- | --- | --- |
| 1 | Project skeleton | Establish module boundaries and CI early. |
| 2 | Pricing domain and persistence | Core model before use cases. |
| 3 | Price change flow | Main business driver. |
| 4 | Outbox publication | Reliability and decoupling. |
| 5 | Query API/read model | Availability and scalability. |
| 6 | Auth and observability checks | Security and operational readiness. |

## 4. Implementation Slices

### Slice 1 - Project Skeleton

| Field | Value |
| --- | --- |
| Goal | Create Angular app, Java API and module/package structure. |
| Related drivers / ADRs | ADR-001, QA-5, CON-4 |
| Story/use case | Initial system skeleton. |
| Modules/files expected | web app shell, API app, pricing module, query module, publication module, identity adapter. |
| Acceptance criteria | App starts locally; modules are visible; health endpoint works. |
| Minimum tests | API context/startup test; web app build test. |
| Architecture constraints | No business logic in controllers; no external system calls in domain modules. |
| Done when | Skeleton can be used by later slices without restructuring. |

### Slice 2 - Pricing Domain And Persistence

| Field | Value |
| --- | --- |
| Goal | Implement hotel, room type, rate, price and price-change persistence. |
| Related drivers / ADRs | ADR-001, ADR-002, HPS-2 |
| Story/use case | Manage price data foundation. |
| Modules/files expected | domain entities/value objects, repositories, DB migration/schema, fixtures. |
| Acceptance criteria | Prices can be persisted and queried by hotel/date/rate/room type. |
| Minimum tests | Repository test for price persistence; domain calculation test. |
| Architecture constraints | Domain logic must not depend on CMS or identity provider. |
| Done when | Price data model supports Slice 3. |

### Slice 3 - Price Change Flow

| Field | Value |
| --- | --- |
| Goal | Implement `POST /price-changes` with derived price calculation. |
| Related drivers / ADRs | QA-1, QA-2, ADR-002 |
| Story/use case | HPS-2 Change Prices. |
| Modules/files expected | command controller, use case/service, calculation service, repository transaction. |
| Acceptance criteria | Accepted change updates all derived prices and returns accepted/queryable result. |
| Minimum tests | Successful change; unauthorized hotel rejected; derived prices generated. |
| Architecture constraints | Price update and outbox creation happen in one transaction. |
| Done when | Main price-change happy path works without CMS dependency. |

### Slice 4 - Outbox Publication

| Field | Value |
| --- | --- |
| Goal | Publish `PriceChanged` events reliably to CMS adapter. |
| Related drivers / ADRs | QA-2, QA-8, ADR-002, ADR-006 |
| Story/use case | Publication to CMS. |
| Modules/files expected | outbox table, worker, CMS adapter, retry state, metrics. |
| Acceptance criteria | Failed CMS call is retried; accepted changes are not lost. |
| Minimum tests | Outbox event created; retry on transient failure; dead/failed state recorded. |
| Architecture constraints | CMS calls are never inside price-change transaction. |
| Done when | Publication can fail independently from booking/price acceptance. |

### Slice 5 - Query API And Read Model

| Field | Value |
| --- | --- |
| Goal | Implement `GET /prices` using read-optimized query path. |
| Related drivers / ADRs | QA-3, QA-4, QA-6, ADR-003 |
| Story/use case | HPS-3 Query Prices. |
| Modules/files expected | query controller, query service, read store/cache adapter, projection updater. |
| Acceptance criteria | Query returns prices without invoking calculation flow. |
| Minimum tests | Query by hotel/date; projection update after price change; missing price response. |
| Architecture constraints | Query path must not call CMS or command calculation service. |
| Done when | Query API can scale independently from command flow. |

### Slice 6 - Auth And Observability Checks

| Field | Value |
| --- | --- |
| Goal | Add managed identity adapter, authorization checks and operational metrics. |
| Related drivers / ADRs | QA-5, QA-8, ADR-004, ADR-006 |
| Story/use case | Managed login and publication metrics. |
| Modules/files expected | auth adapter, permission checks, audit/metrics hooks, dashboards config placeholder. |
| Acceptance criteria | Unauthorized hotel/function access is rejected; metrics emitted for command/query/publication. |
| Minimum tests | API authorization test; metric emitted on publication attempt; query latency metric present. |
| Architecture constraints | Authorization must run in API, not only frontend. |
| Done when | Security and core observability checks are enforceable. |

## 5. Code Agent Prompt

```text
Implement only the selected slice from this file.
Use related drivers/ADRs and architecture constraints.
Do not implement unrelated slices.
Run the minimum tests listed for the slice.
```
