# 🎬 Demo completa: Payment Processing Microservice

← [Instalación](./03-installation.md) | Siguiente: [Ejercicio práctico →](./05-exercise.md)

---

> Esta sección recorre un workflow SDD **completo** aplicado a un microservicio real de procesamiento de pagos en .NET 10. Los outputs que se muestran son 100% auténticos — generados previamente para mantener el flujo de la demo.

## Contexto del proyecto

- **Sistema:** Payment Processing Microservice
- **Stack:** .NET 10, ASP.NET Core, PostgreSQL, RabbitMQ, Redis, Serilog, Polly
- **Arquitectura:** Clean Architecture (5 capas), CQRS + MediatR
- **Duración del workflow completo:** ~40-50 min de ejecución real

---

## FASE 1 — `/speckit.specify` · Generar la especificación

> Ver referencia del comando: [02 · /speckit.specify](./steps/02-specify.md)

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

## FASE 2 — `/speckit.clarify` · Resolver ambigüedades

> Ver referencia del comando: [03 · /speckit.clarify](./steps/03-clarify.md)

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

## FASE 3 — `/speckit.plan` · Roadmap técnico de 4 semanas

> Ver referencia del comando: [04 · /speckit.plan](./steps/04-plan.md)

**Output generado (`plan.md`):**

### Semana 1 — Foundation

- Scaffolding del proyecto aplicando Constitution (5 capas)
- Schema PostgreSQL con migraciones
- Auth OAuth 2.0 + JWT
- Health check endpoint
- Serilog configurado
- xUnit framework operativo
- CI/CD pipeline operativo (build → test → pass)

### Semana 2 — Core Payment Processing

- `ProcessPaymentCommand` handler con lógica de negocio
- Stripe provider adapter
- Polly resilience policies (3 reintentos, circuit breaker)
- Rate limiting middleware
- Unit tests (>80 % cobertura)
- Integration tests con Testcontainers

### Semana 3 — Multi-Provider & Webhooks

- PayPal + Apple Pay provider adapters
- Webhook handlers con validación de firma
- Provider failover automático
- Monitoring dashboard (Prometheus + Grafana)

### Semana 4 — Operations & Hardening

- Suite completa de integration tests
- Security hardening
- Load testing: 10.000 tx/min sostenidas
- Performance: p95 < 100 ms
- Kubernetes manifests + HPA
- Runbook para on-call

**⏱ Tiempo de generación:** 5-7 minutos

---

## FASE 4 — `/speckit.tasks` · Lista de tareas accionable

> Ver referencia del comando: [06 · /speckit.tasks](./steps/06-tasks.md)

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

## FASE 5 — `/speckit.implement` · Ejecución

> Ver referencia del comando: [07 · /speckit.implement](./steps/07-implement.md)

El agente lee `constitution.md`, `spec.md`, `plan.md` y `tasks.md` y genera el código tarea por tarea, siguiendo el orden de dependencias. Cada commit incluye trazabilidad hacia la task → requisito → principio de Constitution.

**Lo que NO hace:**

- No improvisa decisiones de arquitectura
- No agrega features no solicitadas
- No viola las convenciones de la Constitution

**⏱ Tiempo total de ejecución:** ~20-30 minutos para el proyecto completo

---

← [Instalación](./03-installation.md) | Siguiente: [Ejercicio práctico →](./05-exercise.md)
