# 02 - Architectural Design

Objetivo: disenar la arquitectura con ADD a partir de drivers aprobados.

## Entrada

- `input.md` de la fase, derivado de la salida aprobada de Architectural Requirements.
- Lista priorizada de drivers.
- Escenarios de calidad medibles.
- Constraints, concerns, riesgos y prioridades.
- Catalogo permitido de patrones, tecnologias y arquitecturas.

## Proceso

1. Definir la meta de la iteracion.
2. Elegir elementos a refinar.
3. Seleccionar conceptos de diseno: patrones, tacticas, tecnologias o arquitecturas.
4. Instanciar elementos, responsabilidades, interfaces y colaboraciones.
5. Registrar decisiones y tradeoffs.
6. Analizar si los drivers quedaron satisfechos, parcialmente satisfechos o pendientes.

## Salida

- Iteration plan ADD.
- Conceptos seleccionados.
- Decisiones arquitectonicas.
- ADD analysis.

## Approval Gate

El arquitecto aprueba decisiones, alternativas descartadas y drivers cubiertos antes de pasar a Architectural Documentation.

## Formato De Escenario

| Campo | Pregunta |
| --- | --- |
| Fuente de estimulo | Quien o que dispara el evento? |
| Estimulo | Que ocurre? |
| Artefacto | Que parte del sistema recibe el estimulo? |
| Entorno | Bajo que condiciones ocurre? |
| Respuesta | Que debe hacer el sistema? |
| Medida | Como se valida el resultado? |

## Rol Del Agente IA

El agente ejecuta ADD paso a paso, propone alternativas acotadas y prepara tablas de tradeoffs. El arquitecto aprueba cada paso antes de avanzar.
