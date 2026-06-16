---
name: council
kind: orchestrator
description: >
  Corre una decisión, idea o pregunta por un council de 5 asesores que la analizan
  por separado, se revisan entre ellos en anónimo y sintetizan un veredicto. Basado en
  el LLM Council de Karpathy. Usalo cuando digas "council esto", "corré el council",
  "war room esto", "pressure-test esto", "no me decido entre X e Y", "¿qué harías?",
  "validá esto", "dame varias miradas". Es el ejemplo de orquestador multi-agente del
  Nivel 5. NO lo uses para preguntas factuales (tienen una sola respuesta), tareas de
  creación ("escribime un tweet") ni "¿debería?" triviales sin un tradeoff real.
---

# council: 5 miradas sobre una decisión

Le preguntás a una IA y te da una respuesta. Puede ser buena o mediocre, y no tenés forma de saberlo porque viste una sola mirada.

El council lo arregla: corre tu pregunta por 5 asesores independientes, cada uno pensando desde un ángulo distinto. Después se revisan entre ellos. Después un chairman sintetiza todo en una recomendación que te dice dónde coinciden, dónde chocan y qué hacer.

Adaptado del LLM Council de Andrej Karpathy: despachar a varios, peer-review anónimo, síntesis del chairman. Acá se hace dentro de Claude con subagentes que tienen lentes distintas, en vez de modelos distintos.

## Rol

Es un **orquestador** (`kind: orchestrator`). Su trabajo es coordinar, no analizar:
1. **Fino:** el hilo principal encuadra, valida, despacha y sintetiza. El pensamiento pesado vive en los subagentes (asesores / reviewers / chairman).
2. **Evalúa a los workers:** la ronda de peer-review anónima ES la evaluación sobre los asesores; el chairman evalúa asesores y reviewers juntos.
3. **Loguea la corrida:** cada sesión cierra con un log JSON (paso 6).

## Cuándo usarlo

El council es para preguntas donde equivocarse sale caro.
- "¿Lanzo un workshop de $97 o un curso de $497?"
- "De estos 3 ángulos de posicionamiento, ¿cuál es el más fuerte?"
- "Estoy pensando en pivotear de X a Y. ¿Estoy loco?"
- "Acá está el copy de mi landing. ¿Qué está flojo?"

## Cuándo NO usarlo
- Preguntas factuales ("¿capital de Francia?"): una sola respuesta correcta.
- Tareas de creación ("escribime un tweet") o de procesamiento ("resumime esto"): no son decisiones.
- "¿Debería?" sin stakes ni tradeoff real.

## Los 5 asesores

No son cargos ni personajes: son estilos de pensar que crean tensión entre sí.

1. **El Contrarian.** Busca qué está mal, qué falta, qué va a fallar. Asume que la idea tiene una falla fatal y la caza. No es pesimista: es el amigo que te salva de un mal negocio.
2. **El de Primeros Principios.** Ignora la pregunta de superficie y pregunta "¿qué estamos tratando de resolver de verdad?". Saca supuestos y rearma el problema desde cero. A veces el mayor aporte es "estás haciendo la pregunta equivocada".
3. **El Expansionista.** Busca el upside que todos se pierden. ¿Qué podría ser más grande? ¿Qué oportunidad adyacente está escondida? No le importa el riesgo (eso es del Contrarian).
4. **El de Afuera.** Cero contexto sobre vos, tu rubro o tu historia. Responde solo a lo que tiene enfrente. El más subestimado: caza la maldición del conocimiento, lo obvio para vos y confuso para el resto.
5. **El Ejecutor.** Solo le importa una cosa: ¿esto se puede hacer y cuál es el camino más rápido? Mira todo con "OK, ¿y el lunes a la mañana qué hago?". Si suena brillante pero no tiene primer paso, lo dice.

**Por qué estos 5:** tres tensiones naturales. Contrarian vs Expansionista (downside vs upside). Primeros Principios vs Ejecutor (repensar todo vs hacerlo ya). El de Afuera en el medio, manteniendo a todos honestos.

## Flujo

### Paso 1: encuadrar la pregunta (con contexto) [LAT]
**A.** Escaneá rápido el workspace por contexto: el `CLAUDE.md` del proyecto, archivos que el usuario referenció, transcripts de councils previos (no recouncilear lo mismo). Máximo ~30 segundos.
**B.** Reformulá la pregunta cruda + el contexto como un prompt claro y neutral que reciben los 5 asesores: (1) la decisión, (2) contexto del usuario, (3) contexto de los archivos, (4) qué está en juego. Sin tu opinión.
**C. Validá con el usuario antes de convocar. Obligatorio.** Mandá la pregunta encuadrada + los 5-10 datos clave que extrajiste + una sola pregunta: "¿Es correcto? ¿Algo que ajustar antes de convocar?". **No lances asesores sin OK explícito.** Una premisa equivocada se propaga por 5 asesores y 5 reviewers y arruina el veredicto.

### Paso 2: convocar al council [FANOUT: 5 subagentes en paralelo]
Lanzá los 5 asesores a la vez (un solo mensaje, 5 llamadas a subagente). Cada uno recibe: su identidad + estilo, la pregunta encuadrada, y la instrucción de responder solo, sin hedging, metiéndose de lleno en su ángulo. 150-300 palabras cada uno.

### Paso 3: peer review [FANOUT: 5 subagentes en paralelo]
Lo que hace que sea más que "preguntar 5 veces". Juntá las 5 respuestas, anonimizalas como Respuesta A-E (randomizá el mapeo para evitar sesgo de posición). Lanzá 5 reviewers; cada uno ve las 5 anónimas y responde: (1) la respuesta más fuerte y por qué, (2) el mayor punto ciego, (3) qué se les escapó a TODAS. Menos de 200 palabras cada uno.

### Paso 4: síntesis del chairman [LAT]
Un agente recibe todo: la pregunta encuadrada, las respuestas de-anonimizadas y los 5 reviews. Produce el VEREDICTO: dónde coincide el council / dónde choca / puntos ciegos cazados / la recomendación / la primera cosa a hacer. El chairman puede ir contra la mayoría si el disidente tiene el mejor razonamiento.

### Paso 5: presentar el veredicto en el chat [DET]
Directo en el chat, en markdown. NO generes HTML ni archivos. Formato:
```
## Veredicto del Council: {tema corto}

### Dónde coincide
### Dónde choca
### Puntos ciegos que cazó
### La recomendación
### La primera cosa a hacer
```
Escaneable, en bullets. El veredicto no puede ser "depende".

### Paso 6: loguear la corrida [DET]
Siempre. Append de la sesión a `skills/council/runs/YYYY-MM-DD.json` (creá `runs/` si no está). Schema:
```json
{
  "fecha": "YYYY-MM-DDTHH:MM",
  "decision": "pregunta encuadrada en una línea",
  "asesores": ["Contrarian", "Primeros Principios", "Expansionista", "De Afuera", "Ejecutor"],
  "veredicto": "recomendación en una línea",
  "disidencias": ["asesor + disidencia en una línea"]
}
```

## Qué lee y escribe
- **Lee:** la pregunta del usuario y, para contexto, el `CLAUDE.md` del proyecto activo + archivos referenciados.
- **Escribe:** el veredicto va al chat. El log siempre a `skills/council/runs/`. El transcript completo, solo si el usuario lo pide (al proyecto activo, o a `output/` si no hay).

## Cuándo NO usar
- Ya cubierto arriba: factual, creación, procesamiento, "¿debería?" trivial. Si hay una sola respuesta correcta, contestala y listo.

## Señales de que lo hiciste bien (chequeo binario)
- [ ] La validación de contexto (paso 1C) pasó ANTES de lanzar ningún asesor, con OK explícito.
- [ ] Las dos rondas corrieron en paralelo (un mensaje, 5 subagentes cada una), no en secuencia.
- [ ] El peer review fue anónimo, con mapeo de letras randomizado.
- [ ] El veredicto tiene las 5 secciones y una recomendación que NO es "depende".
- [ ] No se generaron archivos HTML ni reportes; el veredicto vive en el chat.
- [ ] `skills/council/runs/YYYY-MM-DD.json` tiene la corrida logueada con el schema completo.
