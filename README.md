# memoria-bench

Vamos a comparar **sistemas de memoria para agentes LLM** (OptMem, MemPalace,
`CLAUDE.md` a mano, RAG, grafos, lo que traigas) usando **distintos harnesses**
(Claude Code, Codex, Gemini CLI, Antigravity) y **distintos benchmarks**.

Hay dos reglas fijas:

1. **Nadie paga API keys.** Todo corre con la suscripción que ya tienes.
2. **Todo lo que reportes se tiene que poder repetir.** Un número que nadie más
   puede reproducir no cuenta. Como ejemplo, MemPalace anunció 96.6 % en
   LongMemEval y resultó que el número venía casi todo de ChromaDB (ver
   [`LECTURAS.md`](LECTURAS.md)).

Fuera de eso, cada quien prueba lo que más le interese.

## Cómo funciona

Trabajamos en rondas:

```
leen el repo → llenan su carpeta → PR → mergeamos → HTML en clase
→ votan por PR → homologamos → plan.md → otra ronda
```

Ya probaste cosas por tu cuenta. Esta primera ronda sirve para **homologar**:
que lo que hizo cada quien quede escrito igual, para poder compararlo, repetirlo
y armar entre todos un plan.

## Ronda 1: homologa lo que hiciste

Se trabaja **por fork y pull request**, igual que en el curso: nadie escribe
directo en este repo.

1. Haz fork y clona **tu fork**:

   ```bash
   gh repo fork raya-lucaria/memoria-bench --clone
   cd memoria-bench
   ```

   Antes de cada ronda, actualiza tu `main` con lo que ya se mergeó:
   `git switch main && git pull upstream main && git push`.
2. Crea tu branch: `git switch -c propuesta-<tu-login>`.
3. Abre el repo en tu harness y dile:

   > Lee AGENTS.md y ayúdame a homologar lo que hice en mi propuesta.

   Si tu harness no lee `AGENTS.md` solo, pídeselo explícitamente. Te va a
   entrevistar, revisar lo que ya tienes y llenar
   `estudiantes/<tu-login>/propuesta.md` a partir de
   [`plantillas/propuesta.md`](plantillas/propuesta.md).
4. **Lee lo que escribió antes de subirlo.** El responsable eres tú, no tu IA.
5. Haz push a tu fork y abre el PR hacia `raya-lucaria/memoria-bench`, titulado
   `propuesta: <tu-login>` (`git push -u origin propuesta-<tu-login>` y luego
   `gh pr create`).

**Todo lo tuyo vive en `estudiantes/<tu-login>/`**, y esa carpeta se llama
exactamente como tu login de GitHub. Solo escribes dentro de ella. Las reglas
completas están en [`estudiantes/README.md`](estudiantes/README.md).

## Después

- Mergeamos los PRs y armamos un HTML con todas las propuestas para verlo en
  clase.
- Homologamos: agrupamos memorias, benchmarks y preguntas, y vemos qué choca y
  qué falta.
- Lo que haya que decidir se vota: subimos `plantillas/boleta.yaml`, cada quien
  la copia a `estudiantes/<tu-login>/votos.yaml`, la llena con su harness y abre
  un PR `votos: <tu-login>`.
- Con eso queda `plan.md`: qué se mide, cómo, quién se encarga de qué, y qué se
  repite entre varias personas para que el resultado sea robusto.

## Archivos

| Archivo | Para qué |
|---|---|
| [`AGENTS.md`](AGENTS.md) | instrucciones para tu IA (`CLAUDE.md` y `GEMINI.md` apuntan aquí) |
| [`estudiantes/`](estudiantes/README.md) | una carpeta por persona; ahí trabaja cada quien |
| [`plantillas/`](plantillas/propuesta.md) | la forma común de la propuesta (y luego de la boleta) |
| [`LECTURAS.md`](LECTURAS.md) | punto de partida común: sistemas, benchmarks, críticas |
| `plan.md` | el plan homologado, a partir de la ronda 2 |
