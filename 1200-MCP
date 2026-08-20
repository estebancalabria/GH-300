# Servidor MCP de GitHub

## Introducción

El servidor MCP de GitHub es una forma hospedada, segura y escalable de integrar GitHub en flujos de trabajo asistidos por IA. Está basado en el **Protocolo de contexto de modelo (MCP)**, introducido por Anthropic, y amplía GitHub Copilot y otras herramientas de IA para:

* Automatizar tareas.
* Administrar repositorios.
* Mejorar la experiencia de desarrollo con asistencia de IA y reconocimiento del contexto.

Está disponible para **Visual Studio Code** y se ampliará a otros editores y plataformas.

### Objetivos de aprendizaje

Al finalizar, se podrá:

* Comprender qué son MCP y el servidor MCP de GitHub y su utilidad.
* Configurar el servidor MCP de GitHub en Visual Studio Code.
* Usar el servidor MCP de GitHub con Copilot Chat para automatizar tareas de desarrollo.
* Identificar y resolver problemas comunes.

### Prerrequisitos

* Cuenta de GitHub.
* Visual Studio Code u otro editor compatible con MCP.
* Para organizaciones o empresas con **Copilot Business** o **Copilot Enterprise**, la directiva **"Servidores MCP en Copilot"** debe estar habilitada.

Opcionalmente:

* Token de acceso personal (**PAT**) de GitHub para configuración avanzada y control de permisos.
* Docker para experimentar con una configuración de servidor local.

---

## Simplificación del flujo de trabajo de IA con el servidor MCP de GitHub

El servidor MCP de GitHub proporciona una forma sencilla y escalable de integrar GitHub Copilot con herramientas relacionadas y flujos de trabajo.

Basado en MCP, reduce la fricción de configuración y permite funcionalidades como la evaluación de prioridades de problemas y la búsqueda semántica.

### ¿Qué es MCP?

**MCP (Protocolo de contexto de modelo)** funciona como un estándar de conexión para herramientas de IA, proporcionando una forma coherente y segura de conectar modelos de IA con las herramientas y fuentes de datos que necesitan.

MCP ofrece:

* Acceso a una biblioteca creciente de herramientas que los modelos de IA pueden utilizar.
* Flexibilidad para trabajar con diferentes proveedores de IA manteniendo flujos de trabajo coherentes.
* Integración con el entorno de desarrollo y los procesos existentes.

### Cómo se conectan los clientes MCP a servidores y servicios

Un cliente MCP, como Claude, un IDE u otra herramienta, puede interactuar con servidores MCP y servicios conectados de tres formas:

#### Comunicación local con datos locales

El cliente MCP se comunica directamente con un servidor MCP que se ejecuta en la máquina, y este se conecta a fuentes de datos locales como archivos, bases de datos u otros recursos.

**Cuándo usarlo:** desarrollo local o acceso rápido a datos que permanecen privados en la máquina.

#### Servidor local como puente a servicios remotos

El cliente MCP se conecta a un servidor local que, a su vez, se comunica con un servicio remoto mediante sus API web.

**Cuándo usarlo:** cuando una herramienta local necesita consultar o actualizar información remota y se beneficia de un servidor intermedio para almacenamiento en caché, comprobaciones de seguridad o preprocesamiento.

#### Comunicación remota a través de Internet

El cliente MCP se conecta a un servidor MCP completamente remoto, que se comunica con otros servicios mediante API web.

**Cuándo usarlo:** cuando el recurso o cálculo necesario no puede producirse localmente, como procesos basados en la nube, plataformas SaaS o integraciones de terceros disponibles únicamente en línea.

---

## ¿Por qué usar el servidor MCP de GitHub?

Los servidores MCP locales normalmente requieren Docker, administración de tokens y configuración manual, lo que puede ralentizar la configuración y dificultar la integración con clientes web como GitHub.com.

El servidor hospedado de GitHub permite una conexión rápida y sencilla sin archivos Docker ni configuración manual. Puede utilizar herramientas de IA como GitHub Copilot Chat en web y móvil y escalar los proyectos a medida que crecen.

También admite inicio de sesión empresarial seguro y funcionalidades avanzadas como búsqueda semántica de código y correcciones automatizadas.

### Ventajas

* Elimina la necesidad de archivos de configuración manual o Docker.
* Proporciona autenticación OAuth sencilla con un solo clic.
* Permite trabajar en entornos web, de escritorio y móviles.
* Admite proveedores de identidad empresariales como Entra y Auth0.
* Escala automáticamente según las necesidades de uso.

---

## Servidor MCP de GitHub en acción

El servidor MCP de GitHub es un servidor de código abierto que conecta GitHub Copilot y otras herramientas de IA directamente con los repositorios.

Permite:

* Analizar y resumir código para comprender proyectos.
* Crear y administrar problemas y solicitudes de incorporación de cambios.
* Automatizar la evaluación de prioridades del repositorio y el seguimiento de tareas.
* Agregar problemas, editar archivos y crear ramas.
* Clasificar pull requests y problemas para priorizarlos.

Actualmente ofrece **más de 30 herramientas**.

---

# Configuración, conexión y uso del servidor MCP de GitHub en VS Code

El servidor MCP de GitHub puede configurarse en Visual Studio Code para incorporar flujos de trabajo de IA directamente al entorno de desarrollo.

La configuración incluye:

* OAuth.
* Token de acceso personal (PAT).
* Configuración local opcional mediante Docker.
* Uso con Copilot Chat.
* Solución de problemas comunes.

## Configuración mediante OAuth

1. En Visual Studio Code, abrir la paleta de comandos con `Ctrl+Mayús+P` en Windows/Linux o `Cmd+Mayús+P` en Mac.
2. Escribir **MCP: agregar el servidor** y presionar Enter.
3. Seleccionar **HTTP (HTTP o Server-Sent Events)**.
4. Introducir como dirección del servidor: `https://api.githubcopilot.com/mcp/`.
5. Introducir un identificador de servidor o utilizar el valor predeterminado.
6. Elegir dónde guardar la configuración: configuración de usuario o configuración del área de trabajo.
7. Autorizar con GitHub mediante OAuth seleccionando **Permitir** e iniciando sesión si se solicita.

Después de la instalación, el servidor MCP de GitHub queda disponible en los proyectos de VS Code para automatizar tareas, administrar problemas y analizar código.

## Configuración mediante token de acceso personal

Para utilizar un PAT:

1. Crear un PAT con el ámbito de repositorio y lectura de paquetes en la cuenta de GitHub.

2. Seguir los pasos anteriores, pero cancelar OAuth cuando se solicite.

3. Agregar en el archivo de configuración:

   `"headers": { "Authorization": "Bearer ${input:github_token}" }`

4. Agregar un mensaje de entrada para solicitar el token de forma segura:

   `"inputs": [ { "id": "github_token", "type": "promptString", "description": "GitHub Personal Access Token", "password": true } ]`

5. Reiniciar el servidor MCP en VS Code e introducir el PAT cuando se solicite.

6. El servidor MCP utilizará el PAT para la autorización.

---

## Configuración local con Docker

Para uso local, el servidor MCP requiere **Docker** y autenticación mediante **PAT**. OAuth no se admite en esta configuración.

En GitHub Enterprise Server con restricciones de PAT, solo se puede acceder a los ámbitos de API permitidos por la directiva de la organización. Si todos los puntos de conexión están restringidos, el servidor MCP no estará disponible.

### Configuración

1. Confirmar que Docker está instalado y ejecutándose.
2. Generar un PAT con los ámbitos necesarios.
3. Configurar el servidor local con Docker utilizando:

   * Entrada `github_token` de tipo `promptString`.
   * `password: true`.
   * Servidor `github`.
   * Comando `docker`.
   * Imagen `ghcr.io/github/github-mcp-server`.
   * Variable `GITHUB_PERSONAL_ACCESS_TOKEN` asociada al token introducido.
4. Reiniciar el servidor MCP e introducir el PAT cuando se solicite.

---

## Solución de problemas

Ante problemas con el servidor MCP de GitHub:

* Confirmar que se inició sesión en GitHub desde VS Code.
* Si se utiliza un PAT, verificar que tenga los ámbitos correctos y esté escrito correctamente.
* Revisar la configuración para detectar errores tipográficos o campos faltantes.
* Si se utiliza Docker, comprobar que esté instalado y ejecutándose.
* Reiniciar VS Code o el servidor MCP para resolver problemas temporales de conexión.

---

# Uso del servidor MCP de GitHub con Copilot Chat

Los servidores MCP amplían GitHub Copilot al conectarlo con herramientas y recursos externos. Al combinar MCP con el **modo agente de Copilot**, Copilot puede planear, ejecutar y refinar flujos de trabajo.

## Uso con Copilot Chat

1. Abrir **Chat de Copilot** en Visual Studio Code y cambiar al **modo agente** para activar las herramientas del servidor MCP.
2. Seleccionar **Seleccionar herramientas** para visualizar las funcionalidades disponibles.
3. Utilizar lenguaje natural para tareas como:

   * Crear un nuevo problema.
   * Resumir un repositorio.
   * Obtener información sobre el trabajo.
4. Seguir las indicaciones de Copilot Chat para completar las tareas.

---

## Funcionalidades agente de Copilot y MCP

### Funcionalidades agenticas

El modo agente permite a Copilot:

* Trabajar de forma independiente mediante flujos de trabajo de varios pasos sin instrucciones constantes.
* Tomar decisiones y elegir herramientas o enfoques según el contexto.
* Adaptarse, mejorar e iterar en función de los resultados y comentarios.

El modo agente permite que Copilot controle tareas de forma más autónoma, funcionando como un colaborador que comprende el contexto general.

### Cómo MCP amplía el modo agente

Al agregar servidores MCP, Copilot puede:

* Acceder directamente a datos externos, API y herramientas empresariales.
* Mantener el contexto entre diferentes plataformas sin cambiar de aplicación.
* Completar bucles agentes en los que busca información, analiza resultados y ejecuta los siguientes pasos de forma dinámica.

El flujo pasa de responder a una única petición a trabajar mediante un ciclo de **explorar, adaptar y refinar**.

### Ventajas de combinar MCP con el modo agente

* **Contexto extendido:** Copilot puede obtener información de varios sistemas además del editor de código.
* **Menor esfuerzo manual:** automatiza tareas rutinarias como abrir problemas, administrar flujos de trabajo o ejecutar comprobaciones.
* **Integración sin problemas:** permite realizar tareas que abarcan herramientas y plataformas sin conectores personalizados ni cambios constantes de aplicación.

---

## Procedimientos recomendados

Para aprovechar mejor MCP y el modo agente:

* **Definir claramente los objetivos:** especificar qué debe lograr Copilot y cuál debe ser el resultado final.
* **Proporcionar contexto:** incluir información sobre el proyecto o flujo de trabajo, como vínculos, referencias o pasos anteriores.
* **Establecer límites:** indicar si Copilot debe detenerse en la planificación sin realizar cambios y limitar las herramientas MCP activas cuando sea necesario.
* **Pedir confirmación:** antes de grandes cambios, solicitar que Copilot resuma el plan para aprobarlo o refinarlo.
* **Usar archivos de solicitud o instrucciones:** crear archivos personalizados que orienten el comportamiento de Copilot con servidores MCP específicos y mantengan un comportamiento coherente y alineado con los flujos de trabajo.
