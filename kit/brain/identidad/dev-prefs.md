# dev-prefs.md

> Solo si programás: cómo te gusta laburar el código. Tu asistente lo lee cuando toca código, así no improvisa tu estilo. Si no programás, borrá este archivo.
>
> Viene con un bloque de **reglas universales de fábrica** (sirven en cualquier stack). Editá lo que no compartas y completá el bloque de abajo con lo tuyo.

## Reglas universales (de fábrica, agnósticas al stack)

Aplican a cualquier repo, sin importar lenguaje ni framework. Son un buen default; cambiá lo que no va con vos.

**Tamaño de archivo**
- Archivos de **≤ 300 líneas**. Si pasa de 200, buscá una extracción (un hook, un sub-componente, un helper). Si pasa de 300, refactorizá antes de seguir agregando.

**Nombres**
- Sin abreviaturas salvo las muy estándar (`url`, `id`, `db`, `api`). `usrMgr` no; `userManager` sí.
- Booleanos: `is*`, `has*`, `should*`, `can*`. No `flag` ni `status` (salvo que sea de verdad un status).
- Las funciones son verbos, las variables son sustantivos.

**Imports**
- Imports directos, sin barrel files (`index.ts` que re-exporta todo).
- Rutas absolutas con alias (`@/` o equivalente) para lo que cruza 2+ niveles de carpeta.

**Secretos y config**
- **Nunca** commitees `.env`, `credentials.json`, API keys, tokens ni nada con secretos.
- Agregalos al `.gitignore` antes del primer commit, no después de la fuga.
- Variables por `.env.local` (gitignored) y documentá las que hacen falta en `.env.example` (commiteado, sin valores).

**Logs y errores**
- Nada de `console.log/warn/error` en código de producción. Usá el logger del proyecto.
- No te tragues errores con un `try/catch` que no hace nada. Si capturás, logueá y decidí qué hacer.
- El mensaje de error tiene que ayudar al próximo a debuggear, no solo decir "algo falló".

**Comentarios**
- Default: sin comentarios. El código con buenos nombres se explica solo.
- Comentá **solo** cuando el *por qué* no es obvio: un workaround, una restricción oculta, un invariante que el próximo se perdería.
- Nunca repitas lo que el código ya dice (`// incrementa el contador` arriba de `counter++`).

**Código muerto**
- Si una función, variable o import no se usa, borralo. No lo dejes con notas tipo `// sacado`.
- Si una feature quedó sin uso, borrá sus caminos. No la guardes "por las dudas".

**Testing**
- No está listo hasta que lo viste funcionar. Type-checks y unit tests verifican que el código es correcto, no que la feature anda.
- UI: levantá el server y usá la feature en el browser antes de cantar "listo".
- Backend: como mínimo, un curl o un test de integración contra el endpoint.

**Performance**
- No optimices antes de medir. Pero tampoco escribas O(n²) cuando O(n) cuesta lo mismo.
- Evitá N+1, sobre todo en loops. Batch o join.
- Listas: paginá o virtualizá cuando los items pasan de 100.

---

## Lo tuyo (completá)

## Stack
- <...> (lenguajes, frameworks, servicios que usás)

## Cómo arranco un repo
- <...> (de cero, plantilla, lo que clonás siempre)

## Commits y ramas
- <...> (formato de los mensajes, cómo manejás branches y merges)

## Qué es "listo" para mí (Definition of Done)
- <...> (además del testing de arriba: lint, review antes de mergear, lo que sea tuyo)

## Reglas que copio a cada proyecto
- <...> (tus reglas técnicas / de estilo, lo que va a `.cursor/rules` o `.claude/`)

## Cómo manejo los bugs
- <...> (reproducir primero, escribir el test que falla, después arreglar, etc.)
