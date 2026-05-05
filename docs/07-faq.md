# ❓ Preguntas frecuentes

← [Extensiones y presets](./06-extensions-presets.md) | Siguiente: [Recursos →](./08-resources.md)

---

## ¿Puede Spec Kit coexistir con otros agentes, skills o instrucciones personalizadas?

**Sí.** Spec Kit está diseñado para ser agnóstico al agente. Instala sus comandos `/speckit.*` en el directorio específico de cada agente (`.claude/commands/`, `.github/agents/`, etc.) sin interferir con skills o instrucciones ya existentes. El namespace `speckit.*` está dedicado y no colisiona con otros comandos.

---

## ¿La Constitution puede ser más de un fichero markdown?

Por defecto, `/speckit.constitution` trabaja con un único fichero (`memory/constitution.md`). Sin embargo, **sí es posible** estructurarla en múltiples documentos:

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

Ver más en: [01 · /speckit.constitution](./steps/01-constitution.md#puede-ser-más-de-un-fichero)

---

## Al modificar una fase anterior, ¿se actualizan automáticamente las siguientes?

**No hay actualización automática en cascada.** Es un diseño deliberado: cada fase es un artefacto independiente que el desarrollador valida antes de avanzar.

| Cambio en | Re-ejecutar |
|-----------|-------------|
| `spec.md` (solo funcional) | `/speckit.tasks` |
| `spec.md` (cambio de scope) | `/speckit.plan` → `/speckit.tasks` |
| `plan.md` (cambio técnico) | `/speckit.tasks` |
| Cualquier cambio | Opcional: `/speckit.analyze` para validar consistencia |

Para propagación automática, usa la extensión **`spec-kit-refine`** (*"Update specs in-place, propagate changes to plan and tasks, and diff impact across artifacts"*).

---

## ¿Cómo conectar Spec Kit con Confluence o Jira como fuente de historias de usuario?

**Opción A — MCP Server (recomendada):** Configura un MCP server de Confluence/Jira en tu entorno. El agente recibirá las historias como contexto y las pasará a `/speckit.specify`.

**Opción B — Extension:** Usa `spec-kit-jira` o `spec-kit-confluence` del catálogo de comunidad.

**Opción C — Manual:** Exporta historias a markdown y pégalas como argumento de `/speckit.specify`. El comando acepta cualquier texto — la fuente de origen no importa.

---

## ¿Es obligatoria la intervención humana, o puede correr todo automático?

**La intervención humana es ESENCIAL y está diseñada explícitamente en el flujo.** El README oficial lo indica: *"Do not treat its first attempt as final"*. El agente puede ser "over-eager" y añadir componentes no solicitados; la filosofía SDD asume colaboración iterativa, no generación automática irrevisable.

Puntos de revisión obligatorios: tras `/specify`, `/clarify`, `/plan`, `/tasks` y durante `/implement`.

Ver la tabla completa en: [El flujo SDD · Puntos de revisión humana](./02-sdd-flow.md#puntos-de-revisión-humana)

---

## ¿Cómo gestionar cambios que surgen durante el desarrollo?

La filosofía SDD lo contempla explícitamente: *"SDD transforms requirement changes from obstacles into normal workflow"*.

```
Surge un cambio durante la implementación
         ↓
¿Es parte del mismo scope?
  → SÍ  → Editar spec.md existente
  → NO  → Crear nueva feature con /speckit.specify
         ↓
Ejecutar /speckit.clarify (para registrar el cambio)
         ↓
Re-ejecutar /speckit.tasks (y /speckit.plan si afecta arquitectura)
         ↓
Continuar /speckit.implement con tareas actualizadas
```

La extensión **`spec-kit-iterate`** está diseñada específicamente para *"refine specs mid-implementation and go straight back to building"*.

---

## ¿Cuándo crear una nueva feature vs. modificar la actual?

| Situación | Acción |
|-----------|--------|
| Extensión o corrección del mismo scope | Editar `spec.md` existente y re-ejecutar fases afectadas |
| Nueva funcionalidad independiente con su propio alcance | Crear nueva feature con `/speckit.specify` |
| Bug o ajuste técnico sin cambio funcional | Sin tocar la spec |

---

## ¿Se puede enlazar directamente el índice de la Constitution?

**Sí.** Siempre que exista navegación entre los markdowns (hipervínculos entre documentos), el agente puede leer el fichero de entrada y seguir los enlaces a documentos relacionados. Esto funciona para agentes como Claude Code y GitHub Copilot Agent Mode, que pueden navegar el sistema de ficheros del proyecto.

---

← [Extensiones y presets](./06-extensions-presets.md) | Siguiente: [Recursos →](./08-resources.md)
