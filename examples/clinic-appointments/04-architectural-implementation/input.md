# Phase 4 Input - Architectural Implementation

## Source

- `examples/clinic-appointments/03-architectural-documentation/architecture-document.md`
- `examples/clinic-appointments/02-architectural-design/design-decisions.md`

## Stack And Library Constraints

| Area | Choice | Constraint |
| --- | --- | --- |
| Frontend | Browser web app | Must support patient and staff workflows. |
| Backend | API service | Keep booking logic behind API. |
| Database | Relational appointment DB | Must enforce unique slot constraint. |
| Notifications | External email/SMS provider | Provider failure must not break booking. |
| Observability | Metrics/logging | Booking and notification failures must be traceable. |

## Inputs To Preserve

- ADR-001 through ADR-005.
- Traceability matrix.
- Scrum handoff stories.
- Governance checks.
- REST interfaces and appointment/notification events.

## Output Expected

- `implementation-plan.md`.
- `design-system.md`.
- Code-agent-ready slices with acceptance criteria and minimum tests.

## Approval Gate

Tech lead confirms each slice keeps ADRs intact and has minimum tests before sending it to a code agent.
