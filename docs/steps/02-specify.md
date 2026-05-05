# 2️⃣ `/speckit.specify` — Transformar ideas en specs ejecutables

← [01 · /speckit.constitution](./01-constitution.md) | Siguiente: [03 · /speckit.clarify →](./03-clarify.md)

---

## ¿Qué es?

Transforma una descripción vaga de feature en una **Especificación de Producto Completa (PRD)** estructurada, con user stories y criterios de aceptación.

## ¿Qué produce?

`specs/<NNN>-feature-name/spec.md` — especificación completa con:

- User stories estructuradas
- Criterios de aceptación medibles
- `[NEEDS CLARIFICATION]` markers para ambigüedades
- Non-functional requirements (rendimiento, seguridad)
- Escenarios de error

## Ejemplo de transformación

```
Input:
  "Necesito un sistema de chat en tiempo real"

Output (spec.md):
  - User stories estructuradas (registro, envío, historial…)
  - Criterios de aceptación medibles (<1s latencia)
  - [NEEDS CLARIFICATION] markers para gaps
  - Non-functional: 10 k usuarios concurrentes, 99,9 % uptime
  - Error handling: desconexiones, mensajes fallidos
```

## ¿Por qué importa?

Este es el **cambio de paradigma central**: especificaciones precisas generan código preciso. Sin esto, el código generado será tan vago como el prompt de entrada.

> "Es como el requisitero tradicional, pero 10× más rápido y con templates que fuerzan completitud."

## Revisión humana obligatoria

Tras ejecutar `/speckit.specify`, **revisar siempre**:

- Scope correcto y acotado
- User stories completas
- Criterios de aceptación medibles y verificables
- Todos los `[NEEDS CLARIFICATION]` identificados

A continuación ejecutar `/speckit.clarify` para resolver esos markers antes de avanzar.

## Ver en la demo

→ [Demo · FASE 1: Generar la especificación](../03-demo.md#fase-1--speckit-specify--generar-la-especificación)

---

← [01 · /speckit.constitution](./01-constitution.md) | Siguiente: [03 · /speckit.clarify →](./03-clarify.md)
