# 04 - Architectural Implementation

Objetivo: convertir arquitectura aprobada en paquetes listos para agente de codigo o equipo Scrum.

## Entrada

- `input.md` de la fase, derivado de Architectural Documentation.
- `architecture-document.md`, decisiones, trazabilidad y Scrum handoff.
- Interfaces, eventos, governance checks y driver status.
- Stack, librerias permitidas/prohibidas y restricciones UI si aplica.

## Proceso

1. Confirmar stack, librerias y constraints que no se pueden romper.
2. Dividir la implementacion en slices pequenos y testeables.
3. Asociar cada slice con driver, ADR, story/caso de uso y check arquitectonico.
4. Definir criterios de aceptacion y tests minimos por slice.
5. Crear `design-system.md` si el proyecto tiene frontend.

## Salida

- `implementation-plan.md`.
- `design-system.md` cuando hay frontend.
- Slices de implementacion ordenados.
- Criterios de aceptacion, tests minimos y constraints por slice.

## Approval Gate

El arquitecto o tech lead aprueba que cada slice respete drivers/ADRs y tenga tests minimos antes de pasarlo al agente de codigo.

## Rol Del Agente IA

El agente prepara el plan de implementacion, design system y prompts por slice. No escribe codigo en esta fase.
