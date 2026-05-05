# 3️⃣ `/speckit.clarify` — QA de la especificación

← [02 · /speckit.specify](./02-specify.md) | Siguiente: [04 · /speckit.plan →](./04-plan.md)

---

## ¿Qué es?

Identifica y resuelve **ambigüedades** en la especificación haciendo preguntas específicas antes de que comiencen las decisiones técnicas.

## ¿Qué hace?

1. Analiza `spec.md` detectando requisitos contradictorios, edge cases sin definir o scope sin límites.
2. Genera preguntas clarificadoras específicas y accionables.
3. Integra las respuestas de vuelta en `spec.md`.
4. Valida completitud con un checklist.

## Ejemplos de preguntas típicas

- *"¿Las refactorizaciones deben ser atómicas entre múltiples providers o puede ser eventual consistency?"*
- *"¿Cuántos reintentos automáticos antes de marcar un pago como fallido?"*
- *"¿Límite de rate por usuario, por API-key o por IP?"*
- *"¿Fraud detection para todas las transacciones o solo por encima de un umbral?"*

## ¿Por qué importa?

Un LLM no puede generar código correcto de una especificación ambigua. Este paso es el **QA de la especificación** — antes del planning, cuando los problemas son baratos de resolver.

> "Es el editor de especificaciones. Dice: 'Wait, esto es ambiguo. ¿Realmente queremos X o Y?'"

## Cuándo usarlo

- Después de `/speckit.specify`
- Antes de `/speckit.plan`
- Cada vez que aparezcan `[NEEDS CLARIFICATION]` markers en `spec.md`

## Revisión humana obligatoria

Tras ejecutar `/speckit.clarify`, verificar que:

- Las respuestas proporcionadas se han integrado correctamente en `spec.md`
- No quedan `[NEEDS CLARIFICATION]` markers sin resolver
- Las respuestas no han introducido nuevas contradicciones

## Ver en la demo

→ [Demo · FASE 2: Resolver ambigüedades](../03-demo.md#fase-2--speckit-clarify--resolver-ambigüedades)

---

← [02 · /speckit.specify](./02-specify.md) | Siguiente: [04 · /speckit.plan →](./04-plan.md)
