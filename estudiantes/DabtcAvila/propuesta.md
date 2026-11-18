---
# Copia este archivo a estudiantes/<tu-login>/propuesta.md.
#
# PARTE ESTÁNDAR (este bloque): igual para todos. Con ella juntamos las
# propuestas, acordamos qué hacemos y repartimos el trabajo. Llena todo lo que
# puedas; si no sabes algo, pon "no-se". Usa los ids de AGENTS.md cuando
# encajen; si no, escribe el nombre como tú lo llames.
#
# PARTE LIBRE (debajo del bloque): escribe como quieras.

login: "DabtcAvila"
harnesses: [claude-code]
suscripciones: ["Claude (suscripción)"]
sistema_operativo: "macos"

# Una entrada por memoria que investigaste.
memorias:
  - id: "ninguna"
    tipo: [ninguna]
    fuente: ""
    sin_api_key: si
    facilidad: facil
    interes: 3            # es el baseline de todo

  - id: "claude-md-manual"
    tipo: [archivo-instrucciones]
    fuente: "https://code.claude.com/docs/en/memory"
    sin_api_key: si
    facilidad: facil
    interes: 3

  - id: "nativa-claude-code"
    tipo: [nativa, notas]
    fuente: "https://code.claude.com/docs/en/memory"
    sin_api_key: si
    facilidad: facil      # viene activada; es la que uso a diario
    interes: 3

  - id: "optmem"
    tipo: [notas, resumen-jerarquico]
    fuente: "https://github.com/VictorTaelin/OptMem"
    sin_api_key: si       # un script sin dependencias; el propio agente resume. Sin verificar instalándolo
    facilidad: no-se
    interes: 3

  - id: "llm-wiki"
    tipo: [notas]
    fuente: "https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f"
    sin_api_key: si       # es un patrón de archivos markdown, no un producto
    facilidad: no-se
    interes: 2

  - id: "logs-crudos-grep"
    tipo: [logs-crudos]
    fuente: "https://arxiv.org/abs/2610.29823"   # MemoryTax: harness + historial en un archivo
    sin_api_key: si
    facilidad: facil
    interes: 3

  - id: "bm25"
    tipo: [logs-crudos]   # búsqueda léxica sobre texto crudo; baseline "tonto" de recuperación
    fuente: "https://arxiv.org/html/2507.05257v3"
    sin_api_key: si
    facilidad: no-se
    interes: 2

  - id: "mempalace"
    tipo: [vectorial]
    fuente: "https://github.com/MemPalace/mempalace"
    sin_api_key: no-se    # ChromaDB local por defecto; sin verificar
    facilidad: no-se
    interes: 2

  - id: "mem0"
    tipo: [vectorial, grafo]
    fuente: "https://github.com/mem0ai/mem0"
    sin_api_key: "no"     # extrae con un LLM; API key por defecto. Sin verificar con Ollama
    facilidad: no-se
    interes: 1

  - id: "letta"
    tipo: [notas, nativa]  # desde feb-2026 su memoria son archivos markdown en git (MemFS)
    fuente: "https://www.letta.com/blog/context-repositories"
    sin_api_key: no-se
    facilidad: no-se
    interes: 1

  - id: "graphiti"
    tipo: [grafo]
    fuente: "https://github.com/getzep/graphiti"
    sin_api_key: no-se    # construir el grafo usa un LLM; sin verificar con modelo local
    facilidad: no-se
    interes: 1

  - id: "hindsight"
    tipo: [grafo, vectorial]
    fuente: "https://github.com/vectorize-io/hindsight"
    sin_api_key: no-se
    facilidad: no-se
    interes: 1

  - id: "mastra-memoria-observacional"
    tipo: [resumen-jerarquico]   # un observador convierte mensajes en observaciones fechadas; solo texto
    fuente: "https://mastra.ai/research/observational-memory"
    sin_api_key: no-se
    facilidad: no-se
    interes: 1

  - id: "claude-mem"
    tipo: [logs-crudos, vectorial]   # hooks que capturan todo + observador que resume
    fuente: "https://github.com/thedotmack/claude-mem"
    sin_api_key: no-se
    facilidad: no-se
    interes: 1

# Una entrada por benchmark que investigaste o que propones.
benchmarks:
  - id: "longmemeval"
    mide: "recuerdo en historiales de chat largos: extracción, entre sesiones, temporal, actualización y abstención"
    fuente: "https://github.com/xiaowu0162/LongMemEval"
    calificacion: llm-juez
    casos: "500"
    cabe_en_suscripcion: no-se   # unos 115 mil tokens de historial por pregunta
    interes: 2

  - id: "locomo"
    mide: "preguntas sobre conversaciones largas entre dos personas (un dato, varios datos, temporal)"
    fuente: "https://github.com/snap-research/locomo"
    calificacion: llm-juez       # el artículo usa F1; los vendedores usan juez. 6.4 % de la clave está mal
    casos: "1540 útiles; una sola conversación = 152"
    cabe_en_suscripcion: no-se   # una conversación (152 preguntas) probablemente sí; sin verificar
    interes: 2

  - id: "longmemeval-v2"
    mide: "memoria de la experiencia de un agente: estado, flujos de trabajo, trampas del entorno"
    fuente: "https://xiaowu0162.github.io/longmemeval-v2/"
    calificacion: no-se
    casos: "451"
    cabe_en_suscripcion: "no"    # historiales de 25 a 115 millones de tokens
    interes: 1

  - id: "beam"
    mide: "diez habilidades de memoria en historiales de 100 mil a 10 millones de tokens"
    fuente: "https://arxiv.org/html/2510.27246v1"
    calificacion: llm-juez
    casos: "2000 preguntas sobre 100 conversaciones"
    cabe_en_suscripcion: no-se
    interes: 1

  - id: "memoryagentbench"
    mide: "recuperar, aprender sobre la marcha, entender a largo plazo y olvidar lo que cambió"
    fuente: "https://arxiv.org/html/2507.05257v3"
    calificacion: automatica     # exactitud, F1 y recall según la tarea
    casos: no-se
    cabe_en_suscripcion: no-se
    interes: 2

  - id: "swe-contextbench"
    mide: "si un agente de código reutiliza la experiencia de un problema anterior relacionado"
    fuente: "https://arxiv.org/html/2602.08316v3"
    calificacion: automatica     # pruebas ejecutables
    casos: "1100 base + 376 relacionadas; versión Lite = 99"
    cabe_en_suscripcion: no-se
    interes: 2

  - id: "vibemembench"
    mide: "si un sistema de memoria ayuda a resolver tareas reales de repositorio"
    fuente: "https://arxiv.org/html/2609.23570"
    calificacion: automatica
    casos: "111 tareas, 3634 trayectorias de historia"
    cabe_en_suscripcion: no-se
    interes: 2

  - id: "dreambench-swe"
    mide: "higiene de memoria: tareas que dependen de algo dicho en sesiones anteriores"
    fuente: "https://arxiv.org/abs/2608.20664"
    calificacion: automatica     # oráculos ejecutables ocultos
    casos: "180"
    cabe_en_suscripcion: no-se
    interes: 2

  - id: "capa"
    mide: "si el asistente deja de preguntar lo que el mismo usuario ya aclaró en sesiones pasadas"
    fuente: "https://arxiv.org/html/2607.26611"
    calificacion: automatica
    casos: "600 sesiones, 300 de evaluación"
    cabe_en_suscripcion: no-se
    interes: 2

  - id: "coremem-chainswe"
    mide: "cadenas de tareas de código donde lo aprendido en una sirve en la siguiente"
    fuente: "https://arxiv.org/abs/2611.17316"
    calificacion: automatica
    casos: "48 cadenas en el conjunto de prueba"
    cabe_en_suscripcion: no-se
    interes: 2

  - id: "memorytax"
    mide: "acierto y costo por pregunta de cada forma de memoria, con el mismo modelo"
    fuente: "https://arxiv.org/abs/2610.29823"
    calificacion: llm-juez
    casos: "152 (una conversación de LoCoMo)"
    cabe_en_suscripcion: no-se   # es el más chico de todos; candidato a replicar
    interes: 3

  - id: "propio-continuidad"
    mide: "continuidad de trabajo entre sesiones: contestar con un dato que solo está en la memoria del proyecto, y cuánto cuesta encontrarlo"
    fuente: "propio"
    calificacion: automatica     # script contra clave fija, sin juez
    casos: "20 preguntas (10 dentro de un proyecto, 10 que cruzan proyectos)"
    cabe_en_suscripcion: si      # versión mínima: 180 corridas cortas; sin verificar el consumo real
    interes: 3

# Una entrada por experimento que propones: una pregunta que se pueda contestar midiendo.
experimentos:
  - pregunta: "¿La memoria nativa por proyecto de Claude Code contesta más preguntas de continuidad entre sesiones que un CLAUDE.md a mano y que no tener memoria, y con cuántos tokens de arranque?"
    memorias: [ninguna, claude-md-manual, nativa-claude-code]
    harnesses: [claude-code]
    benchmark: "propio-continuidad"
    por_que_interesa: "Es la memoria que ya viene con el harness y no cuesta nada instalar. Si no le gana a un archivo a mano, lo demás sobra. En SCLATE (sep-2026) la nativa de Claude Code subió de 48.0 a 60.6 % con 0.92× los tokens, pero con modelos de la generación anterior."

  - pregunta: "¿Una memoria unificada entre proyectos contesta mejor las preguntas que cruzan proyectos que memorias separadas por proyecto, o que separadas más un índice corto de punteros, sin subir el contexto de arranque más de 20 %?"
    memorias: [nativa-claude-code, claude-md-manual, llm-wiki]
    harnesses: [claude-code]
    benchmark: "propio-continuidad"
    por_que_interesa: "Cuatro de ocho harness guardan memoria global y Claude Code la guarda por proyecto. En mi uso real solo 7.7 % de las sesiones leyó memoria de otro proyecto, y un índice unificado pesaría 6.4 veces el tope de 25 KB. Falta medir si unificar mejora el acierto."

  - pregunta: "¿Un harness que busca con grep en el historial crudo iguala a OptMem y a BM25 en una conversación de LoCoMo, y cuántos tokens gasta cada uno?"
    memorias: [ninguna, logs-crudos-grep, bm25, optmem]
    harnesses: [claude-code, codex, gemini-cli]
    benchmark: "locomo"
    por_que_interesa: "Replica MemoryTax (oct-2026) solo con suscripción y agrega OptMem, que no tiene ninguna evaluación publicada. Ahí, con Opus 5.5, Claude Code sobre un archivo sacó 97 % contra 95 % de Mem0 y 90 % de BM25. Es chico: 152 preguntas."

  - pregunta: "Con la misma memoria en archivos, ¿cuánto cambia el acierto al cambiar solo el modelo dentro del mismo harness?"
    memorias: [ninguna, logs-crudos-grep]
    harnesses: [claude-code]
    benchmark: "locomo"
    por_que_interesa: "Si el modelo mueve más que la memoria, comparar memorias con modelos distintos no dice nada. En MemoryTax, Claude Code fue de 29 % con un modelo débil a 97 % con uno fuerte; con Mem0 el rango fue de 17 puntos."

  - pregunta: "¿Un resumen curado de la sesión anterior sirve más que la transcripción completa para continuar una tarea de código?"
    memorias: [ninguna, logs-crudos-grep, nativa-claude-code]
    harnesses: [claude-code]
    benchmark: "propio-continuidad"
    por_que_interesa: "En SWE-ContextBench el resumen correcto subió el acierto de 26.3 a 34.3 % y la trayectoria completa lo dejó en 27.3 %. Decide si conviene guardar todo o guardar poco y bien."

# Para repartir. Elige de la lista; puedes poner varios.
roles: [armar-benchmark, analisis-y-graficas]
quiero_encargarme_de: ["armar propio-continuidad: preguntas con clave fija y calificación por script", "tablas y web de números comparables", "medir uso real de la memoria nativa con medir.py"]
disponibilidad: media
---

# Propuesta de DabtcAvila

## Mi scouting

Investigué con Claude Code el 17-nov-2026: qué benchmarks de memoria existen,
qué puntajes reporta cada sistema y quién los midió, y qué hay publicado con los
modelos vigentes. Todo está tal cual en [`scouting/`](scouting/):

| Archivo | Qué es |
|---|---|
| [`scouting/numeros.html`](scouting/numeros.html) | Web de números: 492 filas filtrables por categoría, benchmark, vigencia del modelo y quién midió. Se abre en el navegador, sin servidor |
| [`scouting/informes/`](scouting/informes/) | Las cinco salidas originales de los subagentes de investigación, con URL por cifra |
| [`scouting/medir.py`](scouting/medir.py) | Script de solo lectura que mide el uso real de la memoria nativa de Claude Code. No llama a ningún modelo |
| [`scouting/medicion-uso-real-2026-11-17.json`](scouting/medicion-uso-real-2026-11-17.json) | Su salida en una máquina, con nombres de proyecto anonimizados |

Nadie ha corrido ningún benchmark todavía. Lo único medido por mí es el uso real
(183 sesiones); todo lo demás son cifras de terceros.

## Lo que encontré

**Sobre las cifras.** Los subagentes leyeron cada página a través de un
resumidor automático, así que cada número debe verificarse en su fuente antes de
citarlo. En los informes, `[P]` o `[V]` significa leído en la página y `[S]`
solo visto en un fragmento de búsqueda. Casi todos los puntajes de vendedores
son autorreportados.

**Los benchmarks de chat ya no ordenan sistemas.** Fuente:
<https://github.com/dial481/locomo-audit>.

- En LoCoMo, 99 de 1,540 respuestas de la clave están mal (techo de 93.6 %).
- El juez habitual aceptó 63 % de respuestas falsas a propósito.
- Un modelo con todo el contexto y una buena instrucción sacó 92.6 %, sin
  ningún sistema de memoria.

**Cuando mide alguien independiente, lo simple compite.**

| Estudio | Resultado | Fuente |
|---|---|---|
| MemoryAgentBench (2025) | BM25 41.5, contexto largo 48.8, Mem0 21.1, Zep 24.0 | <https://arxiv.org/html/2507.05257v3> |
| VibeMemBench (sep-2026) | 11 de 12 combinaciones con producto de memoria quedaron bajo el agente sin memoria | <https://arxiv.org/html/2609.23570> |
| MemoryTax (oct-2026), Opus 5.5 | Claude Code sobre un archivo 97 %, Mem0 95 %, todo en contexto 95 %, BM25 90 %, Zep 87 % | <https://arxiv.org/abs/2610.29823> |
| CoReMem (nov-2026), Opus 5.5 | Sin memoria 38.5 %, Mem0 39.6 %, historial completo 40.6 % | <https://arxiv.org/abs/2611.17316> |

**Cargar más contexto fijo cuesta y no mejora.** Con archivos tipo AGENTS.md
generados, el costo sube 20 a 23 % y el acierto cambia entre −2.0 y +2.4 puntos,
sin significancia (<https://arxiv.org/html/2602.11988>).

**El modelo pesa mucho.** En MemoryTax, el mismo harness sobre archivos va de
29 % a 97 % según el modelo. Por eso propongo fijar el modelo en cada
comparación.

**Huecos con modelos vigentes al 17-nov-2026.**

- GPT-6.2 Astra y Sol salieron hoy y no tienen ninguna medición de memoria.
- Ninguna ficha de modelo de los laboratorios trae una evaluación de memoria.
- La tabla pública de LongMemEval-V2 no tiene entradas.
- OptMem no tiene ninguna evaluación publicada de ningún tipo.

**Uso real medido (una máquina, un usuario, 15-oct al 17-nov-2026).**

| Métrica | Valor |
|---|---|
| Sesiones que leyeron memoria de otro proyecto | 14 de 183 (7.7 %) |
| Llamadas de memoria que fueron a otro proyecto | 35 de 1,714 (2.0 %) |
| Índice unificado contra el tope de 25 KB que carga Claude Code | 160 KB, 6.4 veces |
| Contexto al arrancar, mediana | 62,630 tokens |
| Memorias abiertas al menos una vez por una herramienta | 330 de 605 (cota inferior) |

El script solo ve lo que el agente fue a buscar; no ve lo que omitió sin darse
cuenta.

**De qué desconfío.**

- Del 73.3 % de FrontierMemory: lo reporta Letta y su producto queda primero.
- De los 98 % en LongMemEval de vendedores nuevos: autorreportados.
- De mis propias tablas, hasta que alguien repita las cifras desde la fuente.

## Experimentos que propongo

**Benchmark propio, `propio-continuidad`.** Los benchmarks públicos preguntan
«¿recuerdas el dato?». Lo que me interesa es «¿puedes continuar el trabajo?».

- **Tareas:** 20 preguntas cuya respuesta solo está en la memoria (10 dentro de
  un proyecto, 10 que cruzan proyectos), sobre un conjunto sintético de
  proyectos que cualquiera pueda clonar.
- **Calificación:** un script contra una clave fija, sin juez automático.
- **Métricas:** éxito, omisiones, llamadas hasta el primer dato correcto,
  tokens al arrancar, tokens totales y tiempo.
- **Tamaño:** versión mínima de 180 corridas (20 preguntas × 3 condiciones × 3
  repeticiones). Con ese tamaño solo se distinguen diferencias de 15 puntos o
  más; es una estimación mía, sin verificar.
- **Agnóstico:** la memoria es una carpeta de texto y cada harness la recibe por
  su archivo de instrucciones (`CLAUDE.md`, `AGENTS.md`, `GEMINI.md`).

**Cómo sabríamos si salió bien.** Para cada experimento, la condición nueva
gana si sube el éxito más de 5 puntos o baja las omisiones más de 10, sin subir
el contexto de arranque más de 20 %. Son umbrales propuestos, ajustables al
homologar.

**Replicar MemoryTax con suscripción** (experimento 3) es el más barato y el
que más aporta al grupo: 152 preguntas, comparación directa entre harness, y de
paso sería la primera cifra publicada de OptMem. Solo tengo Claude Code; Codex y
Gemini CLI los tendría que correr alguien más.

## Preguntas y dudas

- ¿Cuántas corridas aguanta una suscripción antes del límite? No lo he medido;
  define el tamaño real de todo.
- LoCoMo se califica con juez. ¿Usamos coincidencia contra la clave corregida
  de la auditoría, para no depender de un juez?
- ¿Fijamos un modelo por harness para todo el grupo? Sin eso, las cifras de
  cada quien no se pueden comparar.
- `medir.py` solo lee el formato de Claude Code. ¿Alguien con Codex o Gemini CLI
  quiere escribir el adaptador para sus transcripciones?
