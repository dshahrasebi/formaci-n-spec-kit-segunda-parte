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

```
DESARROLLO TRADICIONAL          SPEC-DRIVEN DEVELOPMENT
─────────────────────────       ────────────────────────────────
  Código = Verdad                 Especificaciones = Verdad
  Spec   = Guía (descartable)     Código           = Implementación
  
  Prompt vago → código al azar    Spec ejecutable → código preciso
```

### ¿Qué cambia en la práctica?

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

### Por qué importa para los equipos de desarrollo

- **Predecibilidad**: Cada línea de código puede trazarse hasta un requisito de negocio.
- **Consistencia**: La Constitution establece reglas arquitectónicas que todos los agentes respetan.
- **Menos "vibe coding"**: Estructuras reproducibles en lugar de generaciones al azar.
- **Revisión humana explícita**: SDD no es "genera y ejecuta"; es una colaboración humano-IA con puntos de control.

---

## 🔄 El flujo SDD: los 7 pasos

### Visión de conjunto

```
┌──────────────────────────────────────────────────────────────┐
│                  SPEC-DRIVEN DEVELOPMENT                     │
├──────────────────────────────────────────────────────────────┤
│                                                              │
│  Idea / requisito de negocio                                 │
│          ↓                                                   │
│  /speckit.constitution  → ADN arquitectónico (1× proyecto)  │
│          ↓                                                   │
│  /speckit.specify       → Spec completa con user stories     │
│          ↓                                                   │
│  /speckit.clarify       → Resolver ambigüedades              │
│          ↓                                                   │
│  /speckit.plan          → Decisiones técnicas + data models  │
│          ↓                                                   │
│  /speckit.analyze       → Detectar riesgos ANTES de código   │
│          ↓                                                   │
│  /speckit.tasks         → Lista ejecutable ordenada          │
│          ↓                                                   │
│  /speckit.implement     → Código funcional y trazable        │
│          ↓                                                   │
│  Software que cumple la spec (no código al azar)             │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

---

### 1️⃣ `/speckit.constitution` — El ADN arquitectónico

**¿Qué es?**  
Define los principios arquitectónicos inmutables del proyecto. El "rulebook" que guía **toda** la generación de código posterior.

**¿Qué produce?**  
- `memory/constitution.md` con principios como:
  - Arquitectura (Clean Architecture, CQRS, DDD…)
  - Tech stack no negociable
  - Convenciones de nombres estrictamente aplicadas
  - Requisitos de testing (p. ej., cobertura > 80 %)
  - Estándares de logging y resiliencia

**¿Por qué importa?**  
Sin una Constitution, los LLMs pueden generar soluciones inconsistentes o sobre-ingenierizadas en cada invocación. Con ella, todas las fases siguientes respetan el mismo conjunto de decisiones.

**Analogía:**  
> "La Constitución es el *linter*, pero para decisiones arquitectónicas."

**Cuándo usarlo:** Una vez por proyecto, antes que cualquier otra cosa.

---

### 2️⃣ `/speckit.specify` — Transformar ideas en specs ejecutables

**¿Qué es?**  
Transforma una descripción vaga de feature en una **Especificación de Producto Completa (PRD)** estructurada, con user stories y criterios de aceptación.

**¿Qué produce?**
- `specs/<NNN>-feature-name/spec.md` — especificación completa con:
  - User stories estructuradas
  - Criterios de aceptación medibles
  - `[NEEDS CLARIFICATION]` markers para ambigüedades
  - Non-functional requirements (rendimiento, seguridad)
  - Escenarios de error

**Ejemplo de transformación:**

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

**Analogía:**  
> "Es como el requisitero tradicional, pero 10× más rápido y con templates que fuerzan completitud."

---

### 3️⃣ `/speckit.clarify` — QA de la especificación

**¿Qué es?**  
Identifica y resuelve **ambigüedades** en la especificación haciendo preguntas específicas antes de que comiencen las decisiones técnicas.

**¿Qué hace?**
1. Analiza `spec.md` detectando requisitos contradictorios, edge cases sin definir o scope sin límites.
2. Genera preguntas clarificadoras específicas y accionables.
3. Integra las respuestas de vuelta en `spec.md`.
4. Valida completitud con un checklist.

**Ejemplos de preguntas típicas:**
- *"¿Las refactorizaciones deben ser atómicas entre múltiples providers o puede ser eventual consistency?"*
- *"¿Cuántos reintentos automáticos antes de marcar un pago como fallido?"*
- *"¿Límite de rate por usuario, por API-key o por IP?"*

**Analogía:**  
> "Es el editor de especificaciones. Dice: 'Wait, esto es ambiguo. ¿Realmente queremos X o Y?'"

**Cuándo usarlo:** Después de `/specify`, antes de `/plan`, cuando ves `[NEEDS CLARIFICATION]` en la spec.

---

### 4️⃣ `/speckit.plan` — De intención a arquitectura

**¿Qué es?**  
Traduce la especificación ejecutable en un **Plan Técnico Detallado** con decisiones arquitectónicas, tech stack, data models y API contracts.

**¿Qué produce?**
- `plan.md` — decisiones arquitectónicas con *rationale*
- `data-model.md` — schemas y relaciones
- `contracts/` — especificaciones de API (REST / GraphQL / WebSocket)
- `research.md` — benchmarks e investigación de tecnologías
- `quickstart.md` — escenarios de validación clave

**¿Por qué importa?**  
Aquí la **intención del negocio se convierte en arquitectura**. Cada decisión técnica traza hacia atrás a un requisito específico de la spec.

**Analogía:**  
> "De 'QUÉ construir' a 'CÓMO construirlo'. Especificación + Architecture = Plan."

---

### 5️⃣ `/speckit.analyze` — Code review antes del código

**¿Qué es?**  
Ejecuta análisis profundo de spec y plan para detectar riesgos, inconsistencias y oportunidades de mejora *antes de implementar*.

**¿Qué hace?**
- Cross-checks spec vs. plan (¿todos los requisitos tienen cobertura?)
- Detecta violaciones de Constitution, gaps de seguridad, performance bottlenecks
- Genera un findings report con prioridades

**Analogía:**  
> "Es como un code review, pero *antes de que haya código*. Encuentra problemas cuando aún son líneas en un documento."

---

### 6️⃣ `/speckit.tasks` — Sprint backlog auto-generado

**¿Qué es?**  
Convierte el Plan Técnico en una **Lista de Tareas Ejecutables y Ordenadas** con dependencias, paralelización y test-first ordering.

**¿Qué produce?**  
`tasks.md` con:
- Tasks ordenadas por dependencias
- Marcas `[P]` para tareas paralelizables
- Test-first ordering (contratos/tests antes que implementación)
- Criterios de aceptación medibles por tarea
- Trazabilidad hacia requisito específico de la spec

**Ejemplo:**
```
[Test] Crear WebSocket contract tests      (depends: nothing)
[Test] Crear data model tests              (depends: nothing)
[Code] Implementar database schema         (depends: [Test] data model)
[Code] Implementar WebSocket handler       (depends: [Test] WebSocket contract)
[P]   Implementar presence tracker        (paralelo con lo anterior)
```

**Analogía:**  
> "Es el sprint backlog auto-generado. No necesitas estimaciones manuales — la lógica de dependencias sale del plan automáticamente."

---

### 7️⃣ `/speckit.implement` — Cerrar el loop

**¿Qué es?**  
El agente de IA **ejecuta todas las tareas** generando código funcional que cumple con spec, plan y constitution.

**¿Qué hace?**
1. Lee `tasks.md`, `spec.md`, `plan.md`, `constitution.md`.
2. Para cada tarea: entiende el dependency ordering, genera tests/código en orden y valida contra criterios de aceptación.
3. Crea PRs / commits con cambios trazables.
4. Produce código que cumple con arquitectura, principios y criterios de aceptación.

**Lo crucial:**  
No es "generar cualquier código que funcione". Es "generar código que cumple la spec, el plan y los principios". Todo es auditable.

```
Línea de código → Task → Plan decision → Spec requirement → Constitution principle
```

**Analogía:**  
> "Es el desarrollador IA. Lee el spec, el plan y las tareas. Implementa exactamente eso. No improvisa, no agrega features, no sobre-ingenieriza."

---

### Comandos opcionales de calidad

| Comando | Propósito |
|---------|-----------|
| `/speckit.clarify` | Clarificar áreas poco especificadas antes de `/plan` |
| `/speckit.analyze` | Análisis cross-artefacto de consistencia y cobertura |
| `/speckit.checklist` | Generar checklists de calidad (como "unit tests para requisitos en inglés") |
| `/speckit.taskstoissues` | Convertir tasks en GitHub Issues para tracking del equipo |

---

## ⚙️ Instalación y configuración

### Prerrequisitos

- Python 3.11+
- [`uv`](https://docs.astral.sh/uv/) (recomendado) o `pipx`
- Git
- Un agente de IA compatible (GitHub Copilot, Claude Code, Cursor, Windsurf…)

### Instalación persistente (recomendada)

```bash
# Instalar una release estable (sustituye vX.Y.Z por la versión más reciente)
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git@vX.Y.Z

# Verificar instalación
specify version

# Comprobar herramientas disponibles
specify check
```

### Inicializar un proyecto nuevo

```bash
# Proyecto nuevo
specify init <NOMBRE_PROYECTO>

# En un repositorio existente
specify init . --integration copilot
# o
specify init --here --integration copilot
```

### Actualizar Spec Kit

```bash
uv tool install specify-cli --force --from git+https://github.com/github/spec-kit.git@vX.Y.Z
```

### Agentes de IA soportados (30+)

| Agente | Directorio de comandos |
|--------|------------------------|
| GitHub Copilot | `.github/agents/` |
| Claude Code | `.claude/commands/` |
| Cursor | `.cursor/commands/` |
| Windsurf | `.windsurf/workflows/` |
| Gemini CLI | `.gemini/commands/` |
| Amazon Q Developer CLI | `.amazonq/prompts/` |
| Codex CLI | `.codex/commands/` |

> Spec Kit **no reemplaza** ningún agente ni skill existente. Añade sus comandos `/speckit.*` encima sin interferir con lo que ya tengas configurado.

---

## 🎬 Demo completa: Payment Processing Microservice

> Esta sección recorre un workflow SDD **completo** aplicado a un microservicio real de procesamiento de pagos en .NET 10. Los outputs que se muestran son 100% auténticos — generados previamente para mantener el flujo de la demo.

### Contexto del proyecto

- **Sistema:** Payment Processing Microservice
- **Stack:** .NET 10, ASP.NET Core, PostgreSQL, RabbitMQ, Redis, Serilog, Polly
- **Arquitectura:** Clean Architecture (5 capas), CQRS + MediatR
- **Duración del workflow completo:** ~40-50 min de ejecución real

---

### FASE 1 — `/speckit.specify` · Generar la especificación

**Prompt utilizado:**
```
Contexto: Estamos construyendo un Payment Processing Microservice en .NET 10
Objetivo: Generar una Constitution que defina governance, convenciones, 
          tech stack y patrones de arquitectura.

Requisitos:
1. Leer la especificación (spec.md) proporcionada
2. Extraer los patrones arquitectónicos necesarios
3. Definir el tech stack (no negociable)
4. Crear convenciones de nombres para el código
5. Definir arquitectura Clean Architecture de 5 capas
6. Especificar uso de CQRS + MediatR
7. Definir patrones de resiliencia (Polly obligatorio)
8. Crear estándares de logging (Serilog structured logging)
9. Definir requisitos de testing (>80% cobertura)
10. Crear reglas de autenticación/autorización
```

**Output generado (`constitution.md`):**
- 8 Principios básicos (Clean Architecture, CQRS, MCP-First, Resiliencia, Observabilidad, Naming, Testing, Autenticación)
- Tech Stack no negociable: .NET 10, ASP.NET Core, PostgreSQL, RabbitMQ, Redis, Entity Framework, xUnit, Serilog, Polly, OpenAPI
- Convenciones de nombres estrictas (Commands = `{Action}Command`, Handlers = `{Action}CommandHandler`…)
- 5 capas: 01-Domain, 02-Business, 03-Infrastructure, 04-Host, 05-Tests
- PR Checklist (naming, tests, layer separation, logging, resilience, async/await)

**⏱ Tiempo de generación:** 2-3 minutos

---

### FASE 2 — `/speckit.clarify` · Resolver ambigüedades

**Preguntas generadas por el agente:**

| # | Pregunta | Respuesta registrada |
|---|----------|----------------------|
| 1 | ¿Las refactorizaciones deben ser atómicas entre providers? | Eventual consistency aceptable entre providers |
| 2 | ¿Cuántos reintentos automáticos antes de marcar pago fallido? | 3 reintentos con backoff exponencial (2s, 4s, 8s) |
| 3 | ¿Fraud detection para todas las transacciones o solo por umbral? | Todas obligatorio por PCI-DSS |
| 4 | ¿Rate limiting por usuario, API-key o IP? | Por usuario; fallback por IP para tráfico anónimo |
| 5 | ¿Webhook redundancy: polling como fallback? | Sí; si no se recibe webhook en 5 min, hacer polling |
| 6 | ¿Tipos de cambio en tiempo real o fijos diarios? | Tiempo real; cache 1 hora para reducir llamadas API |
| 7 | ¿Refunds parciales desde el inicio? | Sí, con registro de razón obligatorio |
| 8 | ¿Retención de logs de auditoría? | 7 años; archivar a cold storage tras 2 años |

**⏱ Tiempo de generación:** 3-5 minutos

---

### FASE 3 — `/speckit.plan` · Roadmap técnico de 4 semanas

**Output generado (`plan.md`):**

#### Semana 1 — Foundation
- Scaffolding del proyecto aplicando Constitution (5 capas)
- Schema PostgreSQL con migraciones
- Auth OAuth 2.0 + JWT
- Health check endpoint
- Serilog configurado
- xUnit framework operativo
- CI/CD pipeline operativo (build → test → pass)

#### Semana 2 — Core Payment Processing
- `ProcessPaymentCommand` handler con lógica de negocio
- Stripe provider adapter
- Polly resilience policies (3 reintentos, circuit breaker)
- Rate limiting middleware
- Unit tests (>80 % cobertura)
- Integration tests con Testcontainers

#### Semana 3 — Multi-Provider & Webhooks
- PayPal + Apple Pay provider adapters
- Webhook handlers con validación de firma
- Provider failover automático
- Monitoring dashboard (Prometheus + Grafana)

#### Semana 4 — Operations & Hardening
- Suite completa de integration tests
- Security hardening
- Load testing: 10.000 tx/min sostenidas
- Performance: p95 < 100 ms
- Kubernetes manifests + HPA
- Runbook para on-call

**⏱ Tiempo de generación:** 5-7 minutos

---

### FASE 4 — `/speckit.tasks` · Lista de tareas accionable

**Estructura del output generado (`tasks.md`):**

```markdown
## Semana 1: Foundation

- [ ] [Test] Crear test de health check endpoint
- [ ] [Code] Scaffolding Clean Architecture (5 capas)
- [ ] [Code] Configurar PostgreSQL + migrations
- [ ] [Code] Implementar OAuth 2.0 + JWT middleware
- [ ] [Code] Configurar Serilog structured logging
- [ ] [Code] Configurar CI/CD pipeline

## Semana 2: Core Payment Processing

- [ ] [Test] Crear contract tests ProcessPaymentCommand
- [ ] [Test] Crear integration tests con Testcontainers
- [ ] [Code] Implementar ProcessPaymentCommand handler
- [ ] [Code] Stripe provider adapter (depends: contract tests)
- [ ] [Code] Polly resilience policies
- [ ] [P]   Rate limiting middleware (paralelo)

## Semana 3: Multi-Provider & Webhooks

- [ ] [Code] PayPal provider adapter
- [ ] [P]   Apple Pay provider adapter (paralelo)
- [ ] [Code] Webhook handlers (validación de firma)
- [ ] [Code] Provider failover orchestration

## Semana 4: Operations & Hardening

- [ ] [Test] Full integration test suite
- [ ] [Code] Security hardening
- [ ] [Test] Load testing (10.000 tx/min)
- [ ] [Code] Kubernetes manifests + HPA
- [ ] [Docs] Runbook on-call
```

**⏱ Tiempo de generación:** 3-4 minutos

---

### FASE 5 — `/speckit.implement` · Ejecución

El agente lee `constitution.md`, `spec.md`, `plan.md` y `tasks.md` y genera el código tarea por tarea, siguiendo el orden de dependencias. Cada commit incluye trazabilidad hacia la task → requisito → principio de Constitution.

**Lo que NO hace:**
- No improvisa decisiones de arquitectura
- No agrega features no solicitadas
- No viola las convenciones de la Constitution

**⏱ Tiempo total de ejecución:** ~20-30 minutos para el proyecto completo

---

## 🏋️ Ejercicio práctico guiado

### Objetivo del ejercicio

Ejecutar un workflow SDD completo sobre un proyecto sencillo. Al terminar tendrás:
- Una `constitution.md` con principios arquitectónicos
- Una `spec.md` con user stories y criterios de aceptación
- Un `plan.md` con decisiones técnicas
- Un `tasks.md` listo para `/implement`

### Proyecto sugerido: Sistema de gestión de tareas CLI

```markdown
# Descripción del proyecto para /speckit.specify

Necesito una aplicación de línea de comandos para gestionar tareas del equipo de desarrollo.

Requisitos funcionales:
- Crear nuevas tareas con título, descripción y prioridad
- Listar tareas con filtros (estado, prioridad, asignado)
- Marcar tareas como completadas
- Asignar tareas a miembros del equipo
- Exportar listado de tareas a CSV

Restricciones:
- Funcionar exclusivamente en CLI (sin GUI)
- Almacenamiento local en SQLite
- Sin dependencias externas de red
- Compatible con Linux, macOS y Windows
```

### Pasos del ejercicio

```bash
# 1. Inicializar el proyecto
specify init tarea-manager --integration copilot

# 2. Abrir el agente de IA y ejecutar en orden:
/speckit.constitution  Define principios para una CLI tool con SQLite, test-first, sin over-engineering

/speckit.specify       [pegar la descripción del proyecto arriba]

/speckit.clarify       # Responder las preguntas del agente

/speckit.plan          Usar Python con Click framework, SQLite con SQLAlchemy, pytest para tests

/speckit.analyze       # Revisar el findings report

/speckit.tasks         # Revisar el sprint backlog generado

# 3. Opcional si hay tiempo disponible:
/speckit.implement
```

### Puntos de revisión humana (¡no saltárselos!)

| Fase | ¿Qué revisar? |
|------|---------------|
| Tras `/specify` | Scope, user stories, criterios de aceptación |
| Tras `/clarify` | Que las respuestas se integraron correctamente |
| Tras `/plan` | `plan.md`, `data-model.md` — el agente puede ser "over-eager" |
| Tras `/tasks` | Orden de dependencias, `/speckit.analyze` para consistencia |
| Durante `/implement` | Revisar cada fase; no dejar correr sin supervisión |

---

## 🧩 Extensiones y presets de comunidad

Spec Kit puede ampliarse mediante dos mecanismos complementarios:

### Extensiones — Añadir nuevas capacidades

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

### Presets — Personalizar flujos existentes

Los presets modifican el comportamiento del core y las extensiones sin añadir nuevas capacidades: overriding templates, formatos, terminología y estándares.

```bash
# Buscar presets disponibles
specify preset search

# Instalar un preset
specify preset add <nombre-preset>
```

**Casos de uso típicos de presets:**
- Reestructurar templates de spec para cumplir con normativas regulatorias
- Adaptar el workflow a metodologías específicas (Agile, Kanban, DDD, V-Model)
- Añadir security review gates obligatorios en los planes
- Localizar todo el flujo a otro idioma

### Cuándo usar cada uno

| Necesitas | Solución |
|-----------|----------|
| Añadir un nuevo comando o workflow | Extension |
| Personalizar formato de specs, planes o tareas | Preset |
| Integrar una herramienta externa (Jira, Azure DevOps…) | Extension |
| Aplicar estándares organizativos o regulatorios | Preset |

### Jerarquía de resolución de templates

```
1 (mayor prioridad)  Project-Local Overrides   .specify/templates/overrides/
2                    Presets                   .specify/presets/templates/
3                    Extensions                .specify/extensions/templates/
4 (menor prioridad)  Spec Kit Core             .specify/templates/
```

---

## ❓ Preguntas frecuentes

### ¿Puede Spec Kit coexistir con otros agentes, skills o instrucciones personalizadas?

**Sí.** Spec Kit está diseñado para ser agnóstico al agente. Instala sus comandos `/speckit.*` en el directorio específico de cada agente (`.claude/commands/`, `.github/agents/`, etc.) sin interferir con skills o instrucciones ya existentes. El namespace `speckit.*` está dedicado y no colisiona con otros comandos.

---

### ¿La Constitution puede ser más de un fichero markdown?

Por defecto, `/speckit.constitution` trabaja con un único fichero (`memory/constitution.md`). Sin embargo, **sí es posible** estructurar en múltiples documentos:

```markdown
# constitution.md (documento maestro)

## Principios Generales
[...]

## Directrices de Frontend
Ver: [front-guidelines.md](./front-guidelines.md)

## Directrices de Backend
Ver: [back-guidelines.md](./back-guidelines.md)
```

Los agentes modernos (Claude Code, GitHub Copilot Agent Mode) navegan los enlaces relativos y consideran todos los documentos enlazados al tomar decisiones. **Requisito:** los enlaces deben ser rutas relativas válidas dentro del repositorio (no URLs externas).

---

### Al modificar una fase anterior, ¿se actualizan automáticamente las siguientes?

**No hay actualización automática en cascada.** Es un diseño deliberado: cada fase es un artefacto independiente que el desarrollador valida antes de avanzar.

| Cambio en | Re-ejecutar |
|-----------|-------------|
| `spec.md` (solo funcional) | `/speckit.tasks` |
| `spec.md` (cambio de scope) | `/speckit.plan` → `/speckit.tasks` |
| `plan.md` (cambio técnico) | `/speckit.tasks` |
| Cualquier cambio | Opcional: `/speckit.analyze` para validar consistencia |

Para propagación automática, usa la extensión **`spec-kit-refine`** (*"Update specs in-place, propagate changes to plan and tasks, and diff impact across artifacts"*).

---

### ¿Cómo conectar Spec Kit con Confluence o Jira como fuente de historias de usuario?

**Opción A — MCP Server (recomendada):** Configura un MCP server de Confluence/Jira en tu entorno. El agente recibirá las historias como contexto y las pasará a `/speckit.specify`.

**Opción B — Extension:** Usa `spec-kit-jira` o `spec-kit-confluence` del catálogo de comunidad.

**Opción C — Manual:** Exporta historias a markdown y pégalas como argumento de `/speckit.specify`. `/speckit.specify` acepta cualquier texto — la fuente de origen no importa.

---

### ¿Es obligatoria la intervención humana, o puede correr todo automático?

**La intervención humana es ESENCIAL y está diseñada explícitamente en el flujo.** El README oficial lo indica: *"Do not treat its first attempt as final"*. El agente puede ser "over-eager" y añadir componentes no solicitados; la filosofía SDD asume colaboración iterativa, no generación automática irrevisable.

Puntos de revisión obligatorios: tras `/specify`, `/clarify`, `/plan`, `/tasks` y durante `/implement`.

---

### ¿Cómo gestionar cambios que surgen durante el desarrollo?

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

### ¿Cuándo crear una nueva feature vs. modificar la actual?

| Situación | Acción |
|-----------|--------|
| Extensión o corrección del mismo scope | Editar `spec.md` existente y re-ejecutar fases afectadas |
| Nueva funcionalidad independiente con su propio alcance | Crear nueva feature con `/speckit.specify` |
| Bug o ajuste técnico sin cambio funcional | Sin tocar la spec |

---

## 📚 Recursos y referencias

### Repositorio oficial

- **GitHub:** [github/spec-kit](https://github.com/github/spec-kit)
- **Documentación:** [github.github.io/spec-kit](https://github.github.io/spec-kit/)
- **Metodología SDD completa:** [spec-driven.md](https://github.com/github/spec-kit/blob/main/spec-driven.md)
- **Extensiones comunitarias:** [speckit-community.github.io/extensions](https://speckit-community.github.io/extensions/)
- **Presets comunitarios:** [github.github.io/spec-kit/community/presets.html](https://github.github.io/spec-kit/community/presets.html)

### Vídeos

- [🎬 Video Overview oficial de Spec Kit](https://www.youtube.com/watch?v=a9eR1xsfvHg)

### Instalación y referencia CLI

- [CLI Reference](https://github.github.io/spec-kit/reference/overview.html)
- [Upgrade Guide](https://github.com/github/spec-kit/blob/main/docs/upgrade.md)
- [Enterprise / Air-Gapped Installation](https://github.com/github/spec-kit/blob/main/docs/installation.md#enterprise--air-gapped-installation)
- [Supported AI Integrations](https://github.github.io/spec-kit/reference/integrations.html)

### Extensiones útiles para empezar

```bash
specify extension add spec-kit-status        # Ver progreso del workflow
specify extension add spec-kit-verify        # Validar código vs spec
specify extension add spec-kit-refine        # Propagar cambios en cascada
specify extension add spec-kit-brownfield    # Bootstrap en proyectos existentes
specify extension add spec-kit-jira          # Integración Jira
specify extension add spec-kit-azure-devops  # Integración Azure DevOps
```

---

## 🗂️ Estructura del repositorio

```
formación-spec-kit-segunda-parte/
├── README.md                          ← Esta guía (workshop guide + presentación)
└── Presentation/
    └── speckit_romeu [Auto-saved].pptx   ← Presentación PowerPoint del taller
```

---

<div align="center">

**¿Preguntas o problemas?** Abre un issue en [github/spec-kit](https://github.com/github/spec-kit/issues)

*Basado en Spec Kit v0.8.5 — MIT License — Creado por el equipo de GitHub*

</div>
