# Módulo 6: Integrar MCP con GitHub Copilot

## Introducción

En este laboratorio vas a aprender a integrar el Model Context Protocol (MCP) con GitHub Copilot. MCP permite extender las capacidades de Copilot conectándolo con fuentes de datos externas, APIs y herramientas, habilitando una asistencia de IA más contextual y potente.

## Objetivos de aprendizaje

Al finalizar este módulo vas a poder:

- Comprender el Model Context Protocol
- Configurar MCP con GitHub Copilot
- Conectar Copilot a fuentes de datos externas
- Configurar servidores MCP
- Usar contexto extendido para mejores sugerencias
- Resolver problemas de integración de MCP

## Prerrequisitos

- Una cuenta de usuario de GitHub con acceso a GitHub Copilot
- Conocimiento básico de herramientas de colaboración
- Un navegador web con acceso a internet

**Duración estimada:** 45-60 minutos

---

## Ejercicio: Introducción a MCP y configuración del entorno

### Introducción

En el ejercicio "Getting Started with GitHub Copilot" conocimos el sitio de actividades extracurriculares de Mergington High School, que permite a los estudiantes inscribirse a eventos.

Y ahora tenemos un problema... ¡pero uno bueno! Cada vez más docentes quieren usarlo.

Nuestros colegas docentes tienen muchas ideas, pero no damos abasto con todos los pedidos. Para resolver esto, vamos a darle una mejora a GitHub Copilot habilitando el Model Context Protocol (MCP). En concreto, vamos a agregar el servidor MCP de GitHub, que habilitará un flujo de trabajo combinado de gestión de issues y mejoras del sitio web.

¡Empecemos!

- **Para quién es:** Desarrolladores familiarizados con GitHub Copilot que quieren potenciar sus flujos de trabajo de IA.
- **Qué vas a aprender:** Introducción al Model Context Protocol (MCP), configuración del entorno y configuración del servidor MCP de GitHub.
- **Qué vas a construir:** Un entorno de desarrollo con MCP habilitado y conectado a servicios de GitHub.
- **Prerrequisitos:** Conocimiento básico de GitHub Copilot y VS Code.
- **Duración:** Menos de 30 minutos.

En este ejercicio vas a:

- Aprender sobre el Model Context Protocol (MCP)
- Configurar tu entorno de desarrollo con GitHub Codespaces
- Agregar el servidor MCP de GitHub
- Configurar el modo Agente en GitHub Copilot
- Autenticarte con GitHub a través de MCP

### Cómo iniciar este ejercicio

[BROWSER] Abrí el navegador Edge desde la barra de tareas y navegá al siguiente link:

[LINK] https://github.com/skills/integrate-mcp-with-copilot/?tab=readme-ov-file

> 📝 **Nota:** Cuando se te solicite, iniciá sesión en tu cuenta de GitHub.

[MENU] Desplazate hacia abajo y hacé clic en el botón **Copy Exercise** dentro del repositorio plantilla. Esta acción te va a pedir crear un nuevo repositorio. Se recomienda crear un repositorio público, porque los repositorios privados consumen minutos de GitHub Actions.

[DIALOG] Dejá todo por defecto y seleccioná el botón **Create repository**.

### Paso 1: Habilitar el Copilot Coding Agent

En este paso vas a ir más allá del editor y habilitar al agente de codificación de GitHub Copilot para gestionar actualizaciones del repositorio directamente en GitHub. Esto le permite a tu equipo administrar cambios sin necesidad de un entorno de codificación tradicional.

#### Teoría: ¿Qué es el Model Context Protocol (MCP)?

El Model Context Protocol (MCP) suele describirse como el "USB-C de la IA": un conector universal que le permite a GitHub Copilot (y a otras herramientas de IA) interactuar sin fricciones con otros servicios.

En esencia, es una forma de describir las capacidades y los requisitos de un servicio, de modo que las herramientas de IA puedan determinar fácilmente qué métodos usar y proveer los parámetros correctos. Un servidor MCP es quien expone esa interfaz.

En este ejercicio vas a:

- Conocer tu entorno
- Agregar el servidor MCP de GitHub

### Paso 1: Conocé tu entorno

#### Introducción

Antes de meternos de lleno en MCP, vamos a levantar nuestro entorno de desarrollo y refamiliarizarnos con la aplicación de actividades extracurriculares.

#### Actividad 1: Conocé tu entorno

[TAB] Navegá a la pestaña **Code** y desplazate hacia abajo.

[WINDOWS] Hacé clic derecho sobre el botón **Create Codespace** para abrir la página de creación de Codespace en una pestaña nueva. Usá la configuración por defecto y luego hacé clic en **Create new codespace**.

Validá que las extensiones de Copilot Chat y Python estén instaladas y habilitadas.

> 💡 **Tip:** Hacé clic en el ícono de Extensiones en la barra lateral izquierda para verificarlo.

Verificá que la aplicación corra antes de modificarla. En la barra lateral izquierda, seleccioná la pestaña **Run and Debug** y luego presioná el ícono **Start Debugging**.

> 📝 **Nota:** Si el área de Run and Debug aparece vacía, probá recargar VS Code: abrí la paleta de comandos (Ctrl+Shift+P) y buscá **Developer: Reload Window**.

[TAB] Usá la pestaña **Ports** para encontrar la dirección de la página web, abrila y verificá que esté funcionando.

#### Actividad 2: Agregar el servidor MCP de GitHub

Dentro de tu codespace, abrí el panel de Copilot Chat y verificá que el modo **Agent** esté seleccionado.

Dentro de tu codespace, navegá a la carpeta `.vscode` y creá un archivo nuevo llamado `mcp.json`. Pegá el siguiente contenido:

```json
{
  "servers": {
    "github": {
      "type": "http",
      "url": "https://api.githubcopilot.com/mcp/"
    }
  }
}
```

En el archivo `.vscode/mcp.json`, hacé clic en el botón **Start** y aceptá la solicitud de autenticación con GitHub. Esto recién le informó a GitHub Copilot sobre las capacidades del servidor MCP.

[MENU] En el panel lateral de Copilot, hacé clic en el ícono para mostrar las capacidades adicionales.

En Visual Studio Code, abrí la vista **Source Control**, revisá los cambios en el archivo `.vscode/mcp.json` y agregalo al stage. Ingresá un mensaje de commit y luego seleccioná **Commit and Push** para confirmar los cambios y subir el archivo `.vscode/mcp.json` a la rama main.

> 📝 **Nota:** Hacer push directo a main no es una práctica recomendada. Solo se hace para simplificar este ejercicio.

---

### Paso 2: Modo Agente y un servidor MCP para GitHub

¡Buen trabajo! Acabás de conectar tu primer servidor MCP a GitHub Copilot.

Los docentes estuvieron ocupados abriendo nuevos issues en tu repositorio con bugs y pedidos de funcionalidades. Por suerte, con un servidor MCP para GitHub, triagear estos pedidos e investigar para adelantarte es increíblemente eficiente.

#### Teoría: Cómo funciona el llamado de herramientas (tool calling) de MCP en modo Agente

En modo Agente, Copilot actúa como un orquestador autónomo. Con cada prompt, analiza el catálogo de herramientas disponibles provisto por el servidor MCP para decidir el mejor camino a seguir.

- **Selección de herramienta:** Copilot determina si se necesita una herramienta (por ejemplo, `#search_repositories`).
- **Paso de argumentos:** Hace coincidir tu intención con el esquema específico de la herramienta.
- **Ejecución:** Copilot ejecuta el llamado y transmite los resultados directamente al chat.

> 💡 **Tip:** Podés inducir explícitamente a Copilot a llamar a una herramienta específica incluyendo `#<nombre_herramienta>` en tu prompt (por ejemplo, `#create_pull_request` o `#codebase`).

#### Actividad 1: Investigar y descubrir proyectos similares

Asegurate de que el panel de Copilot Chat esté abierto y el modo Agent seleccionado.

Cerrá cualquier archivo abierto en tu codespace para reducir contexto innecesario.

Ingresá el siguiente prompt para buscar inspiración:

> Search for any other repositories for organizing extracurricular activities.

[DIALOG] Cuando Copilot pida permiso para usar la herramienta MCP, hacé clic en **Continue**.

Pedile a Copilot que profundice en uno de los proyectos descubiertos:

> Please look at the code for the 3rd option and give me a detailed description of the features.

Usá Copilot para comparar esas funcionalidades contra tu proyecto actual:

> Please compare these features to our project. Which would be new?

Indicale a Copilot que capture estas ideas de mejora de forma formal:

> I like these ideas. Let's create issues for these in my repository.

[DIALOG] Hacé clic en **Continue** en cada solicitud de permiso para que Copilot cree los issues en tu nombre.

Verificá que los nuevos issues existan en la pestaña **Issues** de tu repositorio.

[MENU] En la parte superior del panel de Copilot Chat, hacé clic en el ícono **New Chat (+)** para limpiar el contexto.

---

### Paso 3: Resolver issues con modo Agente y el servidor MCP de GitHub

La investigación es solo la mitad de la batalla. Ahora vas a usar la capacidad de Copilot de llamar herramientas externas para evaluar las necesidades de tu repositorio y resolver un issue real de principio a fin.

#### Teoría: Triaje asistido por herramientas

En modo Agente, Copilot no solo "chatea": actúa. Utilizando las herramientas MCP de GitHub, puede:

- **Listar issues:** Recuperar todas las tareas abiertas con sus etiquetas y metadatos.
- **Triaje profundo:** Leer comentarios y descripciones de issues para entender la complejidad y urgencia de una tarea.
- **Implementación autónoma:** Ejecutar un plan de varios pasos para crear ramas, modificar archivos y enviar PRs.

#### Actividad 1: Triagear tu repositorio

Abrí Copilot Chat en tu codespace y verificá que el modo Agent esté seleccionado.

Pedile a Copilot un estado de situación de tu proyecto:

> How many open issues are there on my repository?

> 📝 **Nota:** Cuando GitHub Copilot te lo solicite, revisá el pedido y hacé clic en **Allow** para otorgar los permisos necesarios.

Una vez que Copilot te dé el total, pedile ayuda para priorizar el trabajo:

> Please get the list of issues, review the descriptions and comments, and pick the top 3 most important ones.

> 💡 **Tip:** Si Copilot pide permisos repetidamente, podés seleccionar **Always allow** para esa sesión y acelerar el proceso.
>
> 📝 **Nota:** Cuando GitHub Copilot te lo solicite, revisá el pedido y hacé clic en **Allow** para otorgar los permisos necesarios.

Revisá las 3 sugerencias principales que te dio Copilot. Cuando estés listo para avanzar, usá la herramienta `#codebase` para darle a Copilot contexto local completo:

```
#codebase Let's do the first one. Follow these steps:
1. Checkout a new local branch for making our changes.
2. Implement the fix or feature described in the issue.
3. Push the changes and create a pull request.
```

> 📝 **Nota:** Cuando GitHub Copilot te lo solicite, revisá el pedido y hacé clic en **Allow** para otorgar los permisos necesarios.
>
> 📝 **Nota:** Verificá siempre las acciones que Copilot pide realizar, especialmente con las capacidades externas provistas por un servidor MCP, que probablemente no tengan opción de deshacer.

Una vez completada la tarea, Copilot te va a dar un link al nuevo Pull Request.

[BROWSER] Andá a GitHub y revisá la descripción del PR. Vas a ver que Copilot resumió automáticamente lo que se corrigió y lo vinculó al issue original.

---

### Paso 4: Validar código generado por IA

Como líder del proyecto, sos responsable del código que ingresa a tu repositorio. Los equipos de alto rendimiento combinan la productividad de la IA con una revisión humana rigurosa y pruebas automatizadas.

#### Teoría: El ciclo de revisión y feedback

La colaboración no termina cuando se escribe el código. Un flujo de trabajo completo incluye:

- **Revisión de pares:** Inspeccionar el código en cuanto a lógica, estilo y seguridad.
- **Validación:** Asegurarse de que la solución resuelva efectivamente el problema descrito en el issue.
- **Comunicación:** Cerrar el ciclo con las partes interesadas y colaboradores para mantener la trazabilidad.

#### Actividad 1: Revisar y mergear la solución de IA

[BROWSER] Abrí el Pull Request creado por Copilot en el paso anterior.

[TAB] Navegá a la pestaña **Files changed** e inspeccioná la implementación.

Si los cambios se ven correctos, hacé clic en **Merge pull request** y luego en **Confirm merge**.

Volvé a tu entorno de VS Code y asegurate de que el panel de Copilot Chat esté abierto en modo Agent.

> 📝 **Nota:** Si iniciaste un chat nuevo, usá el botón **Show Chats** (el ícono de reloj/lista) en la parte superior del panel para restaurar tu conversación anterior.

Pedile a Copilot que cierre la documentación de tu trabajo agregando un comentario de cierre al issue original:

> Add a closing comment to the issue we just finished.
> Provide a 1-sentence description of the implemented solution and thank the commenters for their ideas and feedback.

> 📝 **Nota:** Cuando GitHub Copilot te lo solicite, revisá el pedido y hacé clic en **Allow** para otorgar los permisos necesarios.

Verificá la acción: Copilot va a llamar a la herramienta `#add_comment`. Revisá el texto que planea publicar y hacé clic en **Continue**.

¡Buen trabajo! Recorriste con éxito el ciclo completo de desarrollo asistido por IA. 🎉

---

### Paso 2 (bis): Colaborar con Copilot

Ahora que le asignaste el issue a Copilot, vas a notar que inició automáticamente un Pull Request (PR) y lo vinculó a tu issue. Revisar el trabajo de Copilot es igual que revisar el código de un compañero humano.

#### Teoría: Entender el flujo de colaboración de Copilot

Copilot brinda transparencia a través de varios canales dentro del Pull Request:

- **Descripción del Pull Request:** Copilot la actualiza continuamente a medida que avanza. Vas a poder ver cómo pasa de la copia inicial del issue a una lista de acciones y, finalmente, a un resumen de finalización.
- **Sesiones del Coding Agent:** Copilot trabaja en "sesiones". Cada vez que asignás una tarea o das feedback, empieza una nueva sesión.
- **Logs en vivo:** Podés hacer clic en el botón **View session** en la línea de tiempo del PR para ver un registro en tiempo real de la lógica, el análisis de archivos y los pasos de implementación de Copilot.

#### Dar feedback

La clave para disparar una nueva sesión de codificación es usar la mención `@copilot`. Copilot ignora los comentarios comunes dirigidos a humanos, pero reacciona de inmediato si lo mencionás en un comentario o en una revisión de PR.

#### Actividad 1: Ver el progreso de Copilot

[BROWSER] Navegá al Pull Request referenciado en tu issue de "Manga Maniacs".

Observá cómo la descripción del PR se actualiza en tres fases:

- **Fase 1:** Copia inicial de los requisitos del issue.
- **Fase 2:** Un plan compuesto por acciones específicas.
- **Fase 3:** Un resumen final de los cambios realizados.

Desplazate por la línea de tiempo y hacé clic en el botón **View session** para ver el registro en vivo del trabajo de Copilot.

Esperá a que la sesión finalice y a que Copilot te solicite como revisor antes de continuar.

#### Actividad 2: Dar feedback a Copilot

[TAB] En el Pull Request, hacé clic en la pestaña **Files changed** y luego en el botón **Add your review**.

Pasá el mouse sobre una línea de la nueva entrada de la actividad Manga y hacé clic en el ícono **+** para dejar un comentario.

Ingresá el siguiente feedback para darle más "personalidad" a la descripción:

> @copilot Please change this description to be inspired by Japanese Manga. It needs more personality to attract students.

[DIALOG] Hacé clic en **Start a review**, luego en **Finish your review** en la parte superior y seleccioná **Submit Review**.

Observá la línea de tiempo del PR: va a comenzar una nueva sesión del agente.

#### Actividad 3: Redirigir a Copilot a mitad de sesión (opcional)

Si la sesión sigue activa, hacé clic en **View session**.

Usá el panel de chat en la parte inferior de los logs de sesión para dar una actualización de último momento:

> There is a slight change of plans—we got a bigger classroom. Let's move the schedule to 5PM Tuesday and change the maximum participants to 25.

Esperá a que Copilot termine de implementar tanto la descripción con "espíritu manga" como las actualizaciones de horario.

#### Actividad 4: Finalizar y mergear

Una vez que Copilot termine y vuelva a solicitar tu revisión, verificá los cambios en la pestaña **Files changed**.

Hacé clic en **Ready for Review** si el PR está en modo borrador.

Hacé clic en el botón **Merge pull request** y luego en **Confirm merge** para sumar el club Manga Maniacs al sitio.

---

### Paso 3 (bis): Preparar el entorno de Copilot

Para que el desarrollo sea confiable para todo el equipo, Copilot necesita guía específica del repositorio y un entorno preconfigurado. Esto reduce errores y ahorra tiempo evitando instalaciones ad-hoc.

#### Teoría: Personalizar el entorno de Copilot

Podés personalizar el comportamiento y el espacio de trabajo de Copilot mediante dos métodos principales:

- **Copilot Instructions (`.github/copilot-instructions.md`):** Este archivo brinda contexto de alto nivel, estándares y preferencias de comunicación. Es donde le indicás a Copilot cómo hablarle a usuarios no técnicos y qué reglas arquitectónicas seguir.
- **Copilot Setup Steps (`copilot-setup-steps.yml`):** Un workflow especial de GitHub Actions que preinstala dependencias (como librerías de Python) y servicios (como MongoDB). Esto garantiza que Copilot pueda ejecutar o testear tu código de inmediato.

#### Actividad 1: Crear instrucciones para guiar a Copilot

[BROWSER] Navegá a la pestaña **Code** de tu repositorio.

[DIALOG] Creá una nueva rama llamada `prepare-environment`.

Abrí el archivo `.github/copilot-instructions.md` para editarlo.

Reemplazá el texto de referencia con la siguiente configuración:

```markdown
## Development Environment
For detailed setup and development instructions, please refer to our [Development Guide](../docs/how-to-develop.md).

### User Interaction
Consider the following when communicating with the staff:
- The staff is not technical. Explain in simple terms and avoid jargon.
- Any new code must be easy to maintain without significant coding experience.

## Program architecture
- The website users are students and teachers. Keep the UX simple.
- Do not make additional apps, services, or command-line tools.
- Use a clear directory structure; avoid long single-file applications.
- Only use HTML, CSS, JavaScript, and Python.
```

Hacé clic en **Commit changes** en la esquina superior derecha y luego nuevamente en **Commit changes** para confirmar.

#### Actividad 2: Preparar el entorno de codificación (workflow)

Asegurate de seguir en la rama `prepare-environment`.

[TAB] Navegá al directorio `.github/workflows/`.

[MENU] Hacé clic en **Add file > Create new file** y nombralo `copilot-setup-steps.yml`.

Pegá la siguiente configuración de workflow:

```yaml
name: "Copilot Setup Steps"
on: workflow_dispatch
jobs:
  # This is the required job name. If different, Copilot will ignore it.
  copilot-setup-steps:
    runs-on: ubuntu-latest

    # Starts a MongoDB service for Copilot to use during its session.
    services:
      mongo:
        image: mongo:7
        ports:
          - 27017:27017
    # Grant Copilot early access to read the repository content.
    permissions:
      contents: read
    steps:
      - name: Checkout code
        uses: actions/checkout@v5
      - name: Set up Python
        uses: actions/setup-python@v6
        with:
          python-version: "3.13"
          cache: "pip"
      - name: Install Python dependencies
        run: |
          python -m pip install --upgrade pip
          pip install -r src/requirements.txt
```

Hacé clic en **Commit changes** en la esquina superior derecha y luego nuevamente en **Commit changes** para confirmar.

[TAB] Navegá a la pestaña **Pull requests** y luego hacé clic en **Compare & pull request** de `prepare-environment` hacia `main`.

Esperá a que el chequeo de validación (Mona) confirme que los archivos son correctos.

Una vez confirmado, hacé clic en **Merge Pull Request** para finalizar la configuración, y luego en **Confirm merge**.

---

### Paso 4 (bis): Gestionar múltiples tareas con el panel de Agentes

Con el entorno de Copilot ya preparado, podés abordar mejoras más complejas para el sitio de actividades extracurriculares. En lugar de asignar issues de a uno, podés usar el **Agents Panel** para manejar varios trabajos a la vez.

#### Teoría: Delegar desde cualquier lugar con el Agents Panel

El Agents Panel es una capa liviana sobre GitHub que funciona como un centro de control para tus flujos de trabajo agénticos. Te permite hacer seguimiento del trabajo de Copilot en segundo plano en tiempo real, sin salir de tu código o discusiones.

**Funciones clave del Agents Panel:**

- **Asignación en segundo plano:** Delegar nuevas tareas a Copilot al instante.
- **Monitoreo en tiempo real:** Ver el estado y progreso de las tareas en distintos repositorios.
- **Deep linking:** Saltar directamente a un Pull Request o log de sesión específico cuando estés listo para revisar.

> 📝 **Nota:** Accedé al panel haciendo clic en el botón **Agents** en la barra de navegación superior o visitando https://github.com/copilot/agents.

#### Actividad 1: Asignar tareas mediante el Agents Panel

[MENU] Abrí el panel Copilot Agents desde la barra de navegación superior.

Seleccioná el repositorio: `GithubUserName/skills-expand-your-team-with-copilot`.

> 📝 **Nota:** Reemplazá `GithubUserName` por tu propio nombre de usuario de GitHub antes de continuar.

Asegurate de que la rama esté configurada en `main`.

Ingresá el siguiente prompt en el panel para iniciar una tarea en segundo plano:

> Integrate social sharing buttons so users can easily share activities with their friends.

Monitoreá el panel para ver aparecer las tareas con su estado actual.

#### Actividad 2: Implementar issues de forma simultánea

[TAB] Navegá a la pestaña **Issues** de tu repositorio en una pestaña nueva.

Buscá y abrí los siguientes dos issues:

- Difficulty Tracks
- Dark Mode

Asigná a `@copilot` como responsable de ambos issues al mismo tiempo.

Volvé al Agents Panel; ahora vas a ver estos issues listados junto a tu tarea de social sharing.

Hacé clic en **View session** en cualquier tarea para ver a Copilot ejecutando tu personalización de `copilot-setup-steps.yml`.

Esperá a que Copilot termine el trabajo en al menos una de las tareas.

Hacé clic en el botón **View Pull Request** dentro del panel para abrir el PR resultante.

Revisá la descripción generada por IA y la pestaña **Files changed**.

Hacé clic en **Merge pull request** y **Confirm merge** una vez que estés conforme con el resultado.

---

## Revisión

¡Felicitaciones! Completaste este ejercicio y aprendiste a integrar MCP con GitHub Copilot.
