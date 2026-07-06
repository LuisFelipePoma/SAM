# Hotel Pricing System - ADD Design Decisions

## Selected Concepts

| Driver | Selected concept | Why | Discarded alternatives |
| --- | --- | --- | --- |
| CON-4, CRN-1, QA-5 | Modular monolith with Angular UI and Java API. | Fast MVP with explicit boundaries. | Microservices from day one; unstructured layered app. |
| QA-1, QA-2, QA-8 | Transactional outbox and message broker. | Durable accepted changes and decoupled CMS publication. | Synchronous CMS calls; shared database integration. |
| QA-3, QA-4, QA-6 | Separate command/query paths with read-optimized query store/cache. | Scales query traffic without slowing price changes. | Single normalized DB for every query; full CQRS/event sourcing. |
| QA-5, CON-2 | Managed identity with API authorization by role and hotel. | Uses cloud SSO and centralizes access control. | Custom identity store; UI-only authorization. |
| QA-7, QA-9 | Externalized config and mocked external adapters. | Supports environment promotion and integration tests. | Hard-coded endpoints; tests against real systems only. |
| QA-8 | Metrics for command latency, outbox lag, publication failures and query latency. | Gives operators evidence for reliability and performance. | Logs only. |

## ADD Analysis

| Driver | Result | Evidence | Next action |
| --- | --- | --- | --- |
| QA-1 | Partially satisfied | Command flow plus outbox reduce latency risk. | Validate under 100 ms with performance test. |
| QA-2 | Satisfied for design | Accepted changes are persisted with outbox event. | Define retry and dead-letter policy. |
| QA-3 | Partially satisfied | Query path is isolated. | Add deployment redundancy details. |
| QA-4 | Partially satisfied | Read store/cache supports scaling. | Load test 100k/day and 1M/day. |
| QA-5 | Satisfied for design | Managed identity and API authorization selected. | Define permission matrix. |
