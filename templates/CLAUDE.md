<!--
  SUPER MD — archivo raíz de tu sistema (SecondBrain).
  Plantilla en español (el método se distribuye en español; el README está en EN + ES).
  Lo que ve el usuario empieza en la línea de abajo.
-->

# CLAUDE.md — <Tu nombre>

> Esto es lo primero que tu asistente (Claude Code o Cowork) lee cuando arranca una sesión.
> El asistente es un cerebro que genera texto. Este archivo es lo que lo convierte en *tu* asistente: le dice quién sos, cómo trabajás y dónde está todo.
> **Empezá llenando solo lo que está marcado con `<...>`.** El resto crece solo (mirá "Cómo crece esto" al final).

---

## Cómo arrancás cada sesión
Reglas que tu asistente sigue siempre:
1. Leé este archivo primero.
2. Si el pedido es de un proyecto, leé `1. Proyectos/<ese proyecto>/CLAUDE.md`.
3. Para datos personales o de cómo trabajo, mirá `sobre-mi.md` y `como-trabajo.md`.

## Quién soy
- **Nombre:** <...>
- **A qué me dedico:** <...>
- **En una línea, qué quiero del asistente:** <...>
- Detalle completo: [sobre-mi.md](sobre-mi.md)

## Cómo trabajo
Mi tono, mi idioma, qué formato me gusta y qué considero "listo": [como-trabajo.md](como-trabajo.md)

## Mi sistema (PARA)
Cuatro carpetas, una sola pregunta para ordenar cualquier cosa: *¿esto qué es?*
- **1. Proyectos/** : algo con un objetivo y una fecha (se termina).
- **2. Áreas/** : responsabilidades que no terminan (salud, finanzas, tu rol).
- **3. Recursos/** : material de referencia que sirve a varios proyectos.
- **4. Archivo/** : lo terminado o lo que pausaste.

Cada proyecto tiene su propio `CLAUDE.md` adentro, con su contexto y un log de decisiones.

## Atajos (frase → dónde ir)
Cuando tengas varios proyectos, esta tabla le dice al asistente dónde buscar apenas decís algo.
| Si digo… | Andá a… |
|---|---|
| *(ejemplo)* "mis gastos del mes" | `1. Proyectos/Gastos/` |
| `<tu frase típica>` | `<tu carpeta>` |

## Si además programás (opcional)
Si un proyecto tuyo tiene código:
- El **código** vive en un repo aparte (por ejemplo `~/Code/<proyecto>/`).
- El **contexto** (todo este sistema) se queda acá.
- En el repo, un `CLAUDE.md` cortito apunta de vuelta a este sistema.

Si no programás, ignorá esta sección. No te hace falta.

---

## 📈 Cómo crece esto (la escalera)
No llenes todo hoy. Subí un escalón cuando estés listo. Cuando ya lo tengas internalizado, podés borrar esta sección.

- **Nivel 0 — Te conoce.** Llená `sobre-mi.md` y `como-trabajo.md`. Listo: el asistente ya trabaja a tu medida. *(esto es todo lo que necesitás para arrancar)*
- **Nivel 1 — Tu primer proyecto.** Creá `1. Proyectos/<algo real>/CLAUDE.md` y meté tu primer caso (por ejemplo, esa automatización que tenés en la cabeza).
- **Nivel 2 — Atajos.** Cuando tengas 3 o 4 proyectos, llená la tabla de arriba. Ahí el sistema empieza a sentirse mágico.
- **Nivel 3 — Tu primer skill.** ¿Le pediste lo mismo 3 veces? Convertilo en un skill para no repetirte (cómo, en `reference.md`).
- **Nivel 4 — (si programás) el split código/contexto.**

**¿No sabés en qué nivel estás o qué sigue?** Pedile a tu asistente: **`/coach`** (o decile *"¿cómo mejoro mi sistema?"*). Te ubica y te propone el próximo paso. Propone, vos decidís.

## El manual completo
Cuándo conviene un skill y cómo se escribe, la diferencia entre pasos mecánicos y pasos de criterio (DET / LAT), y todas las convenciones: [reference.md](reference.md). No hace falta leerlo para empezar, está ahí para cuando quieras crecer.
