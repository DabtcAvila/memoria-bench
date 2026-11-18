---
# Copia este archivo a estudiantes/<tu-login>/propuesta.md.
#
# PARTE ESTÁNDAR (este bloque): igual para todos. Con ella juntamos las
# propuestas, acordamos qué hacemos y repartimos el trabajo. Llena todo lo que
# puedas; si no sabes algo, pon "no-se". Usa los ids de AGENTS.md cuando
# encajen; si no, escribe el nombre como tú lo llames.
#
# PARTE LIBRE (debajo del bloque): escribe como quieras.

login: ""
harnesses: []            # los que tienes con suscripción: claude-code | codex | gemini-cli | antigravity | ...
suscripciones: []        # p. ej. ["Claude Pro", "ChatGPT Plus", "Google AI gratis"]
sistema_operativo: ""    # linux | macos | windows | wsl

# Una entrada por memoria que investigaste.
memorias:
  - id: ""               # p. ej. optmem
    tipo: []             # tipos de AGENTS.md, p. ej. [notas, resumen-jerarquico]
    fuente: ""           # URL
    sin_api_key: no-se   # si | no | no-se   (¿corre solo con tu suscripción?)
    facilidad: no-se     # facil | media | dificil | no-se   (de instalar y probar)
    interes: 2           # 1 bajo | 2 medio | 3 alto   (qué tanto te interesa probarla)

# Una entrada por benchmark que investigaste o que propones.
benchmarks:
  - id: ""               # p. ej. longmemeval, o propio-<nombre>
    mide: ""             # una línea: qué habilidad de memoria
    fuente: ""           # URL, o "propio"
    calificacion: no-se  # automatica | llm-juez | manual | no-se
    casos: no-se         # cuántos casos tiene o tendría
    cabe_en_suscripcion: no-se   # si | no | no-se
    interes: 2

# Una entrada por experimento que propones: una pregunta que se pueda contestar midiendo.
experimentos:
  - pregunta: ""         # p. ej. "¿OptMem recuerda mejor que un CLAUDE.md a mano después de 5 sesiones?"
    memorias: []         # ids, incluye el baseline contra el que comparas (p. ej. ninguna)
    harnesses: []
    benchmark: ""
    por_que_interesa: ""

# Para repartir. Elige de la lista; puedes poner varios.
roles: []                # probar-memoria | integrar-harness | armar-benchmark | motor-comun |
                         # analisis-y-graficas | documentacion
quiero_encargarme_de: [] # texto libre corto, p. ej. ["probar OptMem en Codex"]
disponibilidad: media    # baja | media | alta
---

# Propuesta de <login>

Escribe libre. Estas secciones son una guía, no un formulario.

## Mi scouting

Qué investigaste y por qué te llamó la atención. Si ya tienes notas,
documentos o conversaciones con tu IA, súbelos **tal cual** a
`estudiantes/<tu-login>/scouting/` y aquí solo resume y enlaza.

## Lo que encontré

Lo que no cupo arriba: cómo funciona cada cosa, qué te sorprendió, qué
desconfías de lo que leíste.

## Experimentos que propongo

Explica con calma los de arriba: por qué serían interesantes y cómo sabríamos
si salió bien.

## Preguntas y dudas
