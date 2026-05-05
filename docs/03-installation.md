# ⚙️ Instalación y configuración

← [El flujo SDD](./02-sdd-flow.md) | Siguiente: [Demo →](./04-demo.md)

---

## Prerrequisitos

- Python 3.11+
- [`uv`](https://docs.astral.sh/uv/) (recomendado) o `pipx`
- Git
- Un agente de IA compatible (GitHub Copilot, Claude Code, Cursor, Windsurf…)

## Instalación persistente (recomendada)

```bash
# Instalar una release estable (sustituye vX.Y.Z por la versión más reciente)
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git@vX.Y.Z

# Verificar instalación
specify version

# Comprobar herramientas disponibles
specify check
```

## Inicializar un proyecto nuevo

```bash
# Proyecto nuevo
specify init <NOMBRE_PROYECTO>

# En un repositorio existente
specify init . --integration copilot
# o
specify init --here --integration copilot
```

## Actualizar Spec Kit

```bash
uv tool install specify-cli --force --from git+https://github.com/github/spec-kit.git@vX.Y.Z
```

## Agentes de IA soportados (30+)

| Agente | Directorio de comandos |
|--------|------------------------|
| GitHub Copilot | `.github/agents/` |
| Claude Code | `.claude/commands/` |
| Cursor | `.cursor/commands/` |
| Windsurf | `.windsurf/workflows/` |
| Gemini CLI | `.gemini/commands/` |
| Amazon Q Developer CLI | `.amazonq/prompts/` |
| Codex CLI | `.codex/commands/` |

> Spec Kit **no reemplaza** ningún agente ni skill existente. Añade sus comandos `/speckit.*` encima sin interferir con lo que ya tengas configurado. El namespace `speckit.*` está dedicado y no colisiona con otros comandos.

Ver la lista completa en [Supported AI Integrations](https://github.github.io/spec-kit/reference/integrations.html).

## Instalación en entornos air-gapped / empresa

Para entornos sin acceso a PyPI o GitHub, consulta la guía [Enterprise / Air-Gapped Installation](https://github.com/github/spec-kit/blob/main/docs/installation.md#enterprise--air-gapped-installation).

---

← [El flujo SDD](./02-sdd-flow.md) | Siguiente: [Demo →](./04-demo.md)
