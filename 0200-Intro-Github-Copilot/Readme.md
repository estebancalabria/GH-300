# GitHub Copilot

## Introducción

GitHub Copilot es un asistente para desarrolladores basado en inteligencia artificial que ayuda a trabajar más rápido y con mayor confianza durante todo el ciclo de vida del desarrollo de software.

Utiliza el contexto del código y los comentarios para:

* Generar código.
* Explicar lógica existente.
* Refactorizar implementaciones.
* Corregir errores.
* Escribir pruebas.
* Mantener al desarrollador en el flujo de trabajo.

Las investigaciones mencionadas indican mejoras de productividad y satisfacción al utilizar GitHub Copilot:

* 46 % del código nuevo es escrito mediante IA.
* La productividad general de los desarrolladores es un 55 % más rápida.
* 74 % de los desarrolladores se sienten más centrados en realizar el trabajo que les gusta.

GitHub Copilot fue desarrollado por Microsoft en colaboración con OpenAI y utiliza el sistema OpenAI Codex, entrenado con una alta concentración de código fuente público.

Está disponible como extensión para:

* Visual Studio Code.
* Visual Studio.
* Vim/Neovim.
* IDE de JetBrains.

## Objetivos de aprendizaje

Al finalizar el módulo se podrá:

* Comprender cómo GitHub Copilot ayuda a escribir, comprender y mejorar código mediante sugerencias, explicaciones y generación contextual.
* Comprender las distintas formas de activar GitHub Copilot.
* Diferenciar los planes GitHub Copilot Free, Pro, Pro+, Business y Enterprise.
* Configurar GitHub Copilot.
* Solucionar problemas de GitHub Copilot.

## Requisitos previos

* Conocimientos de GitHub.
* Conocimientos básicos de GitHub Copilot.

## GitHub Copilot como programador de pares de IA

GitHub Copilot proporciona un programador de pares basado en IA que funciona con los principales lenguajes de programación.

Inicialmente se centró en mantener a los desarrolladores en el flujo mediante el autocompletado de comentarios y código, pero sus capacidades se ampliaron para cubrir diferentes etapas del desarrollo.

## Características de GitHub Copilot

### Copilot Chat

Experiencia de chat integrada en los editores compatibles. Permite:

* Formular preguntas sobre el código.
* Obtener explicaciones sobre lógica o errores.
* Generar pruebas y documentación.
* Explorar cómo implementar nuevas funcionalidades.

El chat utiliza el contexto del código y del proyecto para relacionar sus respuestas con el trabajo actual.

### Resúmenes de solicitudes de incorporación de cambios

Al abrir una solicitud de incorporación de cambios, Copilot puede generar automáticamente una descripción resumida de los cambios, facilitando a los revisores la comprensión de la intención y reduciendo el trabajo de documentación.

### Asistencia de revisión de código

Copilot puede ayudar durante las revisiones de código mediante:

* Sugerencias sobre posibles problemas.
* Descripción de cambios.
* Identificación de casos perimetrales.
* Propuestas de mejoras.

Esto permite acelerar los ciclos de revisión y reducir el trabajo manual.

### Copilot para la CLI

La interfaz de línea de comandos permite:

* Solicitar sugerencias de comandos y fragmentos de código.
* Generar scripts de shell.
* Comprender resultados y errores.
* Generar y mejorar proyectos desde la CLI.

### Copilot Spaces

Copilot Spaces proporciona un entorno contextual para colaborar con la IA sobre un proyecto. Permite:

* Explorar la estructura del proyecto.
* Formular preguntas de planificación de alto nivel.
* Refinar requisitos.
* Iterar sobre diseños.

Copilot mantiene el contexto del repositorio y del flujo de trabajo.

### Agente en la nube de Copilot

El agente en la nube funciona como un asistente de IA autónomo capaz de realizar tareas de codificación en varios pasos a partir de instrucciones.

Puede utilizarse para:

* Generar varios archivos relacionados.
* Implementar conjuntos de funcionalidades.
* Crear andamiaje a partir de una especificación.

## Planes de suscripción

Los límites de disponibilidad, pruebas y uso pueden cambiar con el tiempo.

### GitHub Copilot Free

Plan gratuito para desarrolladores individuales.

Características principales:

* Finalizaciones de código en editores compatibles.
* Uso mensual limitado de finalizaciones y solicitudes de chat.
* Acceso a modelos avanzados de IA.

### GitHub Copilot Pro

Plan para desarrolladores individuales que necesitan funcionalidades superiores al plan gratuito.

Características principales:

* Límites de uso superiores al plan gratuito.
* Acceso prioritario a modelos de IA recientes.
* Sugerencias y explicaciones avanzadas de código.
* Integración con VS Code, Visual Studio, JetBrains y Neovim.
* Generación automatizada de pruebas y explicación de código.

### GitHub Copilot Pro+

Incluye las características de Copilot Pro y agrega:

* Capacidad adicional de solicitudes premium.
* Acceso prioritario a la infraestructura.
* Uso adicional de modelos premium.

Está orientado a personas con mayores necesidades de uso.

### GitHub Copilot Business

Plan orientado a organizaciones que necesitan administrar el acceso a Copilot y contar con características adicionales de seguridad y cumplimiento.

Características principales:

* Administración centralizada y controles de directivas.
* Filtrado de vulnerabilidades de seguridad.
* Referencia y filtrado de código público.
* Indemnización por IP.
* Seguridad y privacidad de nivel empresarial.
* Chat en IDE y dispositivos móviles.

### GitHub Copilot Enterprise

Plan orientado a grandes organizaciones que requieren mayor integración, personalización y funcionalidades avanzadas.

Incluye las características de Business y agrega:

* Sugerencias de código personalizadas basadas en código interno o privado.
* Integración con GitHub Enterprise Cloud.
* Generación de documentación y búsqueda mediante IA en el código base.
* Mejoras para solicitudes de incorporación de cambios mediante etiquetas y resúmenes con IA.
* Personalización y ajuste de modelos de Copilot para toda la organización.
* Integración profunda con GitHub para exploración del código base y chat.

GitHub Copilot Enterprise puede indexar el código base de una organización para obtener una comprensión más profunda y generar sugerencias más adaptadas. También permite personalizar GitHub Copilot para trabajar con modelos privados y ofrece integración con GitHub mediante una interfaz de chat y botones de acción en toda la plataforma.

## Interacción con Copilot

GitHub Copilot ofrece diferentes formas de interacción dentro del entorno de desarrollo. El contexto del código, su estructura y los comentarios ayudan a obtener asistencia más precisa y relevante.

### Sugerencias en línea

Las sugerencias insertadas son la forma más inmediata de asistencia. Mientras se escribe, Copilot analiza el código y el contexto para ofrecer finalizaciones en tiempo real.

Las sugerencias aparecen como texto atenuado delante del cursor.

* **Aceptar:** `Tab` o `→`.
* **Rechazar:** continuar escribiendo o `Esc`.

Son especialmente útiles para tareas repetitivas y generación rápida de código reutilizable.

### Paleta de comandos

Permite acceder rápidamente a funciones de Copilot.

En Visual Studio Code:

1. Abrir con `Ctrl+Shift+P` en Windows/Linux o `Cmd+Shift+P` en Mac.
2. Escribir **Copilot**.
3. Seleccionar acciones como **Explica esto** o **Genera pruebas unitarias**.

### Chat de Copilot

Permite interactuar con Copilot mediante lenguaje natural desde el IDE.

Puede utilizarse para:

* Formular preguntas.
* Solicitar fragmentos de código.
* Explorar conceptos.
* Obtener ayuda con sintaxis desconocida.

### Chat insertado

Permite mantener una conversación contextual directamente sobre una sección específica del código, sin cambiar de contexto.

1. Colocar el cursor donde se necesita ayuda.
2. Abrir el chat con `Ctrl+I` en Windows/Linux o `Cmd+I` en Mac.
3. Formular una pregunta o solicitar un cambio.

También permite utilizar comandos de barra diagonal:

* `/explain` — explica el código seleccionado.
* `/suggest` — ofrece sugerencias de código según el contexto.
* `/tests` — genera pruebas unitarias.
* `/comment` — convierte comentarios en fragmentos de código.

### Comentarios al código

Copilot puede convertir descripciones escritas mediante lenguaje natural en código.

El desarrollador describe en un comentario la funcionalidad que necesita y Copilot genera código basado en esa descripción.

Este enfoque resulta útil para crear rápidamente implementaciones sencillas.

### Sugerencias múltiples

Para código más complejo, Copilot puede ofrecer diferentes alternativas.

* Seleccionar el icono de bombilla cuando aparece una sugerencia.
* Usar `Alt+]` en Windows/Linux o `Option+]` en Mac para recorrer alternativas.

Esto permite comparar diferentes enfoques y seleccionar el más adecuado.

### Explicaciones

La función **Explica esto** permite comprender código existente.

1. Seleccionar un bloque de código.
2. Hacer clic derecho y seleccionar **Copilot: Explica esto**.
3. Revisar la explicación generada.

Es especialmente útil para aprendizaje y revisión de código desarrollado por otras personas.

### Generación automatizada de pruebas

Copilot puede generar pruebas unitarias para funciones o clases.

1. Seleccionar una función o clase.
2. Abrir la paleta de comandos.
3. Seleccionar **Copilot: Genera pruebas unitarias**.
4. Revisar los casos de prueba sugeridos.

La generación automatizada ayuda a mantener la integridad del código y detectar errores durante las primeras etapas del desarrollo.

### Importancia del contexto

Copilot aprende del contexto disponible. Mantener el código bien estructurado y comentado ayuda a obtener asistencia más precisa y relevante.

La interacción continua con Copilot permite que comprenda mejor el estilo y las preferencias de codificación.

## Instalación, configuración y solución de problemas

### Registro en GitHub Copilot

Para utilizar GitHub Copilot se necesita una cuenta de GitHub con acceso a Copilot.

Para registrarse:

1. Seleccionar la foto de perfil de GitHub.
2. Ir a **Configuración**.
3. Acceder a Copilot dentro de **Código, planeamiento y automatización**.

Después del registro, se instala la extensión correspondiente al entorno utilizado.

GitHub Copilot admite:

* GitHub.com, sin necesidad de extensión.
* Visual Studio Code.
* Visual Studio.
* IDE de JetBrains.
* Neovim.

### Configuración de GitHub Copilot en VS Code

Para instalar la extensión:

1. Acceder en Visual Studio Marketplace a la página de la extensión de GitHub Copilot.
2. Seleccionar **Instalar**.
3. Abrir VS Code cuando se solicite.
4. En la pestaña **Extensión: GitHub Copilot**, seleccionar **Instalar**.
5. Si es necesario, iniciar sesión en GitHub desde VS Code.

Una vez instalado, Copilot puede autocompletar código y permite habilitar, deshabilitar y configurar opciones avanzadas.

### Habilitar o deshabilitar Copilot

En VS Code:

1. Seleccionar el icono de estado de Copilot en el panel inferior.
2. Elegir **Habilitar** o **Deshabilitar**.

Al deshabilitarlo se puede elegir entre:

* **Deshabilitar finalizaciones** globalmente.
* **Deshabilitar finalizaciones para LANGUAGE**, únicamente para el idioma del archivo actual.

### Activar o desactivar sugerencias en línea

En VS Code:

1. Ir a **Archivo > Preferencias > Configuración**.
2. Seleccionar **Extensiones > GitHub Copilot**.
3. En **Editor: Activar las finalizaciones automáticas**, habilitar o deshabilitar las sugerencias en línea.

También se pueden configurar las sugerencias y los idiomas en los que GitHub Copilot estará habilitado o deshabilitado.

### Solución de problemas

Los archivos de registro de VS Code permiten diagnosticar problemas, especialmente problemas de conexión.

Desde la paleta de comandos se puede acceder a:

* **Desarrollador: Abrir el archivo de registro**.
* **Desarrollador: Abrir la carpeta Registros de extensiones**.

Si los errores no aparecen en los registros habituales, se pueden consultar los registros de Electron mediante:

**Ayuda > Alternar Herramientas de desarrollo**.

Las restricciones de red, firewalls y proxies pueden provocar problemas de conexión con GitHub Copilot.

Para recopilar información de diagnóstico:

1. Abrir la paleta de comandos.

   * Mac: `Shift+Command+P`.
   * Windows/Linux: `Ctrl+Shift+P`.
2. Escribir **Diagnósticos**.
3. Seleccionar **GitHub Copilot: Recopilar diagnósticos**.

Esto permite abrir un nuevo editor con información relevante para inspeccionar o compartir con el equipo de soporte técnico.
