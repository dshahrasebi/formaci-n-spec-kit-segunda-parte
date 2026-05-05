# 🧠 ¿Qué es Spec-Driven Development?

← [Inicio](../README.md) | Siguiente: [El flujo SDD →](./02-sdd-flow.md)

---

## El paradigma invertido

Durante décadas, el código ha sido el artefacto rey del desarrollo de software. Las especificaciones eran scaffolding temporal, descartado en cuanto "comenzaba el trabajo real". **Spec-Driven Development invierte este paradigma.**

```
DESARROLLO TRADICIONAL          SPEC-DRIVEN DEVELOPMENT
─────────────────────────       ────────────────────────────────
  Código = Verdad                 Especificaciones = Verdad
  Spec   = Guía (descartable)     Código           = Implementación

  Prompt vago → código al azar    Spec ejecutable → código preciso
```

## ¿Qué cambia en la práctica?

En SDD las especificaciones no *guían* el código; **lo generan**. El flujo es:

```
Descripción de negocio
        ↓
   Spec ejecutable  ←──── revisión humana
        ↓
   Plan técnico     ←──── revisión humana
        ↓
   Lista de tareas  ←──── revisión humana
        ↓
   Código funcional
        ↓
 Código trazable a cada requisito
```

## Por qué importa para los equipos de desarrollo

- **Predecibilidad:** Cada línea de código puede trazarse hasta un requisito de negocio.
- **Consistencia:** La Constitution establece reglas arquitectónicas que todos los agentes respetan.
- **Menos "vibe coding":** Estructuras reproducibles en lugar de generaciones al azar.
- **Revisión humana explícita:** SDD no es "genera y ejecuta"; es una colaboración humano-IA con puntos de control.

## Key takeaways para el equipo

1. **Specs son el output, no el input.** No escribes specs para describir código. Las escribes para *generarlo*.
2. **Cada paso filtra ruido:** constitution → principios | specify → requisitos | clarify → ambigüedades | plan → decisiones | analyze → riesgos | tasks → acciones | implement → código.
3. **Trazabilidad 100%:** `Línea de código → Task → Plan decision → Spec requirement → Constitution principle`
4. **AI amplifica, no reemplaza:** Estos comandos canalizan la creatividad del IA hacia precisión arquitectónica.

---

← [Inicio](../README.md) | Siguiente: [El flujo SDD →](./02-sdd-flow.md)
