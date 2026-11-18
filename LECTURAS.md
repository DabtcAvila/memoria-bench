# Lecturas

Un punto de partida común. Si encuentras algo mejor, agrégalo en la sección de
fuentes de tu propuesta y lo subimos aquí al homologar.

## Sistemas de memoria

- **OptMem** (Victor Taelin, julio 2026). Notas de una línea en un log al que
  solo se agrega, un árbol de resúmenes y búsqueda con regex. Es un script de
  Python sin dependencias que se instala con un bloque en `AGENTS.md`/`CLAUDE.md`.
  https://github.com/VictorTaelin/OptMem
- **MemPalace** (abril 2026). Memoria vectorial con ChromaDB, organizada con la
  metáfora del "palacio de la memoria". https://github.com/MemPalace/mempalace
- **Mem0.** Extrae hechos con un LLM y los guarda en vectores y grafo. Usa API
  key por defecto. https://github.com/mem0ai/mem0
- **Letta** (antes MemGPT). Memoria por niveles que el propio agente
  administra. https://github.com/letta-ai/letta
- **Graphiti** (Zep). Grafo de conocimiento temporal.
  https://github.com/getzep/graphiti

## Benchmarks

- **LongMemEval** (Wu et al., 2024). 500 preguntas sobre historias de chat
  largas. Mide extracción, razonamiento entre sesiones, razonamiento temporal,
  actualización de conocimiento y abstención. Licencia MIT.
  https://github.com/xiaowu0162/LongMemEval
- **LoCoMo** (Maharana et al., 2024). Conversaciones muy largas entre varias
  sesiones. https://github.com/snap-research/locomo

## El caso que hay que leer: MemPalace y su 96.6 %

MemPalace se anunció con 96.6 % en LongMemEval. Revisiones independientes
mostraron que ese número sale de ChromaDB con sus embeddings por defecto sobre
el texto crudo, no de la arquitectura de MemPalace. Con su compresión propia
(AAAK) baja a 84.2 %. La lección para este proyecto es que **todo número va
contra un baseline tonto, y con instrucciones para repetirlo**.

- Dey y Viradecha (2026), análisis en arXiv: https://arxiv.org/abs/2604.21284
- Vectorize, "MemPalace Benchmarks Debunked" (proveedor competidor; léelo con
  eso en mente): https://vectorize.io/articles/mempalace-benchmarks
