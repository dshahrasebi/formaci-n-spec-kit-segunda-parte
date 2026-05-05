# 🧩 Extensiones y presets de comunidad

← [Ejercicio práctico](./05-exercise.md) | Siguiente: [FAQ →](./07-faq.md)

---

Spec Kit puede ampliarse mediante dos mecanismos complementarios.

## Extensiones — Añadir nuevas capacidades

Las extensiones introducen nuevos comandos y templates para funcionalidades no cubiertas por el core.

```bash
# Buscar extensiones disponibles
specify extension search

# Instalar una extensión
specify extension add <nombre-extension>
```

**Extensiones destacadas:**

| Extensión | Propósito |
|-----------|-----------|
| `spec-kit-jira` | Crear Epics, Stories e Issues en Jira desde spec artifacts |
| `spec-kit-azure-devops` | Sincronizar con Azure DevOps Work Items |
| `spec-kit-review` | Code review post-implementación con agentes especializados |
| `spec-kit-refine` | Propagar cambios en cascada entre artefactos |
| `spec-kit-security-review` | Auditorías de seguridad en todos los artefactos |
| `spec-kit-confluence` | Generar documentación en Confluence |
| `spec-kit-brownfield` | Bootstrap SDD para proyectos existentes |
| `spec-kit-status` | Mostrar progreso del workflow SDD en curso |
| `spec-kit-verify` | Validar código implementado contra spec después de `/implement` |
| `spec-kit-iterate` | Refinar specs mid-implementation y volver a construir |

Catálogo completo: [speckit-community.github.io/extensions](https://speckit-community.github.io/extensions/)

## Presets — Personalizar flujos existentes

Los presets modifican el comportamiento del core y las extensiones sin añadir nuevas capacidades: overriding templates, formatos, terminología y estándares.

```bash
# Buscar presets disponibles
specify preset search

# Instalar un preset
specify preset add <nombre-preset>
```

**Casos de uso típicos:**

- Reestructurar templates de spec para cumplir con normativas regulatorias
- Adaptar el workflow a metodologías específicas (Agile, Kanban, DDD, V-Model)
- Añadir security review gates obligatorios en los planes
- Localizar todo el flujo a otro idioma

Catálogo completo: [github.github.io/spec-kit/community/presets.html](https://github.github.io/spec-kit/community/presets.html)

## Cuándo usar cada uno

| Necesitas | Solución |
|-----------|----------|
| Añadir un nuevo comando o workflow | Extension |
| Personalizar formato de specs, planes o tareas | Preset |
| Integrar una herramienta externa (Jira, Azure DevOps…) | Extension |
| Aplicar estándares organizativos o regulatorios | Preset |
| Plantillas con nuevo comando incluido | Extension o Preset según si añade comandos |

## Jerarquía de resolución de templates

Los templates se resuelven en runtime de mayor a menor prioridad:

```
1 (mayor prioridad)  Project-Local Overrides   .specify/templates/overrides/
2                    Presets                   .specify/presets/templates/
3                    Extensions                .specify/extensions/templates/
4 (menor prioridad)  Spec Kit Core             .specify/templates/
```

---

← [Ejercicio práctico](./05-exercise.md) | Siguiente: [FAQ →](./07-faq.md)
