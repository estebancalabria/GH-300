# Resumen — Interacción y uso de GitHub Copilot

## GitHub Copilot

GitHub Copilot es un asistente avanzado de codificación con tecnología de inteligencia artificial que mejora la eficacia del desarrollador durante todo el flujo de trabajo de desarrollo.

Permite:

* Automatizar tareas rutinarias.
* Completar código de forma pertinente.
* Generar bloques completos de código.
* Acelerar los ciclos de desarrollo desde la codificación inicial hasta la finalización de las solicitudes de incorporación de cambios.
* Permitir que los desarrolladores se concentren en la resolución e innovación de problemas de mayor nivel.

## Métodos de interacción

GitHub Copilot ofrece diferentes formas de interacción adaptadas al entorno de desarrollo:

* **IDE:** finalización de código.
* **Chat conversacional:** resolución de problemas complejos.
* **GitHub.com:** características colaborativas y asistencia durante el desarrollo.
* **CLI:** asistencia mediante la línea de comandos.

Comprender estos modos permite comunicar objetivos de forma eficaz y proporcionar a Copilot la información necesaria para completar las tareas.

## Contenidos del módulo

* **Sugerencias automáticas:** uso de diferentes paneles de sugerencias y adaptación a distintos estilos de codificación para acelerar el desarrollo.
* **Contexto mediante comentarios:** uso de comentarios insertados, comentarios de bloque, docstrings y otros comentarios para mejorar la precisión y velocidad de generación de código.
* **Conversaciones en lenguaje natural:** generación de código complejo, depuración, explicación de código y simplificación de tareas de desarrollo en tiempo real.
* **Chat de GitHub Copilot:** mejora de la relevancia mediante referencias de ámbito, comandos de barra diagonal y agentes para completar tareas rutinarias.
* **GitHub.com:** exploración de repositorios, asistencia en solicitudes de incorporación de cambios, tareas de agentes y revisión colaborativa de código.
* **GitHub Copilot en la CLI:** explicación de comandos, sugerencias y ejecución de comandos para automatizar flujos de trabajo de terminal.
* **Configuración de la CLI:** configuración de alias y administración de opciones de privacidad, incluida la exclusión de la recopilación de datos de uso.

## Finalización del código con GitHub Copilot

Las características de finalización de código están integradas directamente en el IDE, como Visual Studio Code o JetBrains, donde se escribe y revisa el código.

### Lenguajes compatibles

GitHub Copilot ofrece una sólida compatibilidad con:

* Python
* JavaScript
* Java
* TypeScript
* Ruby
* Go
* C#
* C++

También puede ayudar con muchos otros lenguajes y marcos.

### Nivel gratuito

GitHub Copilot ofrece un nivel gratuito con:

* **2000 autocompletados de código al mes.**
* **50 mensajes de chat al mes.**

Los educadores, estudiantes y determinados mantenedores de código abierto pueden recibir Copilot Pro de forma gratuita.

### Sugerencias automáticas

Copilot genera sugerencias mientras se escribe código. Puede:

* Completar la línea actual.
* Sugerir bloques completos de código.
* Aceptar toda la sugerencia, parte de ella o ignorarla.

Las sugerencias en tiempo real y basadas en contexto reducen la necesidad de buscar sintaxis, resolver problemas de lógica o repetir patrones comunes.

### Panel de sugerencias múltiples

Cuando Copilot muestra una sugerencia, aparece como código atenuado. El panel de control permite explorar diferentes alternativas para el mismo problema y seleccionar la más adecuada.

Se pueden recorrer las sugerencias mediante:

* **macOS:** `⌥]` siguiente y `⌥[` anterior.
* **Windows/Linux:** `Alt+]` siguiente y `Alt+[` anterior.

Esto permite comparar rápidamente diferentes implementaciones sin interrumpir el flujo de desarrollo.

### Adaptación al estilo de codificación

Copilot puede adaptar sus sugerencias al contexto y estilo del proyecto:

* **Implementación de métodos:** puede sugerir implementaciones completas al comenzar a escribir un método.
* **Convenciones de nomenclatura:** adapta nombres de variables, funciones y clases.
* **Formato:** respeta preferencias de sangría, corchetes y formato.
* **Estilo de comentarios:** puede adaptarse a comentarios en línea, bloques o cadenas de documentación.
* **Patrones de diseño:** puede sugerir código alineado con los patrones utilizados consistentemente en el proyecto.

## Uso de comentarios para generar sugerencias

Copilot utiliza los comentarios del código para comprender la intención del desarrollador y generar sugerencias más relevantes.

Utiliza principalmente:

* **Procesamiento de lenguaje natural (NLP):** interpreta el significado e intención de los comentarios.
* **Análisis contextual:** relaciona los comentarios con el código circundante y el contexto del archivo o proyecto.

### Tipos de comentarios

Copilot puede utilizar:

* **Comentarios insertados:** explicaciones breves junto a líneas específicas.
* **Comentarios de bloque:** explicaciones más extensas sobre funciones o clases.
* **Docstrings:** cadenas de documentación formales, como las utilizadas en Python.
* **Comentarios de tareas pendientes:** notas sobre futuras implementaciones o mejoras.
* **Documentación de API:** comentarios sobre el uso y parámetros de funciones o métodos.

### Generación de código controlada por comentarios

Los comentarios pueden orientar diferentes aspectos de la generación de código:

* **Implementación de funciones:** una descripción en comentarios puede llevar a Copilot a sugerir una implementación completa.
* **Finalización de código:** los comentarios ayudan a comprender la intención y generar finalizaciones más precisas.
* **Nomenclatura de variables:** pueden orientar nombres descriptivos y adecuados al contexto.
* **Selección de algoritmos:** al describir un algoritmo o enfoque, Copilot puede generar código alineado con los pasos indicados.

## Chat de GitHub Copilot

GitHub Copilot Chat es un asistente interactivo de inteligencia artificial conversacional integrado en el entorno de desarrollo. Permite conversar en lenguaje natural sobre el código, formular preguntas y recibir respuestas y sugerencias en tiempo real.

Se accede desde el **icono de chat de la barra de navegación izquierda del IDE**.

### Principales usos

* **Generación de código:** ayuda a implementar algoritmos complejos, estructuras de datos, expresiones regulares, consultas SQL y código reutilizable.
* **Depuración:** analiza mensajes de error, identifica posibles errores lógicos y propone correcciones y explicaciones paso a paso.
* **Explicación de código:** simplifica código complejo, explica su propósito y funcionamiento y proporciona información sobre prácticas recomendadas y posibles optimizaciones.

También permite seleccionar código con errores, abrir el chat en línea y solicitar ayuda específica.

## Cómo mejorar las respuestas del Chat

### Referencias de ámbito

Permiten especificar el contexto que Copilot debe utilizar:

* **Referencias de archivos:** `#file:nombre_archivo` permite centrar la respuesta en un archivo determinado.
* **Referencias de entorno:** `@terminal` permite utilizar la salida del terminal como contexto para depuración y sugerencias.

### Comandos de barra diagonal

Permiten indicar rápidamente la intención de la consulta:

* **`/doc`:** agrega comentarios al código seleccionado.
* **`/explain`:** explica el código seleccionado.
* **`/fix`:** propone correcciones para problemas del código.
* **`/generate`:** genera código según los requisitos indicados.
* **`/optimize`:** analiza y propone mejoras de rendimiento o eficacia.
* **`/tests`:** genera pruebas unitarias para el código seleccionado.

## Selección de modelos y características premium

GitHub Copilot Chat puede ofrecer diferentes modelos de inteligencia artificial según el entorno.

### Modelos estándar — GPT-4o

* Respuestas rápidas y confiables para tareas habituales.
* Consumo de **1 PRU por solicitud**.
* Adecuados para programación rutinaria, explicaciones y depuración básica.
* Ejemplos: generación de funciones sencillas, ayuda de sintaxis y refactorización básica.

### Modelos Premium — o1-preview, o1-mini

* Ofrecen capacidades de razonamiento mejoradas.
* Consumen **2 PRU por solicitud**.
* Adecuados para análisis sofisticados, algoritmos complejos y decisiones arquitectónicas.
* Ejemplos: depuración avanzada de código multiproceso, diseño de algoritmos complejos y análisis de seguridad.

Para problemas que requieren razonamiento profundo, los modelos Premium pueden proporcionar análisis más exhaustivos y soluciones completas. Es necesario considerar el consumo de PRU al seleccionar el modelo.

## Agentes de Copilot

Los agentes de GitHub Copilot son herramientas personalizadas integradas con el chat para proporcionar funcionalidades específicas y controlar diferentes tareas.

### Acción `/new`

La acción inteligente `/new` permite generar un proyecto completamente nuevo desde cero según los requisitos indicados.

Ejemplo:

```text
/new generate a new HTML file with pages and JavaScript for advanced calculations
```

Después de seleccionar **Crear área de trabajo**, Copilot genera el proyecto y el código solicitado.

### Agentes específicos

* **`@terminal`:** ayuda con preguntas relacionadas con la línea de comandos, como encontrar el archivo más grande de un directorio o explicar el último comando ejecutado.
* **`@vscode`:** responde preguntas relacionadas con Visual Studio Code, como depuración o configuración del IDE.

## Comentarios sobre las respuestas

Los IDE con integración de Copilot Chat suelen incluir mecanismos para valorar las sugerencias.

En Visual Studio Code:

* **👍 Me gusta:** indica que la sugerencia fue útil.
* **👎 No me gusta:** indica que la sugerencia no fue útil.

## Revisión y colaboración de código

GitHub Copilot mejora la revisión de código mediante información y sugerencias que ayudan a mantener la calidad y detectar problemas:

* **Comentarios de revisión:** genera comentarios de revisión con sugerencias específicas.
* **Análisis de seguridad:** identifica posibles vulnerabilidades o incumplimientos de procedimientos recomendados.
* **Optimización del rendimiento:** sugiere mejoras de eficiencia y rendimiento.

Las características de revisión de código consumen **unidades de solicitud Premium (PRU)**. Cada solicitud normalmente utiliza **1-3 PRU**, según el ámbito y complejidad del análisis.

Ejemplo de solicitud:

> "Revise este cambio de código y proporcione comentarios sobre las consideraciones de seguridad y rendimiento."

## Explicación de errores en GitHub Actions

GitHub Copilot puede ayudar a explicar y resolver errores producidos en flujos de trabajo de GitHub Actions. Analiza las ejecuciones con errores y proporciona información sobre lo ocurrido y cómo corregirlo.

### Cómo explica Copilot los errores de Actions

* **Análisis de errores:** examina los archivos de registro e identifica la causa principal.
* **Sugerencias de solución:** proporciona recomendaciones específicas para resolver problemas del flujo de trabajo.
* **Procedimientos recomendados:** ofrece instrucciones para mejorar la confiabilidad y el rendimiento.
* **Reconocimiento del contexto:** comprende la relación entre los diferentes pasos del flujo de trabajo y sus dependencias.

## GitHub Copilot para la línea de comandos

La **CLI de GitHub Copilot** lleva Copilot directamente al terminal, permitiendo:

* Explicar comandos.
* Sugerir comandos de shell a partir de lenguaje natural.
* Trabajar de forma interactiva y segura con archivos y proyectos.

Utiliza la autenticación de GitHub y funciona independientemente de la CLI de GitHub, aunque utiliza las credenciales existentes.

### Instalación e inicio

En macOS y Linux puede instalarse mediante Homebrew:

```bash
brew install copilot-cli
```

También mediante el script oficial:

```bash
curl -fsSL https://gh.io/copilot-install | bash
```

Para iniciar el modo interactivo:

```bash
copilot
```

En el primer inicio, Copilot pregunta si se confía en los archivos de la carpeta actual, ya que puede leer, modificar o ejecutar archivos durante la sesión. Se puede utilizar `@` para seleccionar un archivo específico como contexto.

También existen solicitudes de un solo uso:

```bash
copilot -i "explain brew install git"
copilot -i "suggest find large files and delete them"
```

### Comandos de barra diagonal

Los comandos slash controlan explícitamente la sesión:

| Comando                      | Función                                                    |
| ---------------------------- | ---------------------------------------------------------- |
| `/help`                      | Mostrar comandos y opciones disponibles                    |
| `/explain <command>`         | Explicar un comando de shell                               |
| `/suggest <task>`            | Sugerir un comando de shell para una tarea                 |
| `/revise`                    | Revisar la última sugerencia según nuevas instrucciones    |
| `/feedback`                  | Enviar comentarios                                         |
| `/exit`                      | Salir del modo interactivo                                 |
| `/model <model>`             | Seleccionar el modelo de IA                                |
| `/theme [auto\|dark\|light]` | Cambiar el tema del terminal                               |
| `/skills`                    | Administrar aptitudes para funcionalidades mejoradas       |
| `/mcp`                       | Administrar la configuración del servidor MCP              |
| `/list-dirs`                 | Mostrar directorios permitidos para operaciones de archivo |
| `/reset-allowed-tools`       | Restablecer la lista de herramientas permitidas            |

Los comandos de barra diagonal no pueden reemplazarse por mensajes de lenguaje natural cuando se necesita controlar ajustes de sesión y configuración.

### Flujos de trabajo

**Explicar un comando:**

```text
> Explain what `git reset --hard HEAD` does
```

**Sugerir un comando:**

```text
> Find and delete all .log files in my home folder
```

Copilot genera una sugerencia y solicita confirmación para ejecutarla.

**Revisar una sugerencia:**

```text
> Include only files modified in the last 7 days
```

**Enviar comentarios:**

```text
> /feedback
```

**Salir:**

```text
> /exit
```

## Configuración de la CLI de Copilot

La configuración puede controlarse mediante:

* Comandos de barra diagonal.
* Configuración de la CLI en modo no interactivo.
* Avisos de permisos.
* Marcas de línea de comandos.
* Archivos de configuración local.

Las opciones permiten controlar qué puede acceder y hacer Copilot.

### Opciones de configuración

* **Directorios de confianza:** controlan dónde puede leer, editar y ejecutar archivos.
* **Permisos de herramientas:** permiten o restringen la ejecución de comandos de shell o modificación de archivos mediante opciones como `--allow-tool` o `--deny-tool`.
* **Permisos de rutas:** controlan los directorios accesibles.
* **Permisos de URL:** administran los dominios externos a los que puede conectarse Copilot.

## Entornos de ejecución aislados

GitHub Copilot CLI admite entornos de ejecución aislados para proteger el sistema mientras Copilot realiza tareas.

Existen dos modalidades:

* **Espacio aislado local.**
* **Espacio aislado en la nube.**

### Espacio aislado local

Permite ejecutar comandos dentro de un entorno restringido en la máquina local. Limita el acceso al sistema de archivos, conectividad de red y funcionalidades del sistema operativo.

Se habilita durante una sesión interactiva mediante:

```shell
/sandbox enable
```

Ventajas:

* **Seguridad mejorada:** restringe el acceso a recursos confidenciales.
* **Experimentación más segura:** reduce el riesgo al probar flujos de trabajo controlados por agentes.
* **Ejecución local:** utiliza recursos de la máquina sin infraestructura en la nube.
* **Mayor control:** proporciona medidas adicionales de seguridad para agentes autónomos.

### Espacio aislado en la nube

Permite ejecutar sesiones de Copilot CLI en entornos Linux completamente aislados alojados en GitHub.

Las sesiones se ejecutan en infraestructura de GitHub y están separadas del equipo local y de otras sesiones. El entorno se basa en entornos aislados de Azure Container Apps.

Para iniciar una sesión:

```shell
copilot --cloud
```

Copilot puede ejecutar comandos, modificar archivos, ejecutar pruebas y realizar tareas de desarrollo dentro del entorno de nube.

Ventajas:

* **Aislamiento seguro:** separa las cargas de trabajo de la máquina local.
* **Flexibilidad del dispositivo:** permite reanudar sesiones desde distintos dispositivos.
* **Descarga de recursos:** utiliza recursos en la nube en lugar de CPU y memoria locales.
* **Ejecución en paralelo:** permite ejecutar varias tareas controladas por agentes simultáneamente.

### Continuar sesiones entre dispositivos

Las sesiones de espacio aislado en la nube no están vinculadas a un equipo específico. Permiten:

* Iniciar una sesión en un dispositivo.
* Reanudarla desde otro dispositivo.
* Continuar el trabajo sin transferir manualmente archivos ni recrear entornos.

### Ciclo de vida de las sesiones en la nube

Las sesiones pueden encontrarse en tres estados:

| Estado        | Descripción                                                      |
| ------------- | ---------------------------------------------------------------- |
| **Activo**    | La sesión está en ejecución y disponible para interactuar.       |
| **Detenido**  | La sesión está pausada, pero conserva su estado.                 |
| **Eliminado** | La sesión y todo el estado guardado se eliminan permanentemente. |

Al detener una sesión, GitHub guarda una instantánea del entorno, incluidos archivos, variables de entorno y trabajo en curso. Al reanudarla, se restaura el estado guardado.

### Autenticación y acceso

Los entornos aislados en la nube utilizan el mismo modelo de autenticación que GitHub Copilot CLI. Si se dispone de autenticación y acceso a GitHub Copilot CLI, no se requiere configuración adicional del proveedor de nube.

No es necesario:

* Administrar claves de API.
* Configurar infraestructura en la nube.
* Aprovisionar máquinas virtuales.
* Mantener entornos de contenedor.

Los administradores de la organización o empresa deben habilitar la política de acceso al espacio aislado en la nube para que los miembros puedan utilizarlo.

### Espacio aislado local vs. nube

| Característica                | Espacio aislado local        | Espacio aislado en la nube         |
| ----------------------------- | ---------------------------- | ---------------------------------- |
| Ubicación de ejecución        | Máquina local                | Entorno alojado en GitHub          |
| Uso de recursos               | Recursos locales             | Recursos en la nube                |
| Nivel de aislamiento          | Entorno local restringido    | Entorno de nube totalmente aislado |
| Independencia del dispositivo | No                           | Sí                                 |
| Cargas de trabajo paralelas   | Limitadas por hardware local | Fácilmente escalables              |

### Cuándo utilizar el espacio aislado

Es especialmente útil para:

* Trabajar con repositorios desconocidos.
* Probar comandos generados por agentes.
* Ejecutar flujos de trabajo autónomos.
* Realizar operaciones potencialmente destructivas.
* Trabajar en varios dispositivos.
* Delegar tareas de desarrollo con uso intensivo de recursos.

## Uso eficaz de la CLI de Copilot

* Usar **modo interactivo (`copilot`)** para tareas exploratorias.
* Usar **modo one-shot (`copilot -i`)** para respuestas rápidas.
* Utilizar lenguaje natural para explicar, sugerir o revisar comandos.
* Revisar siempre los comandos antes de ejecutarlos.
* Combinar la CLI de Copilot con la CLI de GitHub (`gh`) para administrar problemas y repositorios.
* Utilizar **comandos de barra diagonal** para acciones estructuradas o comentarios.

# Aplicación GitHub Copilot

## Objetivos de aprendizaje

Al finalizar el módulo se debe poder:

* Describir qué es la aplicación GitHub Copilot y explicar sus ventajas.
* Diferenciar la aplicación GitHub Copilot de Copilot en VS Code, Copilot CLI y Copilot en GitHub.com.
* Identificar formas prácticas de utilizar la aplicación GitHub Copilot en flujos de trabajo de desarrollo reales.

## ¿Qué es la aplicación GitHub Copilot?

La **aplicación GitHub Copilot** es una experiencia de escritorio nativa para macOS, Windows y Linux que proporciona un único lugar para administrar el trabajo de desarrollo de extremo a extremo, desde seleccionar qué construir hasta enviar código.

Reúne:

* Desarrollo basado en agentes.
* Cambios de código y revisión de diferencias.
* Flujos de trabajo de pull request: comprobaciones, comentarios y combinación.

Todo dentro de una aplicación conectada directamente a GitHub.

### Espacio para el trabajo integral

La aplicación permite:

* Empezar a partir de un problema o tarea.
* Generar e iterar código.
* Revisar cambios.
* Administrar solicitudes de incorporación de cambios.
* Completar el proceso de combinación.

Los flujos de trabajo tradicionales implican terminales, IDE y navegadores, lo que genera cambio de contexto, configuración manual y mayor esfuerzo para seguir el progreso de las solicitudes de incorporación de cambios.

La aplicación GitHub Copilot aborda esto mediante:

* Consolidación de flujos de trabajo en una sola experiencia.
* Creación automática de áreas de trabajo aisladas para tareas paralelas.
* Conexión del código, contexto y ciclo de vida de las solicitudes de incorporación de cambios.

### Beneficios

* **Menor cambio de contexto.**
* **Ejecución de tareas paralelas con aislamiento.**
* **Administración integrada del ciclo de vida de las solicitudes de incorporación de cambios.**
* **Ruta más rápida desde la idea hasta el código combinado.**

## Funcionamiento de la aplicación GitHub Copilot

### Sesiones de agente o áreas de trabajo

Cada sesión:

* Está vinculada a una rama o solicitud de incorporación de cambios.
* Está aislada mediante árboles de trabajo de Git.
* Puede ejecutarse en paralelo con otras sesiones sin interferir.

Esto permite organizar múltiples flujos de trabajo simultáneamente.

### Basada en la CLI de Copilot

La aplicación utiliza el entorno de ejecución de Copilot CLI, por lo que:

* Conserva las configuraciones existentes de la CLI.
* Permite reutilizar herramientas, aptitudes y configuraciones.
* Mantiene la compatibilidad con flujos de trabajo avanzados.

## Aplicación GitHub Copilot frente a otras experiencias

| Superficie                    | Más adecuada para                                | Rol clave                                              |
| ----------------------------- | ------------------------------------------------ | ------------------------------------------------------ |
| **Aplicación GitHub Copilot** | Gestión integral de flujos de trabajo de agentes | Coordina problema → código → PR → combinación          |
| **Copilot en VS Code (IDE)**  | Edición y depuración                             | Desarrollo práctico cerca del código                   |
| **Copilot CLI**               | Flujos controlados desde el terminal             | Automatización, scripting y control del entorno        |
| **Copilot en GitHub.com**     | Colaboración y planificación                     | Incidencias, creación de PR y coordinación asincrónica |

## Modos de sesión

La aplicación permite elegir el nivel de autonomía del agente de IA según la complejidad de la tarea y la supervisión requerida.

| Modo            | Descripción                                                                                               | Más adecuado para                                     |
| --------------- | --------------------------------------------------------------------------------------------------------- | ----------------------------------------------------- |
| **Interactive** | El agente propone cambios y colabora paso a paso, esperando entrada y aprobación.                         | Desarrollo colaborativo y exploratorio                |
| **Plan**        | El agente crea primero un plan de implementación detallado que puede revisarse antes de ejecutar cambios. | Tareas complejas que requieren revisión y supervisión |
| **Autopilot**   | El agente implementa cambios, ejecuta pruebas, itera y completa la tarea con intervención mínima.         | Implementaciones bien definidas y tareas rutinarias   |

## Historial de sesiones con `/chronicle`

La aplicación admite funcionalidades del historial de sesiones de Copilot CLI, como `/chronicle`.

Permite recuperar información del trabajo realizado anteriormente en la aplicación y en sesiones de Copilot CLI.

### Casos de uso

* `/chronicle standup`: genera un resumen del trabajo reciente completado entre sesiones.
* `/chronicle`: revisa el historial de actividad y sesiones anteriores.

### Beneficios

* Seguimiento del trabajo entre sesiones.
* Creación rápida de actualizaciones de reuniones.
* Continuidad entre proyectos.
* Mayor visibilidad de la actividad de los agentes.

## Dictado de voz

La aplicación GitHub Copilot admite dictado de voz para introducir mensajes sin escribir.

La voz se convierte en texto mediante un modelo de transcripción local y se inserta en el cuadro de aviso para revisarlo, editarlo y enviarlo.

### Configuración

1. Abrir **Configuración** en la aplicación GitHub Copilot.
2. Seleccionar **Dictado de voz**.
3. Elegir un método abreviado de teclado.
4. Conceder permisos de micrófono al sistema operativo.
5. Descargar el modelo de transcripción local.

### Uso

1. Presionar el acceso directo para iniciar la grabación.
2. Pronunciar la indicación.
3. Presionar nuevamente el acceso directo para detenerla.
4. Revisar o editar el texto.
5. Enviar el aviso a Copilot.

### Ventajas

* Creación más rápida de prompts.
* Captura de ideas e instrucciones sin escribir.
* Transcripción mediante un modelo local instalado en el dispositivo.

## Casos de uso prácticos

### Ejecución de tareas en paralelo

Un desarrollador puede:

* Iniciar varias sesiones de agentes para diferentes funciones.
* Mantener cada tarea aislada en su propia área de trabajo.
* Cambiar entre sesiones sin perder contexto.

Es útil para trabajar en varios problemas simultáneamente.

### Gestión del ciclo de vida de la pull request

La aplicación proporciona:

* Revisión de cambios de código mediante diferencias.
* Monitorización de comprobaciones y estado de CI.
* Respuesta a comentarios.

Con **Agent Merge**, puede:

* Abordar comentarios de revisión.
* Corregir comprobaciones con errores.
* Avanzar la solicitud de incorporación de cambios hasta completarla.

Esto reduce el esfuerzo necesario para finalizar y enviar código.

### Reducción del cambio de herramientas

En lugar de alternar entre terminal, IDE y navegador, los desarrolladores pueden permanecer en una aplicación para:

* Generar código.
* Seguir el progreso.
* Gestionar solicitudes de incorporación de cambios.

### Flujos de trabajo repetibles

Los desarrolladores pueden:

* Convertir avisos en flujos de trabajo reutilizables.
* Programar tareas periódicas.
* Personalizar sesiones con herramientas y aptitudes.

Esto permite escalar el desarrollo basado en agentes entre equipos.

## Resumen de la aplicación GitHub Copilot

La aplicación GitHub Copilot propone una forma de trabajar con IA en el desarrollo de software centrada en la **orquestación**, no solo en la generación de código.

* Proporciona un **área de trabajo central** para administrar el desarrollo basado en agentes.
* Complementa, no reemplaza, los IDE, las herramientas CLI y GitHub.com.
* Permite **ejecutar flujos de trabajo paralelos y enviar código de forma más eficaz**.
* Ayuda a pasar del uso aislado de IA a un enfoque estructurado y escalable para el desarrollo basado en agentes.
