# 03 - Architectural Documentation

Objetivo: dejar evidencia suficiente para construir, revisar y mantener la arquitectura.

## Entrada

- `input.md` de la fase, derivado de la salida aprobada de Architectural Design.
- Decisiones aprobadas.
- Elementos instanciados.
- Interfaces, eventos y responsabilidades.
- Drivers satisfechos o pendientes.
- Stories/epicas iniciales.

## Proceso

1. Documentar vistas C4 minimas: contexto, contenedores y componentes cuando aplique.
2. Agregar vistas 4+1, BD o diagrama de clases solo cuando respondan una pregunta real.
3. Registrar ADRs o tabla de decisiones con alternativas y consecuencias.
4. Enlazar requisito, escenario, driver, decision, vista, story y check.
5. Bajar decisiones a epicas/stories y definir checks de gobernanza.

## Salida

- Documento de arquitectura vivo.
- Decisiones arquitectonicas.
- Interfaces y eventos relevantes.
- Matriz de trazabilidad.
- Handoff a Scrum.

## Approval Gate

Cada story critica debe enlazar a un driver o decision. Las decisiones deben tener vista/diagrama y check asociado.

La salida aprobada de esta fase alimenta Architectural Implementation.

## Rol Del Agente IA

El agente mantiene consistencia entre documentos, genera diagramas, detecta decisiones sin trazabilidad y revisa deriva arquitectura-codigo. El arquitecto valida la version final.
