# 02 - Architectural Design

Goal: design the architecture with ADD from approved drivers.

## Input

- Phase `input.md`, derived from the approved Architectural Requirements output.
- Prioritized driver list.
- Measurable quality scenarios.
- Constraints, concerns, risks, and priorities.
- Allowed catalog of patterns, technologies, and architectures.

## Process

1. Define the iteration goal.
2. Choose elements to refine.
3. Select design concepts: patterns, tactics, technologies, or architectures.
4. Instantiate elements, responsibilities, interfaces, and collaborations.
5. Record decisions and tradeoffs.
6. Analyze whether drivers are satisfied, partially satisfied, or pending.

## Output

- Iteration plan ADD.
- Selected concepts.
- Architectural decisions.
- ADD analysis.

## Approval Gate

The architect approves decisions, discarded alternatives, and covered drivers before moving to Architectural Documentation.

## Scenario Format

| Field | Question |
| --- | --- |
| Source of stimulus | Who or what triggers the event? |
| Stimulus | What happens? |
| Artifact | Which part of the system receives the stimulus? |
| Environment | Under what conditions does it happen? |
| Response | What must the system do? |
| Measure | How is the result validated? |

## AI Agent Role

The agent runs ADD step by step, proposes bounded alternatives, and prepares tradeoff tables. The architect approves each step before moving forward.
