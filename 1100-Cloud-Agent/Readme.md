
# GitHub Copilot Cloud Agent

## Understanding and enabling el GitHub Copilot Cloud Agent

El **GitHub Copilot Cloud Agent** es un asistente autónomo de desarrollo que funciona dentro de GitHub. Recibe tareas claramente definidas, explora el código, crea una rama, genera un plan de implementación y prepara cambios, manteniendo al usuario en control de cuándo abrir un Pull Request.

### Disponibilidad

- **Planes:** Copilot Pro, Copilot Pro+, Copilot Business y Copilot Enterprise.
- **Repositorios:** repositorios alojados en GitHub, excepto los pertenecientes a cuentas de usuario administradas o aquellos donde el agente esté deshabilitado.

### Tareas que puede realizar

- Corregir bugs y regresiones.
- Implementar nuevas funcionalidades incrementales.
- Mejorar la cobertura de tests o generar tests faltantes.
- Crear o actualizar documentación.
- Resolver deuda técnica y tareas pendientes.

### Formas de delegar trabajo

- **Asignar un issue a Copilot:** desde GitHub.com, GitHub Mobile o mediante API/CLI.
- **Solicitar cambios de código:** desde el panel Agents de GitHub, Copilot Chat, el IDE u otra herramienta agéntica compatible con MCP, o Raycast en macOS.

Al finalizar, el agente solicita revisión. Se puede mencionar `@copilot` en un comentario del Pull Request para pedirle que itere sobre su trabajo.

### Diferencias con asistentes tradicionales del IDE

Los asistentes tradicionales ayudan a escribir código localmente, pero dejan al desarrollador tareas como crear ramas, hacer commits, realizar push, escribir la descripción del PR e iterar sobre los cambios.

Con **Copilot Cloud Agent**:

- Todo el trabajo ocurre mediante commits en GitHub.
- Automatiza la creación de ramas, mensajes de commit y generación de código.
- El usuario decide si y cuándo abrir un Pull Request.
- El trabajo queda visible en logs de sesión e historial de PRs.
- La interacción puede realizarse mediante comentarios de revisión del PR.
- Los compañeros pueden visualizar los pasos y colaborar.

### Cloud Agent vs. Agent Mode del IDE

- **Cloud Agent:** funciona autónomamente en un entorno basado en GitHub Actions para completar tareas asignadas mediante issues o Copilot Chat.
- **Agent Mode (Copilot Edits):** realiza ediciones autónomas localmente dentro de la sesión del IDE.

### Habilitación

- **Repositorios de una organización:** la disponibilidad es administrada por los administradores de la organización o empresa.
- **Repositorios personales:** se configura desde las opciones de la cuenta.

### Costos: GitHub Actions + PRUs

Copilot Cloud Agent utiliza dos recursos principales:

- **GitHub Actions minutes:** para el entorno temporal de compilación y pruebas donde trabaja el agente.
- **Copilot Premium Request Units (PRUs):** para el razonamiento de modelos avanzados.

Desde el **4 de junio de 2025**, el agente utiliza una solicitud premium por cada solicitud de modelo que realiza. Dentro de las asignaciones mensuales de Actions y solicitudes premium, las tareas pueden ejecutarse sin cargos adicionales.

Se recomienda utilizar PRUs especialmente cuando aportan valor, como en ediciones de múltiples archivos, generación de tests y cambios amplios que requieren mayor razonamiento. Las modificaciones simples pueden requerir menos pasos intensivos en PRUs.

---

## Seguridad, riesgos y limitaciones del Copilot Cloud Agent

GitHub Copilot Cloud Agent está diseñado considerando seguridad y gobernanza. Respeta los controles existentes de la organización y agrega mecanismos propios de protección.

### Modelo de seguridad y protecciones

- **Gobernanza:** la disponibilidad está controlada por configuraciones de organización y empresa; las políticas de seguridad existentes continúan aplicándose.
- **Entorno restringido:** funciona dentro de un sandbox de GitHub Actions con acceso a Internet protegido por firewall y acceso de solo lectura al repositorio.
- **Restricción de ramas:** solo puede crear y hacer push a ramas que comiencen con `copilot/`; las protecciones y comprobaciones requeridas de las ramas siguen aplicándose.
- **Permisos:** solo responde a usuarios con permisos de escritura. Los comentarios de otros usuarios son ignorados.
- **Colaboradores externos:** los PRs creados por el agente requieren aprobación de un usuario con permisos de escritura antes de ejecutar Actions. El usuario que solicitó el PR no puede aprobarlo.
- **Cumplimiento y atribución:** los commits se realizan conjuntamente con el desarrollador que asignó la tarea o solicitó el PR, manteniendo clara la atribución. Las reglas de aprobaciones requeridas continúan vigentes.

### Riesgos y mitigaciones

#### El agente puede hacer push de código

**Mitigaciones:**
- Solo usuarios con permisos de escritura pueden activar trabajos del agente.
- Los pushes están restringidos a ramas `copilot/`, no a `main`/`master`.
- Las credenciales del agente permiten únicamente un push simple.
- Los workflows de GitHub Actions no se ejecutan hasta que un usuario con permisos de escritura selecciona **Approve and run workflows**.
- El solicitante no puede aprobar el PR del agente.

#### Acceso a información sensible

El acceso a Internet del agente está restringido mediante firewall de forma predeterminada. Puede personalizarse o deshabilitarse según la política.

#### Prompt injection

Los caracteres ocultos, como comentarios HTML, se filtran antes de pasar la entrada al agente, reduciendo el riesgo de instrucciones maliciosas ocultas en comentarios o issues.

A pesar de estas protecciones, los resultados deben revisarse cuidadosamente, al igual que el código producido por cualquier integrante del equipo.

### Limitaciones conocidas

#### Limitaciones del workflow

- Solo puede realizar cambios en el mismo repositorio donde se encuentra el issue o PR asignado.
- Por defecto, el contexto está limitado al repositorio asignado; puede ampliarse mediante MCP.
- Abre exactamente un Pull Request por tarea.
- No puede modificar un PR existente que no haya creado.

#### Limitaciones de compatibilidad

- No firma commits. Si se requieren commits firmados, es necesario reescribir el historial antes del merge.
- Requiere runners Ubuntu x64 alojados en GitHub.
- No admite self-hosted runners.
- No está disponible para repositorios personales pertenecientes a cuentas de usuario administradas.
- No respeta las exclusiones de contenido; puede ver y actualizar archivos excluidos.
- La política **Suggestions matching public code** no se aplica al agente; pueden no proporcionarse referencias.
- Funciona únicamente con repositorios alojados en GitHub.
- No se puede cambiar el modelo de IA utilizado; el modelo es seleccionado por GitHub.

---

## Assigning, tracking, and troubleshooting Copilot Cloud Agent tasks

El **GitHub Copilot Cloud Agent** funciona como un integrante autónomo del equipo dentro de GitHub. Una vez habilitado, permite asignarle tareas, seguir su progreso y guiar su trabajo mediante comentarios en sus Pull Requests.

### Asignar issues a Copilot

Al asignar un issue a Copilot:

1. Copilot agrega una reacción 👀 al issue.
2. Crea una rama dedicada `copilot/`.
3. Abre un Pull Request en estado draft vinculado al issue.
4. Inicia una sesión del agente dentro de un entorno basado en GitHub Actions.
5. Realiza commits en la rama y actualiza el cuerpo del PR con mensajes de estado.
6. Al finalizar, publica el evento **Copilot finished work** y solicita revisión.

En GitHub.com se asigna el issue desde **Issues → Assignees → Copilot**. Copilot recibe el título, descripción y comentarios existentes del issue en el momento de la asignación. Los comentarios posteriores del issue no son vistos por el agente; la información nueva debe agregarse como comentario directamente en el PR del agente.

También se pueden asignar issues desde:

- La lista de issues del repositorio.
- GitHub Projects.
- GitHub Mobile.
- GitHub CLI mediante `gh issue edit`.

### Asignación mediante API

La asignación programática puede realizarse mediante la **GraphQL API**:

1. Verificar que el coding agent esté disponible consultando `suggestedActors` y comprobando que aparezca `copilot-swe-agent`.
2. Obtener el ID del repositorio.
3. Para crear y asignar un issue, utilizar `createIssue` con el ID del repositorio y el ID del bot de Copilot.
4. Para asignar un issue existente, obtener su ID y utilizar `replaceActorsForAssignable`.

### Seguimiento del progreso

Copilot proporciona diferentes señales durante el trabajo:

- **Confirmación inmediata:** agrega una reacción 👀 al issue.
- **Creación del PR:** abre un draft PR vinculado al issue.
- **Sesión activa:** aparece el evento **Copilot started work** en la timeline del PR; actualiza el cuerpo del PR y realiza commits.
- **Logs de sesión:** desde la página Agents se pueden consultar sesiones pasadas y actuales. **View session** permite ver las acciones en tiempo real y **Stop session** detener la sesión.
- **Finalización:** aparece **Copilot finished work** y se solicita una revisión.

### Iterar con Copilot

La interacción se realiza mediante el flujo normal de revisión:

- Mencionar `@copilot` en un comentario del Pull Request para solicitar cambios.
- Solo se procesan comentarios de usuarios con permisos de escritura.
- Copilot agrega una reacción 👀 para confirmar que recibió la solicitud.
- Luego aparece **Copilot started work** en la timeline mientras retoma la tarea.

### Aprobaciones y workflows

Los Pull Requests creados por Copilot siempre están en estado **draft**.

- Requieren aprobación humana antes del merge.
- Los workflows de GitHub Actions no se ejecutan automáticamente.
- Para ejecutarlos, se debe seleccionar **Approve and run workflows** en el cuadro de merge.
- El desarrollador que solicitó la creación del PR no puede aprobarlo.
- Esto mantiene las reglas de revisiones requeridas y garantiza una revisión independiente.

### Troubleshooting

- **Copilot no aparece en Assignees:** verificar que el plan sea Pro, Pro+, Business o Enterprise y que el agente no esté deshabilitado a nivel de organización o repositorio.
- **Repositorios personales de Enterprise Managed User (EMU):** el agente no está disponible; utilizar repositorios propiedad de una organización.
- **"Cannot create a pull request" desde Chat:** verificar que el agente esté disponible. En IDEs, mencionar `@github` en el prompt.
- **Se asignó un issue pero no ocurre nada:** actualizar la página y buscar la reacción 👀 y luego el draft PR.
- **PR creado pero sin progreso:** revisar la timeline buscando **Copilot started work** y abrir los session logs.
- **El agente no responde a un comentario:** comprobar permisos de escritura y que se haya mencionado `@copilot` en el PR del agente.
- **El agente parece bloqueado:** las sesiones pueden recuperarse y tienen un timeout de una hora. Se puede reintentar desasignando y reasignando el issue o publicando nuevamente el comentario.
- **Actions no se ejecutan:** seleccionar **Approve and run workflows**.
- **Los pushes no pasan CI:** proporcionar instrucciones claras a nivel de repositorio mediante `.github/copilot-instructions.md` para que el agente pueda validar su trabajo con tests y linters.
- **Advertencias del firewall:** Internet está restringido por defecto; las advertencias muestran la dirección y comando bloqueados. El firewall puede ajustarse según las necesidades.
- **Imágenes no detectadas:** las imágenes tienen un tamaño máximo de **3,00 MiB**; las imágenes más grandes se eliminan.

---

## Customizing, extending, and validating the Copilot Cloud Agent

GitHub Copilot Cloud Agent funciona dentro de un entorno seguro y efímero de GitHub Actions. Se puede configurar previamente el entorno para mejorar confiabilidad y velocidad, extender sus capacidades mediante **Model Context Protocol (MCP)** y aplicar prácticas de testing y validación antes del merge.

### Preconfigurar el entorno de desarrollo

#### Instalar herramientas y dependencias con `copilot-setup-steps.yml`

Crear `.github/workflows/copilot-setup-steps.yml` en la rama predeterminada del repositorio.

El workflow debe definir un único job llamado `copilot-setup-steps` e incluir los pasos necesarios para instalar dependencias o configurar herramientas.

Ejemplo para TypeScript:

name: "Copilot Setup Steps"

on:
  workflow_dispatch:
  push:
    paths:
      - .github/workflows/copilot-setup-steps.yml
  pull_request:
    paths:
      - .github/workflows/copilot-setup-steps.yml

jobs:
  copilot-setup-steps:
    runs-on: ubuntu-latest
    permissions:
      contents: read
    steps:
      - name: Checkout code
        uses: actions/checkout@v5
      - name: Set up Node.js
        uses: actions/setup-node@v4
        with:
          node-version: "20"
          cache: "npm"
      - name: Install JavaScript dependencies
        run: npm ci

Las claves de configuración permitidas para el job `copilot-setup-steps` son:

- `steps`
- `permissions`
- `runs-on`
- `container`
- `services`
- `snapshot`
- `timeout-minutes` (≤ 59)

El `fetch-depth` de `actions/checkout` es sobrescrito para permitir un rollback seguro.

El workflow puede ejecutarse de forma independiente para validarlo y luego se ejecuta automáticamente antes de iniciar el agente.

### Larger GitHub-hosted runners

- Agregar primero los runners de mayor tamaño.
- En `copilot-setup-steps.yml`, configurar `runs-on` con el label o grupo correspondiente, por ejemplo `ubuntu-4-core`.
- Solo se admiten runners Ubuntu x64.
- No se admiten self-hosted runners.

### Git LFS

Si el repositorio utiliza Git Large File Storage, habilitarlo en los pasos de configuración:

jobs:
  copilot-setup-steps:
    runs-on: ubuntu-latest
    permissions:
      contents: read
    steps:
      - uses: actions/checkout@v5
        with:
          lfs: true

### Personalización del firewall

El acceso a Internet está limitado por defecto para reducir el riesgo de exfiltración. Puede personalizarse o deshabilitarse según la política de la organización.

---

## Extender Copilot Cloud Agent con Model Context Protocol (MCP)

**MCP** es un estándar abierto para conectar LLMs con herramientas y datos. Copilot Cloud Agent puede utilizar herramientas proporcionadas por servidores MCP locales o remotos para ampliar sus capacidades.

- El agente admite **herramientas MCP**, pero no recursos ni prompts.
- Los servidores MCP remotos que requieren OAuth no son compatibles.

### Servidores MCP predeterminados

- **GitHub MCP Server:** permite acceder a issues, PRs y datos de GitHub mediante un token de solo lectura limitado al repositorio actual por defecto. El token puede personalizarse.
- **Playwright MCP Server:** permite leer, interactuar y tomar capturas de páginas web accesibles desde el entorno del agente, incluyendo `localhost` y `127.0.0.1`.

### Configuración del repositorio

Los administradores pueden declarar servidores MCP mediante una configuración JSON en el repositorio.

Una vez configurados, el agente utiliza autónomamente las herramientas disponibles, sin solicitar aprobación en cada uso.

### Buenas prácticas

- Revisar los servidores MCP de terceros considerando su rendimiento y la calidad de sus resultados.
- Preferir herramientas de lectura.
- Si existen herramientas de escritura, permitir únicamente las necesarias.
- Validar cuidadosamente la configuración MCP antes de guardarla.

---

## Testing y validación del resultado del agente

El usuario mantiene la responsabilidad sobre la calidad y seguridad del código generado.

- Ejecutar **CI**, incluyendo tests, linters y análisis de seguridad, en cada PR generado por el agente. Estos checks no se ejecutan hasta seleccionar **Approve and run workflows**.
- Inspeccionar manualmente las áreas de alto impacto o sensibles.
- Solicitar al agente que genere tests, por ejemplo, tests unitarios Jest para todas las funciones de `src/utils/` siguiendo el estilo del repositorio. La generación de tests en múltiples archivos consume PRUs.
- Utilizar **rulesets** para exigir que los PRs del agente superen tests, scanning y linting antes del merge.
- Etiquetar los PRs del agente, por ejemplo `agent-refactor` o `agent-tests`, para facilitar su monitoreo, clasificación y reversión.
- Ajustar las instrucciones de `.github/copilot-instructions.md` cuando se detecten errores repetitivos.
- Revertir rápidamente los cambios cuando sea necesario y solicitar nuevas modificaciones al agente.

### Uso intencional de PRUs para validación

Utilizar PRUs para tareas de validación más profundas, como:

- Ampliación de cobertura de tests.
- Auditorías en múltiples directorios.
- Análisis de áreas de riesgo.

Las verificaciones ligeras consumen menos PRUs, por lo que deben utilizarse de forma intencional para maximizar su valor.

---

## Uso responsable de GitHub Copilot Cloud Agent en GitHub.com

**Copilot Cloud Agent** es un agente autónomo y asíncrono de desarrollo de software integrado en GitHub. Puede tomar una tarea desde un issue o Copilot Chat, crear una rama, explorar el código, generar un plan de implementación y preparar código, dejando al usuario decidir si y cuándo abrir un Pull Request.

Puede generar cambios adaptados a la descripción y configuración proporcionadas para tareas como:

- Corrección de bugs.
- Implementación de nuevas funcionalidades incrementales.
- Prototipado.
- Documentación.
- Mantenimiento del código.

Si se crea un Pull Request, el agente puede iterar con el usuario a partir de sus comentarios y revisiones.

Durante el trabajo, el agente dispone de un entorno de desarrollo efímero donde puede:

- Modificar código.
- Ejecutar tests automatizados.
- Ejecutar linters.

Ha sido evaluado en diversos lenguajes de programación, con **inglés como idioma principal soportado**.

### Funcionamiento de extremo a extremo

#### Procesamiento del prompt

La tarea proporcionada mediante un issue, comentario de Pull Request o Copilot Chat se combina con información contextual relevante para formar el prompt.

Las entradas pueden incluir:

- Lenguaje natural.
- Fragmentos de código.
- Imágenes.

#### Análisis mediante el modelo de lenguaje

El prompt se procesa mediante un modelo de lenguaje que analiza la entrada para razonar sobre la tarea y utilizar las herramientas necesarias.

#### Generación de respuesta

El modelo genera una respuesta basada en el análisis, que puede incluir:

- Sugerencias en lenguaje natural.
- Sugerencias de código.

#### Formateo de resultados

Después de la primera ejecución, el agente actualiza la descripción del Pull Request con los cambios realizados. Puede incluir información adicional sobre recursos a los que no pudo acceder y sugerencias para resolver esas limitaciones.

El usuario puede proporcionar feedback mediante comentarios en el Pull Request o mencionando explícitamente `@copilot`. El feedback vuelve al modelo para su análisis y el agente responde con los cambios actualizados.

El usuario es responsable de revisar y validar las respuestas generadas por Copilot para garantizar que sean correctas y apropiadas. GitHub también realiza **red teaming** como parte de su proceso de desarrollo para comprender y mejorar la seguridad del agente.

### Casos de uso

- **Mantenimiento del código:** correcciones de seguridad, actualización de dependencias y refactorizaciones específicas.
- **Documentación:** actualización y creación de documentación.
- **Desarrollo de funcionalidades:** implementación de solicitudes incrementales.
- **Mejora de cobertura de tests:** desarrollo de suites adicionales de pruebas.
- **Prototipado:** creación de nuevos proyectos y conceptos.

### Mejorar el rendimiento del Copilot Cloud Agent

Para mejorar los resultados, las tareas deben estar bien delimitadas proporcionando:

- Una descripción clara del problema o trabajo requerido.
- Criterios de aceptación completos sobre cómo debe ser una solución correcta, por ejemplo, si debe incluir tests unitarios.
- Indicaciones sobre los archivos que deben modificarse.

### Personalizar el contexto

Copilot Cloud Agent utiliza como contexto el prompt, los comentarios y el código del repositorio. Se pueden agregar **custom Copilot instructions** para que el agente comprenda cómo construir, probar y validar sus cambios.

También se puede personalizar:

- El entorno de desarrollo.
- El firewall.
- Las capacidades mediante MCP.

### Usar Copilot como herramienta, no como reemplazo

Siempre se debe revisar y probar el contenido generado por el agente antes del merge para comprobar que cumple los requisitos y no contiene errores o problemas de seguridad.

### Prácticas de desarrollo seguro y revisión de código

Aunque Copilot Cloud Agent puede generar código sintácticamente correcto, este no necesariamente es seguro. Se deben mantener buenas prácticas de desarrollo seguro:

- Evitar secretos hardcodeados.
- Prevenir vulnerabilidades de inyección.
- Realizar testing riguroso.
- Ejecutar análisis de propiedad intelectual.
- Ejecutar verificaciones de vulnerabilidades.

### Proporcionar feedback

Ante problemas o limitaciones se puede utilizar el botón de **thumbs-down** debajo de una respuesta del agente o compartir feedback en el foro de discusión de la comunidad.

### Mantenerse actualizado

Copilot Cloud Agent continúa evolucionando. Es necesario monitorear nuevos riesgos de seguridad y buenas prácticas a medida que aparecen.

---

## Medidas de seguridad del Copilot Cloud Agent

### Evitar escalación de privilegios

- Copilot Cloud Agent solo responde a interacciones de usuarios con permisos de **write**.
- Los workflows de Actions activados por PRs del agente requieren aprobación de un usuario con permisos de escritura antes de ejecutarse.
- Los caracteres ocultos que no se muestran en GitHub.com se filtran para reducir los riesgos de prompt injection.

### Limitar los permisos de Copilot

- El agente solo accede al repositorio dentro del cual está configurado; no puede acceder a otros repositorios.
- Los pushes están limitados a ramas cuyo nombre comienza con `copilot/`; no puede realizar push a la rama predeterminada.
- El agente no tiene acceso en runtime a los secrets o variables de Actions de la organización o repositorio.
- Solo se le proporcionan los secrets y variables agregados específicamente al entorno de Copilot.

### Prevenir la exfiltración de datos

El firewall está habilitado por defecto para prevenir la exfiltración accidental o maliciosa de código o información sensible.

---

## Limitaciones del Copilot Cloud Agent

El rendimiento puede variar según el código y las entradas utilizadas.

- **Alcance y calidad limitados:** el LLM puede tener dificultades con determinadas estructuras de código o lenguajes poco comunes; la calidad varía según la cobertura del lenguaje.
- **Sesgos potenciales:** los datos de entrenamiento y el contexto recuperado pueden contener sesgos; el agente puede inclinarse hacia determinados lenguajes o estilos.
- **Riesgos de seguridad:** el código generado se basa en el contexto del repositorio y podría exponer información sensible si no se revisa; es necesaria una revisión exhaustiva.
- **Código inexacto:** el código puede parecer correcto pero ser semántica o sintácticamente incorrecto o no coincidir con la intención. Se debe validar su adecuación, patrones y estilo.
- **Código público:** el agente puede producir coincidencias o coincidencias cercanas con código público incluso cuando **Block** está configurado; pueden no proporcionarse referencias.
- **Aspectos legales y regulatorios:** se debe garantizar el cumplimiento de las obligaciones aplicables y evitar usos prohibidos por los términos de servicio y códigos de conducta.

