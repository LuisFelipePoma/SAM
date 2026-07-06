# Software Architecture Method

Framework ligero para estandarizar arquitectura de software en proyectos Web/API empresariales con tiempos ajustados.

El metodo sigue las 3 fases del diagrama:

1. [Architectural Requirements](method/01-architectural-requirements/README.md)
2. [Architectural Design](method/02-architectural-design/README.md)
3. [Architectural Documentation](method/03-architectural-documentation/README.md)

La entrada completa del metodo esta en [method/README.md](method/README.md).

Todo proyecto empieza con un `project-brief.md`; usa [method/project-brief-template.md](method/project-brief-template.md).

## Rol Del Agente IA

El agente es copiloto aprobado: prepara artefactos, preguntas, alternativas, diagramas, ADRs y backlog inicial. El arquitecto decide prioridades, acepta tradeoffs y aprueba decisiones.

## Estructura

| Ruta | Uso |
| --- | --- |
| `method/` | Framework en 3 fases. |
| `method/project-brief-template.md` | Input inicial que entrega cliente/equipo. |
| `method/01-architectural-requirements/` | Atributos de calidad, ASR, QAW-lite, utility tree y lista priorizada. |
| `method/02-architectural-design/` | ADD y seleccion de patrones, tacticas, tecnologias y arquitecturas. |
| `method/03-architectural-documentation/` | C4, BD, 4+1, clases, ADRs, interfaces, eventos y trazabilidad. |
| `examples/hotel-pricing/` | Ejemplo AD&D Hotels separado del framework. |
| `examples/clinic-appointments/` | Segundo ejemplo para validar el metodo con otro dominio. |

## Criterio De Aceptacion

En 1 o 2 sesiones el metodo debe producir drivers priorizados, 3 a 7 decisiones arquitectonicas, vistas C4 basicas, backlog inicial y riesgos. Cada story critica debe enlazar a un driver o decision.

## Fuentes Base

ADD/SEI, QAW-lite, Views and Beyond, C4, ADRs, patrones de arquitectura empresarial y arquitectura evolutiva.
