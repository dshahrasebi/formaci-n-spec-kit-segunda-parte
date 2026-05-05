# 6️⃣ `/speckit.tasks` — Sprint backlog auto-generado

← [05 · /speckit.analyze](./05-analyze.md) | Siguiente: [07 · /speckit.implement →](./07-implement.md)

---

## ¿Qué es?

Convierte el Plan Técnico en una **Lista de Tareas Ejecutables y Ordenadas** con dependencias, paralelización y test-first ordering.

## ¿Qué produce?

`tasks.md` con:

- Tasks ordenadas por dependencias
- Marcas `[P]` para tareas paralelizables
- Test-first ordering (contratos/tests antes que implementación)
- Criterios de aceptación medibles por tarea
- Trazabilidad hacia requisito específico de la spec

## Ejemplo de output

```
[Test] Crear WebSocket contract tests      (depends: nothing)
[Test] Crear data model tests              (depends: nothing)
[Code] Implementar database schema         (depends: [Test] data model)
[Code] Implementar WebSocket handler       (depends: [Test] WebSocket contract)
[P]   Implementar presence tracker        (paralelo con lo anterior)
```

## ¿Por qué importa?

Convierte 20 páginas de planning en una **lista de checkbox accionable**. La lógica de dependencias y el orden de trabajo salen directamente del plan — sin estimaciones manuales.

> "Es el sprint backlog auto-generado. No necesitas estimaciones manuales — la lógica de dependencias sale del plan automáticamente."

## Revisión recomendada

Tras `/speckit.tasks`:

1. Ejecutar `/speckit.analyze` para validar consistencia cross-artefacto
2. Revisar el orden de dependencias manualmente
3. Ajustar si hay tareas que el agente no haya paralelizado correctamente

## Ver en la demo

→ [Demo · FASE 4: Lista de tareas accionable](../03-demo.md#fase-4--speckit-tasks--lista-de-tareas-accionable)

---

← [05 · /speckit.analyze](./05-analyze.md) | Siguiente: [07 · /speckit.implement →](./07-implement.md)
