# 🏋️ Ejercicio práctico guiado

← [Demo](./04-demo.md) | Siguiente: [Extensiones y presets →](./06-extensions-presets.md)

---

## Objetivo del ejercicio

Ejecutar un workflow SDD completo sobre un proyecto sencillo. Al terminar tendrás:

- Una `constitution.md` con principios arquitectónicos
- Una `spec.md` con user stories y criterios de aceptación
- Un `plan.md` con decisiones técnicas
- Un `tasks.md` listo para `/implement`

## Proyecto sugerido: Sistema de gestión de tareas CLI

```markdown
# Descripción del proyecto para /speckit.specify

Necesito una aplicación de línea de comandos para gestionar tareas del equipo de desarrollo.

Requisitos funcionales:
- Crear nuevas tareas con título, descripción y prioridad
- Listar tareas con filtros (estado, prioridad, asignado)
- Marcar tareas como completadas
- Asignar tareas a miembros del equipo
- Exportar listado de tareas a CSV

Restricciones:
- Funcionar exclusivamente en CLI (sin GUI)
- Almacenamiento local en SQLite
- Sin dependencias externas de red
- Compatible con Linux, macOS y Windows
```

## Pasos del ejercicio

```bash
# 1. Inicializar el proyecto
specify init tarea-manager --integration copilot

# 2. Abrir el agente de IA y ejecutar en orden:
/speckit.constitution  Define principios para una CLI tool con SQLite, test-first, sin over-engineering

/speckit.specify       [pegar la descripción del proyecto arriba]

/speckit.clarify       # Responder las preguntas del agente

/speckit.plan          Usar Python con Click framework, SQLite con SQLAlchemy, pytest para tests

/speckit.analyze       # Revisar el findings report

/speckit.tasks         # Revisar el sprint backlog generado

# 3. Opcional si hay tiempo disponible:
/speckit.implement
```

## Puntos de revisión humana (¡no saltárselos!)

| Fase | ¿Qué revisar? |
|------|---------------|
| Tras `/specify` | Scope, user stories, criterios de aceptación |
| Tras `/clarify` | Que las respuestas se integraron correctamente |
| Tras `/plan` | `plan.md`, `data-model.md` — el agente puede ser "over-eager" |
| Tras `/tasks` | Orden de dependencias, `/speckit.analyze` para consistencia |
| Durante `/implement` | Revisar cada fase; no dejar correr sin supervisión |

## Referencias de cada paso

| Paso | Documentación |
|------|---------------|
| `/speckit.constitution` | [01 · Constitution](./steps/01-constitution.md) |
| `/speckit.specify` | [02 · Specify](./steps/02-specify.md) |
| `/speckit.clarify` | [03 · Clarify](./steps/03-clarify.md) |
| `/speckit.plan` | [04 · Plan](./steps/04-plan.md) |
| `/speckit.analyze` | [05 · Analyze](./steps/05-analyze.md) |
| `/speckit.tasks` | [06 · Tasks](./steps/06-tasks.md) |
| `/speckit.implement` | [07 · Implement](./steps/07-implement.md) |

---

← [Demo](./04-demo.md) | Siguiente: [Extensiones y presets →](./06-extensions-presets.md)
