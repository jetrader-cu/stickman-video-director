# AGENTS.md — stickman-video-director

- Skill instalable: `skills/directing-stickman-videos/` (también plugin de Claude Code vía `.claude-plugin/`).
- Comportamiento original (inglés, Gemini Omni Flash, puerta de configuración y aprobación de la Fase A) NO se rompe: las
  extensiones de la empresa (brand packs, español, render local HyperFrames) son opcionales y viven en `references/`.
- Los README multilingües se verifican con `bash tests/verify-readmes.sh`: no edites secciones sin replicarlas en todos los
  idiomas. La documentación de la empresa va en `docs/integracion-empresa.md`.
- Escenarios de evaluación en `tests/scenarios/`; rúbrica en `tests/evaluation-rubric.md`.
- Integración con las apps: ver `docs/integracion-empresa.md` y la skill `co-stickman-videos` del kit `ai-swarm` de cada repo.
