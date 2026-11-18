---
# Copia este archivo a propuestas/<tu-login>/propuesta.md y llénalo.
# Usa los ids de AGENTS.md. Lo que no esté ahí va en ids_nuevos.
login: ""
harnesses: []          # p. ej. [claude-code, codex]
modelos: []            # el nombre exacto que reporte tu harness, p. ej. [claude-sonnet-5-5]
suscripciones: []      # p. ej. ["Claude Pro", "ChatGPT Plus", "Google AI gratis"]
sistema_operativo: ""  # linux | macos | windows | wsl
memorias_probadas: []  # ids de sistemas, p. ej. [optmem, claude-md-manual]
benchmarks_usados: []  # ids, p. ej. [longmemeval, propio-recetas]
memorias_que_me_interesan: []
benchmarks_que_propongo: []
quiero_encargarme_de: []   # texto libre corto, p. ej. ["driver de codex", "benchmark de convenciones"]
ids_nuevos: []         # - {id: mi-memoria, tipo: vectorial, fuente: https://...}
---

# Propuesta de <login>

## 1. Lo que hice

Repite este bloque por cada cosa que probaste.

### <título corto>

- **Memoria:** id(s)
- **Harness y modelo:**
- **Benchmark o tarea:** id, o descríbela si fue informal
- **Qué hice:** en pocas líneas
- **Qué salió:** números si los hay, con su unidad. Si no mediste: "no medido".
- **Evidencia:** archivos en `evidencia/`, o "sin evidencia"
- **Cómo repetirlo:** comandos o pasos exactos para que otra persona llegue a lo
  mismo. Si no se puede, explica por qué.
- **Qué salió mal o me sorprendió:**

## 2. Lo que propongo

- **Qué comparación quiero ver** (memoria × harness × benchmark) y por qué me
  interesa:
- **Mi hipótesis:** qué espero que pase, escrita antes de medir.
- **Benchmark que propongo** (si propones uno): qué mide, cómo se califica sin
  un LLM de juez y cuántos casos tiene. Debe caber en la cuota de una
  suscripción.
- **De qué me quiero encargar:**

## 3. Lo que no sé o me preocupa

## 4. Fuentes
