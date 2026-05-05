# 5️⃣ `/speckit.analyze` — Code review antes del código

← [04 · /speckit.plan](./04-plan.md) | Siguiente: [06 · /speckit.tasks →](./06-tasks.md)

---

## ¿Qué es?

Ejecuta análisis profundo de spec y plan para detectar riesgos, inconsistencias y oportunidades de mejora *antes de implementar*.

## ¿Qué hace?

- Cross-checks spec vs. plan (¿todos los requisitos tienen cobertura en el plan?)
- Detecta decisiones no justificadas en el plan
- Identifica violaciones de Constitution, gaps de seguridad y performance bottlenecks
- Genera un findings report priorizado

## ¿Por qué importa?

Detecta problemas cuando son baratos de arreglar — antes de que haya una sola línea de código.

> "Es como un code review, pero *antes de que haya código*. Encuentra problemas cuando aún son líneas en un documento."

## Cuándo usarlo

- Después de `/speckit.tasks`, antes de `/speckit.implement` (uso principal)
- Opcionalmente después de cualquier modificación manual de `spec.md` o `plan.md`

## Propagación de cambios tras el análisis

Si `/speckit.analyze` detecta inconsistencias, la re-ejecución manual de las fases afectadas es intencional:

| Cambio derivado del análisis | Re-ejecutar |
|------------------------------|-------------|
| Corrección en `spec.md` (funcional) | `/speckit.tasks` |
| Corrección en `spec.md` (scope) | `/speckit.plan` → `/speckit.tasks` |
| Corrección en `plan.md` | `/speckit.tasks` |

> Para propagación automática de cambios, usa la extensión [`spec-kit-refine`](https://speckit-community.github.io/extensions/).

---

← [04 · /speckit.plan](./04-plan.md) | Siguiente: [06 · /speckit.tasks →](./06-tasks.md)
