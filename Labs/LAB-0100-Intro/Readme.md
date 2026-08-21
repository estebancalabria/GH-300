## Laboratorio: Introducción a GitHub Copilot

### Preparación

[BROWSER] Entrar a https://github.com/ e iniciar sesión

[BROWSER] Ir a https://github.com/skills/getting-started-with-github-copilot

[MENU] Click en "Copy exercise"

[MENU] Click en "Create Repository"

> Info: https://github.blog/news-insights/research/research-quantifying-github-copilots-impact-on-developer-productivity-and-happiness/

[BROWSER] Si no tenés cuenta, registrarte en https://github.com/github-copilot/signup (activa 30 días de prueba gratis)

### Paso 1: Abrir el Codespace

[BROWSER] En el repo copiado, ir a **Issues**

[LINK] Abrir el issue "Exercise: Getting Started with GitHub Copilot"

[MENU] Scroll abajo → "Open on GitHub Codespaces" → "Create new Codespace"

[WINDOWS] Esperar a que cargue. Instalar extensiones de Python y GitHub Copilot si no están

### Paso 2: Copilot Chat (modo Ask)

[WINDOWS] Abrir el chat de Copilot, modo **Ask**

```
@workspace Please briefly explain the structure of this project.
What should I do to run it?
```

[MENU] Ejecutar y debuggear desde el menú izquierdo

[TAB] Ir a la solapa "Ports", puerto 8000 → abrir en navegador

[BROWSER] Ver la web generada

[WINDOWS] Abrir nueva terminal, `Ctrl+I`

```
Hey copilot, how can I create and publish a new Git branch?
```

Luego de la respuesta:

```
Awesome! Thanks, Copilot! Let's use the branch name "accelerate-with-copilot".
```

Ejecutar el comando sugerido.

### Paso 3: Corregir un bug con Copilot Chat

Prompt en el chat:

```
@workspace Students are able to register twice for an activity.
Where could this bug be coming from?
```

[WINDOWS] Abrir `src/app.py`, buscar el método `signup_for_activity`

[WINDOWS] Antes del comentario `# Add student`, escribir:

```
# Validate student is not already signed up
```

Presionar `Tab` para aceptar la sugerencia de Copilot. Aceptar el cambio.

### Paso 4: Generar datos de ejemplo (Inline Chat)

[WINDOWS] En `src/app.py`, línea ~23, ubicarse en la variable `activities`

[WINDOWS] Abrir Inline Chat: `Ctrl+I` (o click derecho → Copilot → Editor Inline Chat)

```
Add 2 more sports related activities, 2 more artistic
activities, and 2 more intellectual activities.
```

Revisar los cambios (se marcan en celeste) y **Keep**.

### Paso 5: Commit con Copilot

[TAB] Ir a "Source Control"

[MENU] Click en "+" sobre `app.py` para stagear

[MENU] Click en el ícono de estrellas ✨ "Generate Commit Message with Copilot"

[MENU] "Commit" → "Sync Changes"

[DIALOG] Si aparece popup "This action will pull and push commits...", click **OK**

Esperar el check automático (Mona) y feedback.

### Paso 6: Copilot Edit Mode (multi-archivo)

[WINDOWS] Abrir Copilot Chat → dropdown → modo **Edit**

[DIALOG] Si aparece popup, click **Yes**

[WINDOWS] Arrastrar al chat como contexto:
- `src/static/app.js`
- `src/static/index.html`
- `src/static/styles.css`

Prompt:

```
Hey Copilot, can you please edit the activity cards to add a participants section.
It will show what participants that are already signed up for that activity as a bulleted list.
Remember to make it pretty!
```

[TAB] Verificar en la pestaña del navegador (Mergington High School) que se vea bien, refrescar si hace falta

[WINDOWS] Volver a VS Code, revisar cada edit sugerido y **Keep**

[TAB] "Source Control" → stagear `app.js` y `styles.css` → generar commit message con Copilot → "Commit" → "Sync Changes"

[DIALOG] Confirmar popup si aparece

Revisar feedback de Mona. Si falla el CSS por estilos, en el chat:

```
Please update the web application styling in the style.css file to support participant info.
```

Aceptar cambios (**Keep**) y repetir commit/push.

### Teoría: Agent Mode vs Edit Mode

| Aspecto | Edit Mode | Agent Mode |
|---|---|---|
| Contexto | Solo archivos agregados manualmente | Lee/agrega archivos según necesite |
| Auto-revisión | Mínima, iterás vos | Loop de feedback y reintento en errores |
| Alcance | Quirúrgico | Más amplio, toca capas relacionadas |
| Cuándo usar | Sabés exactamente qué cambiar | Objetivo amplio o incierto |
| Tools | No ejecuta comandos | Puede leer/editar archivos, correr comandos, tests |

### Paso 7: Agent Mode

[WINDOWS] Copilot Chat → dropdown → modo **Agent**

[MENU] Click en el ícono de Tools para explorar herramientas disponibles

Prompt (botón "unregister"):

```
#codebase Please add a delete icon next to each participant and hide the bullet points.
When clicked, it will unregister that participant from the activity.
```

Reiniciar el debugger, revisar resultado, **Keep** si está bien (o dar feedback).

Prompt (bug de refresco):

```
I've noticed there seems to be a bug. When a participant is registered,
the page must be refreshed to see the change on the activity.
```

Revisar y **Keep**.

### Paso 8: Tests con Agent Mode

Prompt:

```
Add fastapi tests using pytest in a new tests directory and run them.
Make sure to add any new dependencies to requirements.txt
```

[DIALOG] Aprobar el uso de herramientas si Copilot lo solicita

[TAB] "Source Control" → stagear todo → generar commit message con Copilot → "Commit" → "Sync Changes"

### Paso 9: Copilot en Pull Requests

- **PR summaries**: Copilot resume todos los cambios del PR con referencias (no disponible en Copilot Free)
- **Code review**: Copilot hace una primera revisión automática antes del peer review (no disponible en Copilot Free)
