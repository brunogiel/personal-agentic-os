# SecondBrain

**Claude arranca cada sesión adivinando quién sos.** Esto corta la adivinanza: unos archivos de texto que lee al arrancar lo convierten en _tu_ asistente, no en uno genérico. No es un segundo cerebro para que leas vos: es un segundo cerebro desde el que opera tu asistente.

Un método simple e instalable para ordenar cómo trabajás con **Claude Code** (o **Cowork**) y hacerlo crecer en el tiempo. Instalás una sola cosa, un coach, y él arma y hace crecer el resto con vos, de a un escalón.

Es para cualquiera: desde el que arranca de cero hasta el que ya la tiene clara. No hace falta que programes. Si programás, la división código/contexto ya viene contemplada.

---

## Por qué funciona

Claude es un cerebro que genera texto. El harness (Claude Code, Cowork) le da manos y memoria. **Tus carpetas son lo que lo convierte en _tu_ asistente.** Unos archivos de texto, que el asistente lee al arrancar cada sesión, lo hacen dejar de adivinar quién sos y cómo trabajás. Ese es todo el truco. El resto es ordenar.

Casi nadie escribe esos archivos. Esto te da la semilla y un coach que te lleva de la mano para hacerla crecer. Lo vas a notar en la **segunda sesión**: vuelve sabiendo lo que le contaste en la primera.

## Instalación

Dos caminos. Agarrá el tuyo.

### 🖥️ Cowork (sin terminal) — el fácil

Se instala como plugin, directo desde la UI de Cowork:

1. Abrí el panel de **plugins** y agregá este marketplace: `brunogiel/secondbrain-claude`
   (o escribí `/plugin marketplace add brunogiel/secondbrain-claude`).
2. Instalá el plugin **secondbrain**
   (o escribí `/plugin install secondbrain@secondbrain-claude`).
3. Abrí (o creá) una carpeta donde quieras que viva tu cerebro, en algún lado que sincronice (Drive, iCloud, Dropbox), y abrila en Cowork.
4. Decí **"armame el sistema"** (o `/second-brain-coach`).

Sin terminal, sin zip, sin git. El coach te arma la carpeta del brain *con vos*, de a un paso, y **siempre pregunta antes de crear nada** (no te arma una carpeta por atrás). Y el plugin **se actualiza solo**.

### ⌨️ Claude Code (terminal)

```bash
curl -fsSL https://raw.githubusercontent.com/brunogiel/secondbrain-claude/main/install.sh | bash
```

Después abrí la carpeta y escribí **`/second-brain-coach`**.

---

En los dos casos el reparto es el mismo. **El método se instala como una app, fuera de tu carpeta**: como plugin en Cowork, o global en `~/.claude/skills/` en Claude Code. Lleva el coach (con su doctrina, plantillas y ejemplos) más el **kit** que instala en tu brain (`kit/brain/` los archivos base, `kit/skills/` el catálogo de skills de uso), y `actualizar`/`migrar`. **Tu carpeta solo tiene lo tuyo**: las carpetas `0. Inbox/` + PARA y lo esencial (router `CLAUDE.md`, `ESTADO.md`, `ESCALERA.md`, `AGENTS.md`, tu identidad en `2. Áreas/yo/`). Los **skills que realmente usás** (redactar, anti-slop, triage, auditar, crear-skill, evaluar-skill, ppt-builder, panel) NO te los tiran todos de una: el coach te va sumando cada uno a una carpeta `skills/` a secas y a la vista a medida que subís, así lo ves, lo abrís y aprendés cómo está hecho. Se disparan por la **tabla "Mis skills" de tu `CLAUDE.md`** (una frase → un skill) — por eso andan igual en **Claude Code, Cowork y Codex** (los tres leen tu `CLAUDE.md`; Codex vía `AGENTS.md`), sin carpetas específicas de Claude.

## ¿Ya tenés un sistema?

No tenés que migrar. Instalalo y usalo como quieras. Si ya tenés una carpeta que funciona, el coach **lee tu estructura y la mantiene**: no te renombra carpetas ni te fuerza PARA. Mapea lo que tenés en tu router (el `CLAUDE.md` que el asistente lee al arrancar) para que deje de adivinar dónde vive cada cosa, y después te propone un par de mejoras *en tu propia estructura*, de a una. Tomás las ideas que te gustan y dejás el resto. PARA es solo el empaque default para el que arranca de cero, no un requisito. Lo único no-negociable es que el router conozca tu estructura; todo lo demás es opt-in.

No es destructivo y es reversible (ver *Qué toca* abajo), así que no hay una gran decisión que tomar: instalalo, probalo y quedate con lo que te sirve.

## Qué toca (y cómo deshacerlo)

Sin caja negra. El reparto exacto:

- **Tu carpeta** recibe solo lo tuyo (tu `CLAUDE.md`, identidad, proyectos, inbox, los skills de uso que adoptás), y **la arma el coach con vos, preguntando** — nunca crea ni pisa nada sin tu OK (saltea lo que ya existe), así que no puede romper un sistema que ya armaste. El **curl no toca tu carpeta**; solo instala el método global.
- **El método** se instala como una app, fuera de tu carpeta: un **plugin** en Cowork, o global en `~/.claude/skills/` en Claude Code (el coach + `actualizar`/`migrar`). Nada de él vive en tu carpeta.
- **Las actualizaciones** solo refrescan ese motor. En Cowork el plugin se actualiza solo; en Claude Code lo hace `actualizar`. En los dos casos nunca tocan tu carpeta, así que tus ediciones están a salvo.
- **Desinstalar** saca solo el motor; tu carpeta queda intacta. En Cowork, sacá el plugin desde la UI (o `/plugin uninstall secondbrain`). En Claude Code:
  ```bash
  curl -fsSL https://raw.githubusercontent.com/brunogiel/secondbrain-claude/main/uninstall.sh | SB_YES=1 bash
  ```

## La escalera (crecé de a un escalón)

No armás todo el día uno. Subís. El coach te enseña la idea de cada escalón, no solo qué hacer.

| Nivel | Qué aprendés + sumás | Qué ganás |
|---|---|---|
| **0** | Las 3 capas (modelo / harness / tus carpetas) + capturar: te conoce (`sobre-mi` + `como-trabajo`) y nada se pierde (`0. Inbox/`) | Deja de adivinar quién sos |
| **1** | Tu primer proyecto (su propio cerebro + log de decisiones) | No volvés a explicar un proyecto dos veces |
| **2** | Atajos (rutean al asistente al toque) | Decís "mis gastos" y ya sabe dónde mirar |
| **3** | Tu primer skill (leés el que viene, después armás el tuyo) y qué es un script | Una frase dispara una receta entera |
| **4** | El sistema trabaja *para* vos: una rutina que corre sola + conectás una herramienta por MCP para que tenga ojos (mail, calendario) | Trabaja mientras dormís, sobre tus datos reales |
| **5** | Orquestás: varios skills laburando juntos en una tarea (usás un orquestador de ejemplo, después armás el tuyo) | Trabajo grande, repartido y recombinado |
| **6** | Lo mantenés: una revisión de salud (`auditar-sistema`) + afinás un skill (`evaluar-skill`) | El sistema no se pudre callado |
| *(si programás)* | Una rama opcional (no es un nivel): split código/contexto + subagentes en tu código | Código en su repo, contexto acá |

¿En bolas o avanzado? El coach se adapta: de a un escalón con todo explicado si arrancás, o un setup rápido de varios escalones más un track avanzado si ya la tenés clara. Pedile **`/second-brain-coach`** cuando quieras: te ubica y te propone el próximo paso. Propone, vos decidís.

## Cowork, Code o lo que sea

Tu **cerebro** son archivos de texto en una carpeta sincronizada, así que es el mismo abras donde abras. Arrancá en **Cowork** (sin terminal); crecé a **Claude Code** abriendo la misma carpeta, sin migración. Y el texto no está atado a Claude: tus carpetas, identidad y proyectos sirven con **Codex, Cursor o lo que venga** (un `AGENTS.md` que viene incluido apunta a los agentes no-Claude a tu `CLAUDE.md`).

Siendo honestos con la línea: tu **cerebro** (tu texto) *y* tus **skills de uso** son portables — los skills viven en una `skills/` a secas y se disparan por la tabla de tu `CLAUDE.md`, que leen Code, Cowork y Codex (Codex vía `AGENTS.md`). Lo único específico de Claude es el **motor** (el comando `/second-brain-coach` y los pocos skills de mantenimiento); en otro harness los manejás pidiéndolos con palabras. El harness es las manos; el cerebro es tuyo.

> **Y si desarrollás software en serio** (con epics, PRDs, equipo), eso es otro deporte. Combiná SecondBrain con un método de desarrollo como [BMAD-METHOD](https://github.com/bmad-code-org/BMAD-METHOD): SecondBrain se queda con tu contexto y tus decisiones, el método de dev maneja la construcción. Conviven en el split código/contexto (Nivel 5).

## Qué trae adentro

- **`CLAUDE.md`**: tu archivo raíz, un router fino que se lee al arrancar cada sesión.
- **`ESTADO.md`**: tu tablero fino (dónde estás, qué hay activo; lo lee el asistente cada sesión).
- **`ESCALERA.md`**: tu tracker de progreso gamificado: niveles 0→6, un checklist por nivel, qué hiciste y qué falta. Cierra con **"📦 Todo lo que trae el kit"**: el catálogo de lo que ves y manejás (archivos base + skills de uso) con un checkbox por cada uno, para ver en un solo lugar qué tenés y qué te falta. El coach lo mantiene; preguntale "¿cómo vengo?" o "¿qué skills tengo?" cuando quieras.
- **`AGENTS.md`**: un puntero de 6 líneas para que un agente no-Claude (Codex, etc.) encuentre tu `CLAUDE.md`.
- **`0. Inbox/`**: capturá sin decidir: tirá lo turbio acá y cocinalo después (el protocolo está en `INBOX.md`).
- **`sobre-mi.md` / `como-trabajo.md` / `mi-estilo.md`**: quién sos, cómo te gusta trabajar y una muestra de tu voz para escribir (templates para llenar, en `2. Áreas/yo/`).
- **`soul.md` / `dev-prefs.md`**: lo de fondo (se llena con el tiempo, hablando) y, si programás, cómo te gusta laburar el código (`dev-prefs.md` ya viene con un bloque de reglas universales de ingeniería de fábrica, no es un template vacío). Los suma el coach a medida que subís; no vienen en la instalación.
- **`3. Recursos/arquitectura-skills.md`**: tu referencia para armar buenos skills (regla de 3, DET/LAT, anatomía, errores típicos).
- **`3. Recursos/anti-slop-writing.md`**: la doctrina completa de anti-slop (las 5 reglas, con listas negras y ejemplos antes/después) que el skill `anti-slop` usa de base.
- **El método** se instala como una app fuera de tu carpeta (plugin en Cowork, o global en `~/.claude/skills/` en Claude Code), no en tu brain: el coach lleva su doctrina (`reference.md`), plantillas y ejemplos, más el **kit** que instala en tu brain (`kit/brain/` archivos base, `kit/skills/` catálogo de skills de uso). Nada del método ensucia tu brain — ves solo lo tuyo.
- **El motor** (🔒 fuera de tu carpeta, invisible, se llama por nombre — nunca ensucia tu brain):
  - **`second-brain-coach`**: te sube de nivel y te enseña mientras subís (`/second-brain-coach`).
  - **`actualizar`**: chequea si el kit tiene versión nueva y, con tu OK, la instala.
  - **`migrar-de-claude-projects`**: trae tus Projects cerrados de Claude al sistema.
- **Los skills que usás** (👁 visibles en `skills/`, el coach te los va sumando a medida que subís — dormidos hasta que una frase los despierta):
  - **`redactar`**: escribe en tu voz (la aprende de textos tuyos).
  - **`anti-slop`**: le saca el olor a IA a cualquier texto.
  - **`crear-skill`**: te ayuda a armar un skill nuevo bien hecho.
  - **`evaluar-skill`**: mide un skill contra su propio SKILL.md y propone arreglos (para cuando tenés varios y querés mantenerlos afilados).
  - **`auditar-sistema`**: una revisión de salud de tu sistema (va bien como rutina).
  - **`triage`**: tu brief de la mañana y los accionables, cruzando tus fuentes: mail, calendario (reporte de citas) y tu chat/tareas de trabajo (Slack, Jira, Linear, Trello, Notion comments, lo que uses). Cada fuente necesita su MCP; con el mail solo ya arranca.
  - **`ppt-builder`**: arma un deck (o post, video, carrusel, landing) en 5 etapas; el **ejemplo de orquestador con estado** (coordina `redactar` + `anti-slop` + tu skill de pptx). Aparece en el Nivel 5.
  - **`panel`**: trae 2-5 reviewers con lentes distintas para mirar algo que estás haciendo (un doc, mail, propuesta, copy) desde varios ángulos antes de soltarlo, y te devuelve la pelota (muestra ángulos, no decide); el **ejemplo de orquestador multi-agente**. Aparece en el Nivel 5.

## Filosofía

- **Propone, vos decidís.** Nada se crea sin tu OK.
- **Un escalón por vez.** Sin listas que abruman.
- **Enseña mientras subís.** Aprendés la idea, no solo la tarea.
- **Liviano para correr.** Lee solo lo que necesita, así no te quema el plan de $20.
- **Todo viaja dormido.** Un skill no hace nada hasta que una frase lo despierta.

## Autor

Hecho por [Bruno Gielczynsky](https://www.linkedin.com/in/brunogiel/). Parte de una familia de métodos de AI instalables junto con [Empat.ia](https://github.com/brunogiel/Empat.ia).

## Licencia

MIT. Usalo, forkealo, hacelo tuyo.
