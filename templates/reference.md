<!--
  REFERENCE — el manual que crece (SecondBrain).
  Plantilla en español. No se lee de corrido: es consulta, vas a una sección cuando la necesitás.
-->

# reference.md — El manual

Esto no se lee de un tirón. Es una caja de herramientas: venís acá cuando querés subir un escalón. Tu `CLAUDE.md` raíz alcanza para arrancar. Esto es para cuando quieras crecer.

---

## 1. El porqué: por qué unas carpetas cambian tu asistente

Pensalo en 3 capas:

1. **El modelo** (Claude). Es un cerebro que genera texto. Solo. No sabe quién sos.
2. **El harness** (Claude Code, Cowork, Cursor). Es el cuerpo: le da manos para tocar archivos, memoria, y un loop para trabajar solo.
3. **Tus carpetas** (este sistema). Son lo que el harness lee para volverse *tu* asistente.

La frase clave: **tus carpetas personalizan el asistente, no son el asistente.** Por eso un archivo de texto bien puesto cambia tanto el resultado: el asistente lo lee al arrancar y deja de improvisar sobre quién sos. Ese es todo el truco. El resto es ordenar.

---

## 2. PARA: cómo ordenás cualquier cosa

Una sola pregunta para decidir dónde va algo: *¿esto qué es?*

- **1. Proyectos/** : tiene un objetivo y termina. ("Lanzar la landing", "Cerrar el balance de marzo").
- **2. Áreas/** : una responsabilidad que no termina. ("Salud", "Finanzas", "Mi rol en la empresa").
- **3. Recursos/** : material de referencia que sirve a varios proyectos. ("Mis plantillas", "Frameworks que uso").
- **4. Archivo/** : lo terminado o lo que pausaste. No lo borrás, lo sacás de la vista.

Regla práctica: si dudás entre Proyecto y Área, preguntate *¿esto se termina algún día?* Si sí, Proyecto. Si no, Área. Cuando un proyecto se cierra, pasalo a Archivo (no lo borres, sirve de historia).

---

## 3. Cada proyecto tiene su propio cerebro

Adentro de cada proyecto va un `CLAUDE.md` con dos cosas:
- **Contexto:** qué es, quién participa, qué estado tiene, qué links importan.
- **Log de decisiones:** una línea con fecha cada vez que decidís algo importante. ("2026-06-01: elegimos X en vez de Y porque Z").

El log es oro: la próxima vez que abrís el proyecto (vos o el asistente), no tenés que reconstruir por qué hiciste las cosas. Está escrito.

---

## 4. Memoria: qué guardar y qué no

`MEMORIA.md` es donde el asistente acumula hechos que valen para todo, no para un proyecto. ("Soy alérgico a X", "Mi tono en mails es informal", "Prefiero que me preguntes antes de asumir").

Guardá lo que **no** se deduce solo de tus archivos. No guardes lo que ya está escrito en otro lado (eso es duplicar). Si algo resultó ser falso, borralo.

---

## 5. Skills: cuándo y cómo

Un **skill** es una receta guardada: instrucciones que el asistente sigue cuando una frase lo dispara. Mientras nadie lo llama, no hace nada. Por eso podés tener muchos sin que te molesten.

**Cuándo crear uno: la regla de 3.** ¿Le pediste lo mismo 3 veces? Convertilo en skill. Antes de eso es prematuro.

Regla de diseño: el harness fino, el skill gordo. Toda la inteligencia vive en el `SKILL.md`, no en mil instrucciones sueltas que repetís cada vez.

**Anatomía mínima de un skill que funciona** (un archivo `SKILL.md` en una carpeta):
- **Descripción con frases reales** que lo disparan (no "hace reportes", sino "cargá la factura", "subí el resumen"). Esa descripción es lo que hace que se dispare solo cuando lo necesitás.
- **Contexto en 2 líneas:** qué hace y para quién, en términos de tu trabajo, no de código.
- **Cuándo SÍ y cuándo NO** usarlo (los bordes importan tanto como el centro).
- **Pasos marcados `[DET]` o `[LAT]`** (mirá la sección 6).
- **Qué archivos lee y escribe**, para no pisar nada por accidente.
- **Cómo se ve un buen resultado:** qué devuelve y 2-3 señales de que salió bien.

**Errores típicos al hacer skills (evitalos):**
- **Clonar un skill cambiando un dato.** Si tenés "skill-para-Ana" y "skill-para-Juan" iguales salvo el nombre, parametrizá: que tome el nombre como dato de entrada.
- **Pedirle al modelo que haga cuentas grandes.** Contar, sumar o cruzar 500 filas es código (DET), no criterio. El modelo se equivoca en lo combinatorio.
- **Meter todo en un mega-skill.** Si una parte sirve para varias cosas (por ejemplo, tu forma de escribir), sacala a su propio skill chico y reusala en vez de enterrarla.
- **Skill sin señales de éxito.** Si al terminar no sabés si salió bien más allá de "parece OK", falta definir cómo se mide.

---

## 6. DET vs LAT: el click que mejora todo lo que pedís

Cuando le das una instrucción (o escribís un skill), separá cada paso en dos tipos:

- **DET (determinístico):** mecánico, siempre igual, no requiere pensar. *"Abrí este archivo", "sumá la columna C", "mandá el mail a esta dirección".*
- **LAT (latente):** requiere criterio del asistente. *"Decidí qué leads priorizar", "escribí el resumen en mi tono", "elegí el mejor título".*

Por qué importa:
- Los pasos **DET** conviene clavarlos exactos (o que los haga código), así el asistente no improvisa donde no debe.
- Los pasos **LAT** son donde le dejás pensar de verdad. Ahí le das contexto y libertad, no una receta rígida.

El error típico del principiante es tratar todo como LAT ("hacelo lindo") o todo como DET ("seguí estos 40 pasos"). Cuando separás, tus pedidos se vuelven claros y tus skills, confiables. Marcá cada paso `[DET]` o `[LAT]` y vas a ver la diferencia.

---

## 7. Skill vs agente (para cuando crezcas)

- **Skill = receta.** Corre dentro de tu sesión, con vos presente. Puede preguntarte.
- **Agente = proceso que corre solo.** Arranca limpio (sin tu charla), hace su tarea, termina. Puede dispararse por horario (todas las mañanas a las 8).

Empezás con skills. Los agentes vienen después, cuando una tarea ya no necesita que estés ahí.

---

## 8. Orquestador vs worker (más adelante todavía)

Cuando tengas varias recetas, una puede coordinar a las otras:
- **Worker:** hace una tarea concreta.
- **Orquestador:** no hace el trabajo, decide qué worker corre y junta los resultados.

Tu `/coach` es un orquestador chiquito: no hace tu sistema, te lleva de la mano para que lo armes vos.

---

## 9. Si programás: el split código / contexto

Una sola regla: **el código vive en su repo, el contexto vive en este sistema.**
- Código → `~/Code/<proyecto>/` (con git).
- Contexto, decisiones, notas → tu carpeta de Proyecto acá.
- En el repo, un `CLAUDE.md` corto apunta de vuelta a este sistema, así el asistente sabe dónde está todo.

Si no programás, esta sección no te toca.

---

## 10. Buenas costumbres
- **No creés cosas sin pedido.** El asistente no debería inventar archivos, READMEs ni carpetas porque sí. Que pregunte.
- **Una decisión, una línea en el log.** Te lo agradecés en 3 meses.
- **Revisá de a uno.** Pedile las cosas de a una y mirá antes de seguir. El asistente es rápido, vos sos el que decide.
- **Empezá chico y medí.** No armes el sistema entero hoy. Subí un escalón, usalo una semana, subí el siguiente.

---

## La escalera (tu índice de crecimiento)
- **Nivel 0:** el asistente te conoce (`sobre-mi` + `como-trabajo`).
- **Nivel 1:** tu primer proyecto con su `CLAUDE.md`.
- **Nivel 2:** la tabla de atajos en tu `CLAUDE.md` raíz.
- **Nivel 3:** tu primer skill (regla de 3).
- **Nivel 4:** (si programás) el split código / contexto.

¿No sabés en qué escalón estás? Pedile **`/coach`**.
