---
name: anti-slop
description: >
  Limpia un texto del "olor a IA" en una sola pasada. Usalo cuando digas
  "pasalo por anti-slop", "limpiá este texto", "esto suena a IA", "sacale el slop",
  "revisá esto antes de mandarlo", "no me convence cómo quedó". Ideal para textos
  de 300 palabras o más. No cambia lo que decís, saca lo que sobra.
---

# anti-slop — sacarle el olor a IA a un texto

Una pasada de higiene. No reescribís el mensaje ni la voz: sacás los tics que delatan que lo escribió una máquina. **Una sola pasada, sin loops.**

## Las 4 reglas

### 1. "No es X, es Y" (el tell número uno)
El patrón "no es X, es Y" / "no se trata de X sino de Y" / "menos X, más Y" es la muletilla más común de los LLM. Borrá la mitad negada y dejá solo la afirmación directa.
- Mal: "No es un problema de productividad, es de atención." → Bien: "El cuello de botella es la atención."
- Está OK contrastar solo para corregir un dato concreto: "La reunión es el martes, no el jueves."

### 2. Verbos metafóricos donde no hacen falta
destilar, anclar, desempacar, cristalizar, potenciar, tejer, forjar, catalizar, sembrar. (En inglés: distill, unlock, leverage, harness, delve.) Cambialos por verbos planos: explicar, mostrar, sacar, juntar, reducir, definir, comparar.

### 3. Puffery y falsa profundidad
"un punto de inflexión clave", "marcando una evolución importante", "sentando las bases para", y participios decorativos al final ("subrayando su importancia", "reflejando tendencias más amplias"). Decí el hecho con números y dejá que el lector mida el peso.
- Mal: "Creció mucho, marcando un hito clave." → Bien: "Creció 40%: de 200 a 280 clientes."

### 4. Vocabulario muerto
robusto, escalable (fuera de contexto técnico), holístico, sinérgico, innovador, disruptivo, transformador, sin fricción, intuitivo, empoderar, visionario. Si hay una palabra más simple que dice lo mismo, usala.

## El guion largo (em-dash)
El em-dash (—) metido por todos lados es marca típica de IA. En español, cambialo por coma, punto, dos puntos o paréntesis. En inglés es puntuación normal, dejalo. En texto bilingüe, juzgá por el idioma del bloque.

## El test único
> "¿Suena a algo que esta persona escribiría, o a una IA tratando de sonar humana?"

Si suena forzado, simplificá.

## Reglas de aplicación
- **Una sola pasada.** Si después sigue con slop, reescribí de cero. Los loops dan texto cada vez más estéril.
- **No toques la voz si el problema es la idea.** Si el texto es vago, no es slop: es que no hay un claim. Decilo en vez de pulir.
- **No sobre-corrijas.** No evites una palabra útil solo porque está en una lista. Si es la palabra exacta, va.

## Flujo
1. **[DET]** Leé el texto entero.
2. **[LAT]** Marcá los problemas por regla (1 a 4 + el em-dash).
3. **[LAT]** Reescribí limpio, mismo mensaje, misma voz.
4. **[DET]** Entregá el texto + 2-3 líneas de qué sacaste.

## Cuándo NO usar
- Textos de un par de líneas: no hace falta.
- Texto técnico, código o datos: ahí no hay slop que sacar.

## Señales de que lo hiciste bien
- Dice lo mismo pero suena humano.
- No metiste ideas nuevas ni cambiaste el mensaje.
- Fue una pasada, no diez.
