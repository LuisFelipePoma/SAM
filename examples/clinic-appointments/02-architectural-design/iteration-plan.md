# Clinic Appointments - Architectural Design

| Iteration | Goal | Drivers | Elements to refine |
| --- | --- | --- | --- |
| 1 | Establish initial system structure. | CON-2, QA-4, CA-1 | Whole system, web app, API, auth, modules, database. |
| 2 | Make booking consistent. | QA-1, CA-3, CA-4 | Booking command flow, appointment store, slot reservation. |
| 3 | Make availability search fast. | QA-2, QA-3, CA-2 | Availability query API, read model, indexes/projection. |
| 4 | Add notifications and operations visibility. | QA-5, QA-6, CA-7 | Notification outbox, provider adapter, metrics/logging. |

## Execution Summary

| Iteration | Result |
| --- | --- |
| 1 | Use a modular monolith with web app, API, appointment, identity and notification modules. |
| 2 | Use transactional booking with a unique slot constraint to prevent double-booking. |
| 3 | Use a read-optimized availability projection for search. |
| 4 | Use notification outbox and metrics/logging for provider failures. |
