# 🔄 El flujo SDD: los 7 pasos

← [¿Qué es SDD?](./01-what-is-sdd.md) | Siguiente: [Instalación →](./03-installation.md)

---

## Visión de conjunto

```
┌──────────────────────────────────────────────────────────────┐
│                  SPEC-DRIVEN DEVELOPMENT                     │
├──────────────────────────────────────────────────────────────┤
│                                                              │
│  Idea / requisito de negocio                                 │
│          ↓                                                   │
│  /speckit.constitution  → ADN arquitectónico (1× proyecto)  │
│          ↓                                                   │
│  /speckit.specify       → Spec completa con user stories     │
│          ↓                                                   │
│  /speckit.clarify       → Resolver ambigüedades              │
│          ↓                                                   │
│  /speckit.plan          → Decisiones técnicas + data models  │
│          ↓                                                   │
│  /speckit.analyze       → Detectar riesgos ANTES de código   │
│          ↓                                                   │
│  /speckit.tasks         → Lista ejecutable ordenada          │
│          ↓                                                   │
│  /speckit.implement     → Código funcional y trazable        │
│          ↓                                                   │
│  Software que cumple la spec (no código al azar)             │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

## Los 7 comandos

| # | Comando | Propósito | Detalle |
|---|---------|-----------|---------|
| 1 | `/speckit.constitution` | ADN arquitectónico del proyecto | [→ ver detalle](./steps/01-constitution.md) |
| 2 | `/speckit.specify` | Spec completa con user stories | [→ ver detalle](./steps/02-specify.md) |
| 3 | `/speckit.clarify` | Resolver ambigüedades en la spec | [→ ver detalle](./steps/03-clarify.md) |
| 4 | `/speckit.plan` | Plan técnico con decisiones arquitectónicas | [→ ver detalle](./steps/04-plan.md) |
| 5 | `/speckit.analyze` | Análisis de riesgos antes de implementar | [→ ver detalle](./steps/05-analyze.md) |
| 6 | `/speckit.tasks` | Sprint backlog ordenado con dependencias | [→ ver detalle](./steps/06-tasks.md) |
| 7 | `/speckit.implement` | Generación del código trazable | [→ ver detalle](./steps/07-implement.md) |

## Comandos opcionales de calidad

| Comando | Propósito |
|---------|-----------|
| `/speckit.clarify` | Clarificar áreas poco especificadas antes de `/plan` |
| `/speckit.analyze` | Análisis cross-artefacto de consistencia y cobertura |
| `/speckit.checklist` | Generar checklists de calidad (como "unit tests para requisitos en inglés") |
| `/speckit.taskstoissues` | Convertir tasks en GitHub Issues para tracking del equipo |

## Puntos de revisión humana

La intervención humana está diseñada **explícitamente** en el flujo:

| Tras esta fase | ¿Qué revisar? |
|----------------|---------------|
| `/speckit.specify` | Scope, user stories, criterios de aceptación |
| `/speckit.clarify` | Que las respuestas se integraron correctamente |
| `/speckit.plan` | `plan.md`, `data-model.md` — el agente puede ser "over-eager" |
| `/speckit.tasks` | Orden de dependencias; ejecutar `/speckit.analyze` |
| Durante `/speckit.implement` | Revisar cada fase; no dejar correr sin supervisión |

> El README oficial advierte: *"Do not treat its first attempt as final"*

---

← [¿Qué es SDD?](./01-what-is-sdd.md) | Siguiente: [Instalación →](./03-installation.md)
