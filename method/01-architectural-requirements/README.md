# 01 - Architectural Requirements

Objetivo: convertir el problema del cliente en drivers arquitectonicos priorizados.

## Entrada

- `input.md` de la fase, derivado de `project-brief.md` y preparado como briefing minimo por el arquitecto.
- Problema de negocio, objetivo, alcance/MVP y stakeholders.
- Funcionalidades principales, atributos de calidad esperados y restricciones.
- Sistemas externos, contexto actual y prioridades del cliente.

`architecture-drivers.md` no es input manual. Es la salida que el agente genera desde `project-brief.md` + `input.md`, y que el arquitecto revisa/aprueba.

## Proceso

1. Separar funcionales clave, atributos de calidad, constraints y concerns.
2. Categorizar atributos de calidad usando ISO/SEI como vocabulario base.
3. Convertir atributos importantes en escenarios medibles.
4. Priorizar con QAW-lite / utility tree y discutir tradeoffs.
5. Generar `architecture-drivers.md` con ASR, escenarios, utility tree y drivers priorizados.

## Salida

| Artefacto | Contenido |
| --- | --- |
| `architecture-drivers.md` | ASR, escenarios medibles, utility tree y lista de drivers. |
| Approved driver list | Lista final revisada y aprobada por el arquitecto. |

## Approval Gate

El arquitecto no redacta todo el documento manualmente. Aprueba/corrige drivers primarios, supporting drivers, metricas, prioridades y tradeoffs antes de pasar a Architectural Design.

## Rol Del Agente IA

El agente hace el trabajo pesado de analisis y redaccion: resume el problema, detecta ambiguedades, clasifica ASR, propone escenarios medibles, prioriza y genera `architecture-drivers.md`. El arquitecto conserva la decision final.
