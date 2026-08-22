# Módulo 05: Amplía tu equipo con Copilot Coding Agent

## Introducción

En este laboratorio aprenderás a usar las capacidades del agente de codificación de GitHub Copilot para potenciar la productividad de tu equipo. El coding agent va más allá del autocompletado simple: ayuda con tareas complejas como refactorización, debugging e implementación de funcionalidades en múltiples archivos.

## Objetivos de aprendizaje

Al finalizar este módulo vas a poder:

- Comprender las capacidades del Copilot coding agent
- Usar el agente para tareas de desarrollo complejas
- Colaborar de forma efectiva con el agente de IA
- Aprovechar el agente para cambios multi-archivo
- Aplicar las sugerencias del agente en proyectos reales
- Integrar el coding agent en los flujos de trabajo del equipo

## Prerrequisitos

- Cuenta de usuario de GitHub con acceso a GitHub Copilot
- Comprensión básica de herramientas de colaboración
- Navegador web con acceso a internet

Duración estimada: 45–60 minutos.

---

## Cómo iniciar este ejercicio

[BROWSER] Abrí el navegador Edge desde la barra de tareas y navegá a:
https://github.com/skills/expand-your-team-with-copilot/

📝 Nota: cuando te lo pida, iniciá sesión en tu cuenta de GitHub.

Desplazate hacia abajo y hacé clic en [BROWSER] botón **Copy Exercise** en el repositorio plantilla. Esta acción te pide crear un nuevo repositorio. Se recomienda crear un repositorio **público**, ya que los repositorios privados consumen minutos de GitHub Actions.

Dejá todo por defecto y hacé clic en [BROWSER] botón **Create repository**.

---

## Paso 1: Habilitar Copilot Coding Agent

En este paso vas más allá del editor y habilitás al agente de Copilot para que gestione actualizaciones del repositorio directamente en GitHub. Esto permite que tu equipo administre cambios sin un entorno de desarrollo tradicional.

### Teoría: Copilot como tu Coding Agent

El Copilot coding agent opera enteramente en GitHub. Desde la perspectiva de un colaborador, el flujo es muy similar a un ciclo de desarrollo normal, pero es Copilot quien maneja la implementación:

1. Un colaborador con permisos de escritura asigna un issue a Copilot.
2. Copilot crea una rama y un pull request.
3. Copilot trabaja en la rama mediante un workflow de Actions y publica actualizaciones en la pestaña de conversación del PR.
4. Al finalizar, se solicita revisión a quien asignó la tarea.
5. El feedback se puede dar mediante comentarios, que Copilot luego implementa.

### Actividad 1: Habilitar Copilot Coding Agent en tu repositorio

1. [BROWSER] En la parte superior derecha de GitHub, hacé clic en tu ícono de usuario y seleccioná [MENU] **Settings**.
2. En la navegación izquierda, expandí la sección [MENU] **Copilot** y seleccioná [MENU] **Coding agent**.
3. Verificá que el campo **Repository access** esté configurado en **All repositories**.

### Actividad 2: Asignar un Issue a Copilot

1. [BROWSER] Andá a la [TAB] pestaña **Issues** de tu repositorio y hacé clic en el botón **New Issue**.
2. Configurá el **Title** como: `Missing Activity: Manga Maniacs`
3. Ingresá el siguiente texto como descripción y hacé clic en **Create**:

   ```
   The manga club was recently announced and is naturally missing from the website. Please add it.

   Details:
   - Description: Explore the fantastic stories of the most interesting characters from Japanese Manga (graphic novels).
   - Schedule: Tuesdays at 7pm
   - Max attendance: 15 people
   ```

4. En la parte superior derecha, hacé clic en el área [MENU] **Assignees** y seleccioná **Copilot**.

---

## Paso 2: Colaborar con Copilot

Una vez asignado Copilot a tu Issue, vas a notar que automáticamente inició un Pull Request (PR) y lo vinculó a tu issue. Revisar el trabajo de Copilot es igual que revisar el código de un compañero humano.

### Teoría: Entendiendo el flujo de colaboración de Copilot

Copilot brinda transparencia a través de varios canales dentro del Pull Request:

- **Descripción del Pull Request:** Copilot la actualiza continuamente a medida que avanza. Vas a ver cómo pasa de una copia inicial del issue, a una lista de acciones concretas, y finalmente a un resumen de finalización.
- **Sesiones del Coding Agent:** Copilot trabaja en "sesiones". Cada vez que asignás una tarea o das feedback, comienza una nueva sesión.
- **Logs en vivo:** Podés hacer clic en el botón **View session** en la línea de tiempo del PR para ver en tiempo real la lógica, el análisis de archivos y los pasos de implementación de Copilot.

**Cómo dar feedback:** la clave para disparar una nueva sesión de codificación es usar la mención `@copilot`. Copilot ignora los comentarios normales dirigidos a humanos, pero reacciona de inmediato si lo mencionás en un comentario o en una revisión de PR.

### Actividad 1: Ver el progreso de Copilot

1. [BROWSER] Navegá al Pull Request referenciado en tu issue "Manga Maniacs".
2. Observá cómo la descripción del PR se actualiza en tres fases:
   - **Fase 1:** copia inicial de los requisitos del issue.
   - **Fase 2:** un plan con acciones concretas.
   - **Fase 3:** un resumen final de los cambios realizados.
3. Desplazate por la línea de tiempo y hacé clic en el botón **View session** para ver el journal en vivo del trabajo de Copilot.
4. Esperá a que la sesión finalice y a que Copilot te solicite como revisor antes de continuar.

### Actividad 2: Dar feedback a Copilot

1. [BROWSER] En el Pull Request, hacé clic en la [TAB] pestaña **Files changed** y luego en el botón **Add your review**.
2. Pasá el mouse sobre una línea de la nueva entrada de la actividad de Manga y hacé clic en el ícono **+** para dejar un comentario.
3. Ingresá el siguiente feedback para darle más "personalidad" a la descripción:

   ```
   @copilot Please change this description to be inspired by Japanese Manga. It needs more personality to attract students.
   ```

4. Hacé clic en **Start a review**, luego en **Finish your review** (arriba) y seleccioná **Submit Review**.
5. Observá la línea de tiempo del PR para ver el inicio de una nueva sesión del agente.

### Actividad 3: Guiar a Copilot en medio de la sesión (Opcional)

1. Si la sesión sigue activa, hacé clic en **View session**.
2. Usá el panel de chat en la parte inferior de los logs de la sesión para dar una actualización de último momento:

   ```
   There is a slight change of plans—we got a bigger classroom. Let's move the schedule to 5PM Tuesday and change the maximum participants to 25.
   ```

3. Esperá a que Copilot termine de implementar tanto la descripción con "espíritu manga" como las actualizaciones de horario.

### Actividad 4: Finalizar y hacer merge

1. Una vez que Copilot termine y vuelva a solicitar tu revisión, verificá los cambios en la [TAB] pestaña **Files changed**.
2. Hacé clic en **Ready for Review** si el PR está en modo borrador.
3. Hacé clic en el botón **Merge pull request** y luego en **Confirm merge** para agregar el club Manga Maniacs al sitio.

---

## Paso 3: Preparar el entorno de Copilot

Para que el desarrollo sea confiable para todos, Copilot necesita guías específicas del repositorio y un entorno preconfigurado. Esto reduce errores y ahorra tiempo al evitar instalaciones ad-hoc.

### Teoría: Personalizando el entorno de Copilot

Podés personalizar el comportamiento y el espacio de trabajo de Copilot mediante dos métodos principales:

- **Copilot Instructions** (`.github/copilot-instructions.md`): brinda contexto de alto nivel, estándares y preferencias de comunicación. Es donde le indicás a Copilot cómo hablarle a usuarios no técnicos y qué reglas arquitectónicas seguir.
- **Copilot Setup Steps** (`copilot-setup-steps.yml`): un workflow particular de GitHub Actions que pre-instala dependencias (como librerías de Python) y servicios (como MongoDB). Esto asegura que Copilot pueda ejecutar o testear tu código de inmediato.

### Actividad 1: Crear instrucciones para guiar a Copilot

1. [BROWSER] Navegá a la [TAB] pestaña **Code** de tu repositorio.
2. Creá una nueva rama llamada: `prepare-environment`.
3. Abrí el archivo `.github/copilot-instructions.md` para editarlo.
4. Reemplazá el texto de ejemplo con la siguiente configuración:

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

5. Hacé clic en **Commit changes** (arriba a la derecha) y luego confirmá con **Commit changes** nuevamente.

### Actividad 2: Preparar el entorno de codificación (Workflow)

1. Asegurate de seguir en la rama `prepare-environment`.
2. Navegá al directorio `.github/workflows/`.
3. Hacé clic en **Add file > Create new file** y nombralo `copilot-setup-steps.yml`.
4. Pegá la siguiente configuración de workflow:

   ```yaml
   name: "Copilot Setup Steps"
   on: workflow_dispatch
   jobs:
     # Este debe ser el nombre exacto del job. Si difiere, Copilot lo ignorará.
     copilot-setup-steps:
       runs-on: ubuntu-latest

       # Levanta un servicio de MongoDB para que Copilot lo use durante su sesión.
       services:
         mongo:
           image: mongo:7
           ports:
             - 27017:27017
       # Otorga a Copilot acceso temprano para leer el contenido del repositorio.
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

5. Hacé clic en **Commit changes** (arriba a la derecha) y luego confirmá con **Commit changes** nuevamente.
6. Andá a la [TAB] pestaña **Pull requests** y hacé clic en **Compare & pull request** desde `prepare-environment` hacia `main`.
7. Esperá a que el chequeo de validación (Mona) confirme que los archivos son correctos.
8. Una vez confirmado, hacé clic en **Merge Pull Request** para finalizar la configuración y luego en **Confirm merge**.

---

## Paso 4: Gestionar múltiples tareas con el Panel de Agentes

Con el entorno de Copilot ya preparado, podés abordar mejoras más complejas para el sitio de Actividades Extracurriculares. En lugar de asignar issues de a uno, podés usar el **Agents Panel** para manejar varios trabajos a la vez.

### Teoría: Delega desde cualquier lugar con el Agents Panel

El Agents Panel es una capa liviana sobre GitHub que funciona como un hub centralizado para tus flujos agénticos. Permite seguir el trabajo en segundo plano de Copilot en tiempo real sin salir de tu código o discusiones.

**Características clave del Agents Panel:**

- 🛠️ **Asignación en segundo plano:** delegá nuevas tareas a Copilot al instante.
- 👀 **Monitoreo en tiempo real:** seguí el estado y progreso de las tareas en distintos repositorios.
- 🔗 **Deep Linking:** saltá directamente a un pull request o log de sesión específico cuando estés listo para revisar.

📝 Nota: se accede al panel haciendo clic en el botón **Agents** en la barra de navegación superior, o visitando https://github.com/copilot/agents.

### Actividad 1: Asignar tareas mediante el Agents Panel

1. [BROWSER] Abrí el Copilot Agents panel desde la barra de navegación superior.
2. Seleccioná el repositorio: `GithubUserName/skills-expand-your-team-with-copilot`. **Nota:** reemplazá `GithubUserName` por tu propio usuario de GitHub.
3. Asegurate de que la rama esté configurada en `main`.
4. Ingresá el siguiente prompt en el panel para iniciar una tarea en segundo plano:

   ```
   Integrate social sharing buttons so users can easily share activities with their friends.
   ```

5. Monitoreá el panel para ver las tareas aparecer con su estado actual.

### Actividad 2: Implementar issues simultáneamente

1. [BROWSER] Navegá a la [TAB] pestaña **Issues** de tu repositorio en una nueva pestaña.
2. Buscá y abrí los siguientes dos issues:
   - **Difficulty Tracks**
   - **Dark Mode**
3. Asigná `@copilot` como responsable en ambos issues al mismo tiempo.
4. Volvé al Agents Panel; ahora vas a ver estos issues listados junto a tu tarea de social sharing.
5. Hacé clic en **View session** en cualquier tarea para ver a Copilot ejecutando tu workflow personalizado `copilot-setup-steps.yml`.
6. Esperá a que Copilot termine el trabajo de al menos una de las tareas.
7. Hacé clic en el botón **View Pull Request** dentro del panel para abrir el PR resultante.
8. Revisá la descripción generada por la IA y la [TAB] pestaña **Files changed**.
9. Hacé clic en **Merge pull request** y **Confirm merge** una vez que estés conforme con los resultados.

---

## Repaso

¡Felicitaciones, completaste este ejercicio y aprendiste mucho sobre el GitHub Copilot coding agent!

Resumen de lo logrado:

- Aprendiste las capacidades y el uso del Copilot coding agent.
- Inspeccionaste la lógica que usó Copilot para implementar tu issue.
- Diste feedback para que Copilot refine la implementación.
- Aprendiste a configurar y personalizar el entorno de trabajo de Copilot.
- Usaste Copilot para trabajar en paralelo en múltiples issues.
- Aprendiste a asignar y seguir tareas mediante el Agents Panel.

### ¿Qué sigue?

- Revisá los demás ejercicios de GitHub Skills.
- Profundizá en la personalización del entorno de Copilot con el ejercicio *Customize your GitHub Copilot experience*.
- Aprendé más sobre el uso de Model Context Protocol en el entorno de Copilot con el ejercicio *Integrate MCP with Copilot*.

### Recursos adicionales

- Mejores prácticas con Copilot coding agent para obtener mejores resultados.
- Cómo extender el GitHub Copilot coding agent con servidores adicionales de Model Context Protocol.
- Prácticas para el uso responsable del Copilot coding agent.
- Distintas formas de asignar trabajo al Copilot Coding Agent en VS Code.
