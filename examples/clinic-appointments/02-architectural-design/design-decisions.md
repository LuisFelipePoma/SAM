# Clinic Appointments - ADD Design Decisions

## Selected Concepts

| Driver | Selected concept | Why | Discarded alternatives |
| --- | --- | --- | --- |
| CON-2, QA-4 | Modular monolith. | Fits small team and 10-week MVP while keeping boundaries clear. | Microservices; unmanaged layered app. |
| QA-1 | Transactional booking with unique slot constraint. | Database constraint is the simplest reliable double-booking guard. | Distributed lock; optimistic check only. |
| QA-2 | Read-optimized availability projection. | Keeps search fast without complicating booking transaction. | Search directly over raw appointment tables. |
| QA-4 | API role/ownership authorization with audit logging. | Protects patient data regardless of UI behavior. | UI-only checks. |
| QA-5 | Notification outbox with provider adapter. | Confirmed bookings are not blocked by SMS/email outages. | Synchronous provider call inside booking transaction. |

## ADD Analysis

| Driver | Result | Evidence | Next action |
| --- | --- | --- | --- |
| QA-1 | Satisfied for design | Unique slot constraint protects booking consistency. | Define exact slot key. |
| QA-2 | Partially satisfied | Availability projection selected. | Validate with expected peak load. |
| QA-4 | Satisfied for design | API authorization and audit logging selected. | Define role matrix. |
| QA-5 | Partially satisfied | Notification outbox selected. | Define retry policy and alerts. |
| QA-6 | Partially satisfied | Modular boundaries support future modules. | Keep appointment core independent of payment/telemedicine. |
