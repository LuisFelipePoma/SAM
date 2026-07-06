# 03 - Architectural Documentation

Goal: leave enough evidence to build, review, and maintain the architecture.

## Input

- Phase `input.md`, derived from the approved Architectural Design output.
- Approved decisions.
- Instantiated elements.
- Interfaces, events, and responsibilities.
- Satisfied or pending drivers.
- Initial stories/epics.

## Process

1. Document minimum C4 views: context, containers, and components when applicable.
2. Add 4+1, database, or class diagram views only when they answer a real question.
3. Record ADRs or a decision table with alternatives and consequences.
4. Link requirement, scenario, driver, decision, view, story, and check.
5. Translate decisions into epics/stories and define governance checks.

## Output

- Living architecture document.
- Architectural decisions.
- Relevant interfaces and events.
- Traceability matrix.
- Handoff a Scrum.

## Approval Gate

Each critical story must link to a driver or decision. Decisions must have an associated view/diagram and check.

The approved output from this phase feeds Architectural Implementation.

## AI Agent Role

The agent keeps documents consistent, generates diagrams, detects decisions without traceability, and reviews architecture-code drift. The architect validates the final version.
