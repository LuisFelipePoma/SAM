# Hotel Pricing System - ADD Iteration Plan

| Iteration | Goal | Drivers | Elements to refine |
| --- | --- | --- | --- |
| 1 | Establish initial system structure. | CRN-1, CON-4, CON-6, QA-5 | Whole system, UI, API, core domain, persistence, external adapters. |
| 2 | Make price changes fast and reliable. | QA-1, QA-2, QA-8, HPS-2 | Pricing command flow, calculation component, publication flow, outbox, metrics. |
| 3 | Make price queries available and scalable. | QA-3, QA-4, QA-6, HPS-3 | Query API, read model, query store/cache, protocol adapters. |
| 4 | Prepare delivery and testability. | QA-7, QA-9, CON-3, CRN-5 | Deployment config, CI/CD, environment mocks, integration tests. |

## Execution Summary

| Iteration | Result |
| --- | --- |
| 1 | Use a modular monolith with Angular UI, Java API, domain modules, external adapters and managed identity. |
| 2 | Use event-driven publication with transactional outbox, retry and publication metrics. |
| 3 | Use separate command and query paths with a read-optimized query store/cache. |
| 4 | Use externalized configuration, containerized deployment and adapter mocks for integration tests. |
