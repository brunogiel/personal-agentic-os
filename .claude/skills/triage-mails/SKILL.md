---
name: triage-mails
description: >
  Te arma un digest de tu inbox: los accionables arriba y el resto clasificado.
  Usalo cuando digas "leeme los mails", "triage de mails", "qué llegó al inbox",
  "digest del inbox", "revisá mi correo". Necesita Gmail conectado por MCP.
---

# triage-mails: el digest del inbox

## Qué es
Lee tu inbox reciente y te lo devuelve masticado: qué requiere acción y qué es ruido. No manda ni archiva nada solo, propone.

## Precondición: Gmail por MCP
Necesitás Gmail conectado por MCP (mirá `.secondbrain/reference.md`, sección 17). Si no está conectado, frená y guiá al usuario para conectarlo antes de seguir.

## Flujo
1. **[DET]** Leé el inbox de las últimas 24h (o el rango que pida).
2. **[LAT]** Clasificá cada hilo: responder / accionar / decidir / FYI / ruido.
3. **[LAT]** Armá el digest: arriba los 3 accionables más importantes; abajo, el resto agrupado por categoría, una línea cada uno.
4. **[LAT]** Si algo pide respuesta, ofrecé redactarla (con el skill `redactar` si está), pero NO mandes nada sin OK.

## Cuándo NO usar
- Sin Gmail conectado: conectalo primero.
- Para mandar o archivar en masa: esto es para leer y proponer, no para actuar solo.

## Señales de que lo hiciste bien
- Los 3 accionables de arriba son de verdad los importantes.
- El ruido quedó como ruido, no inflado.
- No tocaste el inbox (ni mandar, ni archivar) sin OK.
