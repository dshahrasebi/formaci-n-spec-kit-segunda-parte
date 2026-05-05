# 1️⃣ `/speckit.constitution` — El ADN arquitectónico

← [Volver al flujo SDD](../02-sdd-flow.md) | Siguiente: [02 · /speckit.specify →](./02-specify.md)

---

## ¿Qué es?

Define los principios arquitectónicos inmutables del proyecto. El "rulebook" que guía **toda** la generación de código posterior.

## ¿Qué produce?

`memory/constitution.md` con principios como:

- Arquitectura (Clean Architecture, CQRS, DDD…)
- Tech stack no negociable
- Convenciones de nombres estrictamente aplicadas
- Requisitos de testing (p. ej., cobertura > 80 %)
- Estándares de logging y resiliencia

## ¿Por qué importa?

Sin una Constitution, los LLMs pueden generar soluciones inconsistentes o sobre-ingenierizadas en cada invocación. Con ella, todas las fases siguientes respetan el mismo conjunto de decisiones.

> "La Constitución es el *linter*, pero para decisiones arquitectónicas."

## Cuándo usarlo

Una vez por proyecto, **antes que cualquier otra cosa**.

## ¿Puede ser más de un fichero?

Por defecto el comando opera sobre un único fichero (`memory/constitution.md`). Sin embargo, es posible estructurarla en múltiples documentos usando un documento maestro con referencias relativas:

```markdown
# constitution.md (documento maestro)

## Principios Generales
[...]

## Directrices de Frontend
Ver: [front-guidelines.md](./front-guidelines.md)

## Directrices de Backend
Ver: [back-guidelines.md](./back-guidelines.md)
```

Los agentes modernos (Claude Code, GitHub Copilot Agent Mode) navegan los enlaces relativos y consideran todos los documentos enlazados al tomar decisiones.

> **Requisito:** los enlaces deben ser rutas relativas válidas dentro del repositorio (no URLs externas).

## Ver en la demo

→ [Demo · FASE 1: Generar la Constitution](../03-demo.md#fase-1--speckit-specify--generar-la-especificación)

---

← [Volver al flujo SDD](../02-sdd-flow.md) | Siguiente: [02 · /speckit.specify →](./02-specify.md)
