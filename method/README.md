# Architecture Method

Metodo practico para pasar de problema de cliente a arquitectura implementable sin perder control de informacion, decisiones y trazabilidad.

## Input Inicial

Todo proyecto inicia con un `project-brief.md`. Ese archivo lo entrega cliente/equipo y no debe contener diseno tecnico final.

Usa [project-brief-template.md](project-brief-template.md) como formato base.

## Flujo Principal

1. [Architectural Requirements](01-architectural-requirements/README.md): categorizar atributos de calidad, priorizar tradeoffs y obtener una lista priorizada de drivers.
2. [Architectural Design](02-architectural-design/README.md): ejecutar ADD con drivers aprobados y seleccionar patrones, tacticas, tecnologias y arquitecturas.
3. [Architectural Documentation](03-architectural-documentation/README.md): documentar vistas, decisiones, interfaces, eventos, trazabilidad y handoff a Scrum.

## Cadena De Inputs

```text
project-brief.md
  -> 01-architectural-requirements/input.md
  -> 02-architectural-design/input.md
  -> 03-architectural-documentation/input.md
```

## Regla Del Metodo

El agente no decide arquitectura. El agente prepara informacion, alternativas y artefactos; el arquitecto aprueba drivers, tradeoffs y decisiones.

## Salida Minima

- Drivers priorizados.
- Plan de iteraciones ADD.
- 3 a 7 decisiones arquitectonicas iniciales.
- Vistas C4 basicas y diagramas necesarios.
- Backlog inicial con epicas/stories ligadas a drivers o decisiones.
