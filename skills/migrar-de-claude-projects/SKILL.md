---
name: migrar-de-claude-projects
description: >
  Te ayuda a traer tus proyectos de Claude (los Projects de la app, cerrados) al sistema.
  Usalo cuando digas "migrá mis proyectos de claude", "traé mis projects", "importá mis
  proyectos de la app", "pasá mis proyectos de claude.ai acá".
---

# migrar-de-claude-projects: traer tus Projects al sistema

## Qué es
Los Projects de la app de Claude están cerrados: no se pueden leer desde acá. Así que los traemos a mano, de a uno, y los convertimos en proyectos del sistema (cada uno con su `CLAUDE.md`).

## Flujo (uno por vez)
1. **[LAT]** Pedile que elija UN Project para empezar.
2. **[DET]** Pedile que te pegue las instrucciones (custom instructions) de ese Project, y que te diga o pegue qué archivos de conocimiento tiene.
3. **[LAT]** Armá `1. Proyectos/<nombre>/CLAUDE.md`: el contexto sale de esas instrucciones, más un log de decisiones que arranca hoy.
4. **[DET]** Guardá los archivos de conocimiento en esa misma carpeta del proyecto.
5. **[LAT]** Mostrale cómo quedó y confirmá antes de pasar al siguiente. No los batchees todos de una.

## Cuándo NO usar
- Para proyectos que ya viven en el sistema.
- Para "traer todo de una": es de a uno, así revisás cada uno.

## Señales de que lo hiciste bien
- Cada Project quedó como una carpeta en `1. Proyectos/` con su `CLAUDE.md`.
- Revisaste de a uno, no en bloque.
- El contexto del Project no se perdió en la traducción.
