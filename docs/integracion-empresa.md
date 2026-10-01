# Integración con el enjambre IA de la empresa

Este repo (fork de `kaomei/stickman-video-director`, MIT) se usa para vídeos explicativos con monigotes de QvaArbi, FulaYa
y CuadraYa. La versión 1.1.0 añade, sin romper el comportamiento original:

| Cambio | Archivo |
|---|---|
| Plugin de Claude Code (marketplace propio) | `.claude-plugin/marketplace.json`, `.claude-plugin/plugin.json` |
| Brand packs y narración en otros idiomas (español de Cuba) | `skills/directing-stickman-videos/references/brand-and-language.md` |
| Render local con HyperFrames cuando el modelo de vídeo no está disponible (Gemini no opera en Cuba) | `skills/directing-stickman-videos/references/local-render-hyperframes.md` |
| Escenario de evaluación | `tests/scenarios/language-and-brand.md` |

## Instalar

```bash
claude plugin marketplace add jetrader-cu/stickman-video-director
claude plugin install stickman-video-director@stickman-video-director
# Codex: cp -R skills/directing-stickman-videos "${CODEX_HOME:-$HOME/.codex}/skills/"
# OpenCode / Antigravity: cp -R skills/directing-stickman-videos ~/.agents/skills/
```

## Uso con las apps

Los brand packs viven en los repos de las apps: `ai-swarm/brands/<slug>.json` (skill `co-brand-kits`). Guía completa:
`docs/ai-swarm/14-voces-avatares-stickman-remix.md` y skill `co-stickman-videos` en cualquiera de los 4 repos.

## Sincronizar con el original

`git remote add upstream https://github.com/kaomei/stickman-video-director && git fetch upstream && git merge upstream/main`.
Los cambios propios están aislados en archivos nuevos y en una sección de `SKILL.md`, para que los merges sean simples.
