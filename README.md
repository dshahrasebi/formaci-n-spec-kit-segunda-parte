# 🌱 Spec Kit — Workshop de Formación

> **Guía completa de taller · Spec-Driven Development con Spec Kit**  
> Esta página es el punto de entrada del workshop. Toda la documentación está organizada en la carpeta [`docs/`](./docs/).

---

## 📋 Agenda del Taller

| # | Bloque | Duración | Documento |
|---|--------|----------|-----------|
| 1 | ¿Qué es Spec-Driven Development? | 15 min | [docs/01-what-is-sdd.md](./docs/01-what-is-sdd.md) |
| 2 | El flujo SDD: los 7 pasos | 30 min | [docs/02-sdd-flow.md](./docs/02-sdd-flow.md) |
| 3 | Instalación y configuración | 10 min | [docs/03-installation.md](./docs/03-installation.md) |
| 4 | Demo completa: Payment Processing Microservice | 40 min | [docs/04-demo.md](./docs/04-demo.md) |
| 5 | Ejercicio práctico guiado | 30 min | [docs/05-exercise.md](./docs/05-exercise.md) |
| 6 | Extensiones y presets de comunidad | 10 min | [docs/06-extensions-presets.md](./docs/06-extensions-presets.md) |
| 7 | Preguntas frecuentes | 15 min | [docs/07-faq.md](./docs/07-faq.md) |
| 8 | Recursos y referencias | — | [docs/08-resources.md](./docs/08-resources.md) |

**Duración total estimada:** ~2,5 horas

---

## 🔄 El flujo SDD en un vistazo

```
Idea / requisito de negocio
        ↓
/speckit.constitution  → ADN arquitectónico (1× proyecto)    docs/steps/01-constitution.md
        ↓
/speckit.specify       → Spec completa con user stories       docs/steps/02-specify.md
        ↓
/speckit.clarify       → Resolver ambigüedades                docs/steps/03-clarify.md
        ↓
/speckit.plan          → Decisiones técnicas + data models    docs/steps/04-plan.md
        ↓
/speckit.analyze       → Detectar riesgos ANTES de código     docs/steps/05-analyze.md
        ↓
/speckit.tasks         → Lista ejecutable ordenada            docs/steps/06-tasks.md
        ↓
/speckit.implement     → Código funcional y trazable          docs/steps/07-implement.md
        ↓
Software que cumple la spec (no código al azar)
```

Cada paso tiene su propia página de referencia en [`docs/steps/`](./docs/steps/).

---

## 🗂️ Estructura del repositorio

```
formación-spec-kit-segunda-parte/
├── README.md                             ← Este archivo (punto de entrada)
├── Presentation/
│   └── speckit_romeu [Auto-saved].pptx  ← Presentación PowerPoint del taller
└── docs/
    ├── 01-what-is-sdd.md                ← ¿Qué es Spec-Driven Development?
    ├── 02-sdd-flow.md                   ← El flujo SDD: los 7 pasos
    ├── 03-installation.md               ← Instalación y configuración
    ├── 04-demo.md                       ← Demo: Payment Processing Microservice
    ├── 05-exercise.md                   ← Ejercicio práctico guiado
    ├── 06-extensions-presets.md         ← Extensiones y presets de comunidad
    ├── 07-faq.md                        ← Preguntas frecuentes
    ├── 08-resources.md                  ← Recursos y referencias
    └── steps/
        ├── 01-constitution.md           ← /speckit.constitution
        ├── 02-specify.md                ← /speckit.specify
        ├── 03-clarify.md                ← /speckit.clarify
        ├── 04-plan.md                   ← /speckit.plan
        ├── 05-analyze.md                ← /speckit.analyze
        ├── 06-tasks.md                  ← /speckit.tasks
        └── 07-implement.md              ← /speckit.implement
```

---

<div align="center">

**¿Preguntas o problemas?** Abre un issue en [github/spec-kit](https://github.com/github/spec-kit/issues)

*Basado en Spec Kit v0.8.5 — MIT License — Creado por el equipo de GitHub*

</div>
