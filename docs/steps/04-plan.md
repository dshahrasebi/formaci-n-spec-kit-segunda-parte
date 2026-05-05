# 4️⃣ `/speckit.plan` — De intención a arquitectura

← [03 · /speckit.clarify](./03-clarify.md) | Siguiente: [05 · /speckit.analyze →](./05-analyze.md)

---

## ¿Qué es?

Traduce la especificación ejecutable en un **Plan Técnico Detallado** con decisiones arquitectónicas, tech stack, data models y API contracts.

## ¿Qué produce?

| Fichero | Contenido |
|---------|-----------|
| `plan.md` | Decisiones arquitectónicas con *rationale* |
| `data-model.md` | Schemas y relaciones |
| `contracts/` | Especificaciones de API (REST / GraphQL / WebSocket) |
| `research.md` | Benchmarks e investigación de tecnologías |
| `quickstart.md` | Escenarios de validación clave |

## ¿Por qué importa?

Aquí la **intención del negocio se convierte en arquitectura**. Cada decisión técnica traza hacia atrás a un requisito específico de la spec.

> "De 'QUÉ construir' a 'CÓMO construirlo'. Especificación + Architecture = Plan."

## Revisión humana obligatoria

Tras ejecutar `/speckit.plan`, revisar especialmente:

- `plan.md` — el agente puede ser "over-eager" e incluir componentes no solicitados; pedir rationale si algo parece innecesario
- `data-model.md` — verificar que el schema refleja exactamente los requisitos funcionales
- `contracts/` — validar que las APIs exponen lo necesario, no más

## Ver en la demo

→ [Demo · FASE 3: Roadmap técnico de 4 semanas](../03-demo.md#fase-3--speckit-plan--roadmap-técnico-de-4-semanas)

---

← [03 · /speckit.clarify](./03-clarify.md) | Siguiente: [05 · /speckit.analyze →](./05-analyze.md)
