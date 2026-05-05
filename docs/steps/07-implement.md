# 7️⃣ `/speckit.implement` — Cerrar el loop

← [06 · /speckit.tasks](./06-tasks.md) | [Volver al flujo SDD →](../02-sdd-flow.md)

---

## ¿Qué es?

El agente de IA **ejecuta todas las tareas** generando código funcional que cumple con spec, plan y constitution.

## ¿Qué hace?

1. Lee `tasks.md`, `spec.md`, `plan.md` y `constitution.md`.
2. Para cada tarea: entiende el dependency ordering, genera tests/código en orden y valida contra criterios de aceptación.
3. Crea PRs / commits con cambios trazables.
4. Produce código que cumple con arquitectura, principios y criterios de aceptación.

## Lo crucial

No es "generar cualquier código que funcione". Es "generar código que cumple la spec, el plan y los principios". Todo es auditable:

```
Línea de código → Task → Plan decision → Spec requirement → Constitution principle
```

## Lo que NO hace

- No improvisa decisiones de arquitectura
- No agrega features no solicitadas
- No viola las convenciones de la Constitution

> "Es el desarrollador IA. Lee el spec, el plan y las tareas. Implementa exactamente eso. No improvisa, no agrega features, no sobre-ingenieriza."

## Revisión humana continua

La intervención humana durante `/speckit.implement` es **esencial**:

- El agente reporta progreso tarea a tarea; revisar cada fase antes de continuar
- Tras completar, testear la aplicación manualmente
- Resolver cualquier error de runtime detectado
- El README oficial advierte: *"Do not treat its first attempt as final"*

## Gestionar cambios surgidos durante la implementación

Si durante la implementación surge un cambio de requisito:

```
Surge un cambio
      ↓
¿Es parte del mismo scope?
  → SÍ  → Editar spec.md existente → /speckit.clarify → /speckit.tasks
  → NO  → Nueva feature con /speckit.specify
```

> La extensión [`spec-kit-iterate`](https://speckit-community.github.io/extensions/) está diseñada para *"refine specs mid-implementation and go straight back to building"*.

## Ver en la demo

→ [Demo · FASE 5: Ejecución](../03-demo.md#fase-5--speckit-implement--ejecución)

---

← [06 · /speckit.tasks](./06-tasks.md) | [Volver al flujo SDD →](../02-sdd-flow.md)
