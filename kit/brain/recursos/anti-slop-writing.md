<!--
  anti-slop-writing.md: la doctrina completa detrás del skill `anti-slop`.
  Al instalar va a tu brain como `3. Recursos/anti-slop-writing.md`. El skill `anti-slop`
  la lee cuando la tenés; sin ella igual funciona, pero con ella afina mejor.
  Es referencia (gusto + ejemplos), no un skill: no se dispara sola.
-->

# Anti-slop writing: reglas de higiene

Cómo sacar los patrones que delatan que un texto lo escribió un LLM. Aplica a todo lo que sale de tu asistente bajo tu nombre o como contenido publicable: emails largos, reportes, briefs, contenido SEO, posts, presentaciones.

No reemplaza tu voz (la que vive en `2. Áreas/yo/mi-estilo.md`). Esto es la pasada de higiene que va después: primero escribís con tu voz, después le sacás lo que suena a máquina.

Inspirado en guías públicas de anti-AI-slop. Acá quedan las 5 reglas que pasan el filtro de utilidad real, adaptadas a español rioplatense.

---

## Regla 1: Reframe ban (negative parallelism)

El patrón "no es X, es Y" es probablemente el tell #1 de texto generado por LLM. Aparece porque el modelo aprendió que crea sensación de profundidad. Es muletilla.

### El patrón a cazar

Cualquier oración, par de oraciones, párrafo o título que:
1. Niegue, minimice o desestime una idea X
2. Y la reemplace con Y

Aplica aunque no aparezca la palabra "no". Aplica cruzando oraciones.

### Formas obvias

- "Esto no es X. Es Y."
- "No se trata de X. Se trata de Y."
- "Olvidate de X. Pensá en Y."
- "Menos X, más Y."
- "X está muerto. Y es el futuro."
- "La pregunta no es X. La pregunta es Y."
- "El problema no es X. Es Y."
- "Nunca fue sobre X. Siempre fue sobre Y."
- "X parece el problema. El problema real es Y."

### Formas sneaky (mismo patrón, palabras suaves)

- "A primera vista, X..." (y después pivotea a Y)
- "La mayoría piensa X..." (pivotea)
- "X parece correcto, pero..."
- "Mientras que X aparenta..."

Si después del setup viene "pero / sin embargo / en realidad / lo cierto es / lo que importa es / lo que pasa es", reescribir.

### El fix

Borrar la mitad rechazada. Reescribir solo la afirmación positiva como oración directa.

**Mal:** "No es un problema de productividad. Es un problema de atención."
**Bien:** "El cuello de botella es la atención."

**Mal:** "El dashboard no es una herramienta de reporting. Es un filtro de decisiones."
**Bien:** "El dashboard filtra decisiones."

**Mal:** "La gente culpa al algoritmo. Los datos de input están rotos."
**Bien:** "Los datos de input están rotos."

### Cuándo sí está OK contrastar

Solo para corregir un dato concreto: fecha, número, nombre, alcance, distinción técnica.

- "La reunión es el martes, no el jueves." ✅
- "El archivo pesa 12 MB, no 12 GB." ✅
- "Es deadline civil, no penal." ✅

---

## Regla 2: Verbos metafóricos para trabajo abstracto

Cuando hablás de ideas, estrategia, productos, organizaciones o emociones, ciertos verbos meten metáfora donde no hace falta. Son adornos.

### Lista negra (español)

- destilar
- anclar
- desempacar
- cristalizar
- subrayar (en sentido de "destacar")
- amplificar
- sembrar
- forjar
- tejer
- moldear
- esculpir
- cementar
- tender un puente
- iluminar (en sentido figurado)
- catalizar

### Lista negra (inglés, para texto bilingüe)

- distill, anchor, unpack, crystallize, surface, amplify, channel, frame, map, sharpen, mold, sculpt, cement, bridge, weave, thread, scaffold

### El fix

Usar verbos literales:

- explicar, mostrar, decir, listar, comparar, elegir, sacar, agregar, cambiar, juntar, separar, reducir, fijar, definir, nombrar

**Mal:** "Vamos a destilar los aprendizajes del trimestre."
**Bien:** "Resumimos los 3 aprendizajes del trimestre."

**Mal:** "El producto teje sales y soporte."
**Bien:** "El producto deja que sales y soporte vean las mismas notas del cliente."

---

## Regla 3: Puffery y fake depth con participios

El modelo infla cada hecho normal en algo trascendente. También cuelga participios genéricos al final ("subrayando su importancia") que parecen análisis pero no dicen nada.

### Puffery a cortar

- "un punto de inflexión clave"
- "un momento decisivo"
- "un cambio fundamental"
- "marcando una evolución importante"
- "implicaciones más amplias"
- "sentando las bases para"

Decir el hecho. Que el lector mida el peso.

### Participios decorativos a cortar

- "subrayando su importancia"
- "destacando su significado"
- "reflejando tendencias más amplias"
- "contribuyendo a una historia rica"
- "abriendo el camino para"
- "abriendo la puerta a"

Si el análisis importa, le toca su propia oración con un claim concreto.

**Mal:** "El producto tuvo un crecimiento importante este trimestre, marcando un punto de inflexión clave para la compañía."
**Bien:** "El producto creció 40% este trimestre. Pasamos de 200 a 280 clientes."

---

## Regla 4: Vocabulario muerto

Palabras que en abstracto suenan bien y en concreto no aportan. Si el contexto es técnico/financiero y la palabra es la exacta (ej. "leverage" en finanzas, "harness" cuando hablás de un harness real), están permitidas. El test es: ¿hay una palabra más simple que dice lo mismo sin perder precisión? Si sí, reemplazar.

### Lista corta (las que más aparecen en outputs LLM en español)

- aprovechar (cuando es decorativo, no cuando significa "usar X como palanca")
- potenciar
- impulsar
- robusto
- escalable (fuera de contexto técnico)
- transformador
- disruptivo
- holístico
- sinérgico
- innovador (vacío en 9 de 10 casos)
- pionero
- vanguardia
- fluido / sin fricción
- intuitivo
- empoderar
- visionario
- estratégico (cuando es muletilla)

### Lista corta (inglés, para texto bilingüe)

- leverage (decorativo), unlock, harness, delve, realm, intricate, robust, scalable, holistic, synergize, innovative, transformative, seamless, intuitive, empower, streamline, supercharge, game-changer, cutting-edge

### El fix

Reemplazar con la palabra plana o cortar.

**Mal:** "Vamos a aprovechar la sinergia entre los equipos."
**Bien:** "El equipo de sales y el de producto van a compartir el roadmap del Q2."

---

## Regla 5: Meta-señalización (anunciar lo que vas a decir en vez de decirlo)

Frases que narran el acto de hablar en lugar de hablar. Throat-clearing.

### A cortar

- "te tiro la pregunta directa"
- "sin más rodeos"
- "te dejo planteado"
- "vale la pena destacar que"
- "es importante notar que"
- "dicho esto"
- "para ser claro"

### El fix

Arrancá directo con la idea.

**Mal:** "Sin más rodeos, el problema es la retención."
**Bien:** "El problema es la retención."

---

## Cómo aplicar (anti-overfitting)

Esta guía describe gusto. No reemplaza criterio. Algunos errores comunes al aplicarla:

- **No copiar el estilo "anti-slop" hasta que parezca sketch.** Frases cortas sí, todas las frases cortas no.
- **No forzar humor para sonar humano.** Si no sale, no va.
- **No evitar una palabra útil porque está en alguna lista.** Si es la palabra exacta, va.
- **No convertir el output en un checklist de errores evitados.** Escribí natural primero, sacá lo que suene a máquina después.

El test es uno solo:

> "¿Suena a algo que vos escribirías, o a una IA tratando duro de sonar humana?"

Si sale forzado, simplificar.

---

## Quick check (mental, antes de mandar)

Pasada rápida sobre el texto:

1. ¿Hay algún "no es X, es Y" en cualquier forma? Borrar la X.
2. ¿Hay verbos como destilar, anclar, desempacar, cristalizar? Reemplazar con verbos literales.
3. ¿Hay frases tipo "marcando un punto de inflexión", "subrayando su importancia"? Cortar.
4. ¿Hay aprovechar / potenciar / impulsar / robusto / escalable / holístico fuera de contexto técnico? Cortar o reemplazar.
5. ¿Hay meta-señalización ("sin más rodeos", "vale la pena destacar")? Cortar y arrancar directo.
6. ¿El primer párrafo arranca con la idea útil, o con throat-clearing? Cortar el arranque.
7. ¿El cierre repite lo ya dicho? Cortar.

Si pasa los 7, listo.

---

## Notas

- **Em-dashes (—) van baneados en texto en español.** Reemplazar por coma, punto, dos puntos o paréntesis. Vale para todo texto en español, no solo el que pasa por anti-slop. **En texto en inglés el em-dash es puntuación normal y se deja**, no lo saques (sobre-corregir el inglés es un error común). En docs bilingües, juzgar por idioma del bloque.
- **No loops.** Una pasada de revisión y listo. Si el texto sigue teniendo slop después, mejor reescribir desde cero que pasarlo 3 veces (los loops convergen a texto cada vez más estéril).
- **No tocar la voz cuando lo que está mal es la idea.** Si el texto es vago, no es slop, es que no hay claim. Decirlo en vez de pulir.
