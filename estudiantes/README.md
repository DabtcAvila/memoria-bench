# estudiantes

Una carpeta por persona. **La tuya se llama exactamente como tu usuario de
GitHub**, con sus mismas mayúsculas y sus mismos guiones. Así nadie choca con
nadie.

Ese nombre no se teclea, se obtiene:

```bash
gh api user --jq .login          # tu login
mkdir -p estudiantes/<tu-login>
```

## Las reglas

1. Solo escribes dentro de `estudiantes/<tu-login>/`. Nada fuera.
2. Una branch por ronda (`propuesta-<tu-login>`, `votos-<tu-login>`). Nunca
   desde `main`.
3. Nada de `.env`, API keys, `.DS_Store`, `__pycache__/`, `.venv/` ni
   `node_modules/`.
4. Si te piden corregir un PR, haces `push` a la misma branch. No abras otro.

## Qué va en tu carpeta

```
estudiantes/<tu-login>/
  propuesta.md     ronda 1, copiada de plantillas/propuesta.md
  evidencia/       logs, salidas, notas de lo que corriste (saneado, < ~1 MB)
  votos.yaml       ronda 2, copiada de plantillas/boleta.yaml cuando exista
  …                lo que quieras: notebooks, scripts, notas
```
