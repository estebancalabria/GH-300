# GitHub Copilot — Características avanzadas

## Introducción

GitHub Copilot es un asistente de codificación con IA que proporciona sugerencias de autocompletado mientras se programa, a partir del código escrito o mediante lenguaje natural.

Copilot analiza el archivo actual y los archivos relacionados, utilizando el contexto del código y los comentarios para sugerir nuevas líneas o funciones completas.

GitHub Codespaces es un entorno de desarrollo hospedado en la nube que puede ejecutarse con Visual Studio Code. Permite personalizar el entorno para proyectos de GitHub, incluyendo dependencias, bibliotecas, extensiones y configuraciones de Visual Studio Code.

## Escenario: trabajar con un proyecto existente

GitHub Copilot puede aumentar la productividad tanto en proyectos nuevos como existentes mediante funciones avanzadas de IA aplicadas a tareas como:

* Escritura de código.
* Documentación.
* Pruebas.
* Incorporación de nuevos puntos de conexión de API HTTP.
* Comprensión de un código base existente.

El módulo utiliza ejemplos prácticos para modificar un repositorio mediante distintas técnicas de GitHub Copilot.

## Objetivos de aprendizaje

Al finalizar el módulo, se podrá:

* Trabajar con un repositorio de GitHub preconfigurado en Codespaces con la extensión GitHub Copilot.
* Utilizar características interactivas de GitHub Copilot para generar sugerencias útiles en un proyecto existente.
* Aplicar características avanzadas de GitHub Copilot para comprender un proyecto, escribir documentación y crear pruebas unitarias.
* Utilizar avisos interactivos y otras funciones avanzadas para mejorar un proyecto de software.

## Requisitos previos

* Conocimientos básicos de Python y editores de texto.
* Comprensión básica de Git y GitHub Fundamentals.
* Conocimiento de comandos básicos de `git`, como `git add` y `git push`.
* Cuenta de GitHub con una suscripción activa a GitHub Copilot, ya sea personal o administrada por una organización o empresa.
* Para aprendizaje, Copilot Free con límites de uso es suficiente.

## Características avanzadas de GitHub Copilot

Al trabajar con código es necesario consultar documentación del proyecto, bibliotecas y frameworks, además de comprender el código base. Tareas como corregir errores y escribir pruebas pueden requerir mucho tiempo.

GitHub Copilot ofrece características avanzadas para facilitar estas tareas.

### Texto fantasma

Cuando GitHub Copilot está habilitado, proporciona sugerencias denominadas **texto fantasma**.

* Se puede ignorar la sugerencia.
* Se puede aceptar presionando **Tabulador**.
* No es necesario escribir una indicación para obtener sugerencias, ya que Copilot utiliza de forma predeterminada los archivos abiertos como contexto.
* También se puede proporcionar una solicitud mediante comentarios, la ventana de chat o el chat en línea.

### Chat con GitHub Copilot

GitHub Copilot permite mantener una conversación interactiva mediante la característica de chat.

En Visual Studio Code, el icono de chat de la barra lateral izquierda abre una interfaz dedicada donde se pueden realizar preguntas sobre:

* El código en el que se está trabajando.
* Otras cuestiones relacionadas con el software.

### Chat en línea

El chat en línea permite interactuar con GitHub Copilot directamente desde el código, sin cambiar de contexto.

Accesos:

* **Windows:** `Ctrl+i`
* **Mac:** `Command+i`

Las sugerencias e interacciones aparecen cerca del código, evitando tener que cambiar a otro panel.

### Comandos de barra diagonal

En el panel de chat y en el chat en línea se pueden utilizar comandos de barra diagonal para indicar una intención específica y resolver tareas comunes de desarrollo.

Al escribir `/` aparece un menú con los comandos disponibles.

Ejemplos:

* `/tests`: ayuda a escribir pruebas.
* `/docs`: ayuda a escribir documentación.

Los comandos específicos permiten obtener mejores respuestas sin necesidad de escribir mensajes más extensos.

### Agentes

Visual Studio Code dispone de una característica denominada **agentes**, que permite interactuar con GitHub Copilot utilizando un contexto específico.

Por ejemplo:

* `@terminal`: permite comunicarse con GitHub Copilot para interactuar con el terminal.

## Ejercicio: configuración de GitHub Copilot para trabajar con Visual Studio Code

En este ejercicio se crea un repositorio mediante una plantilla de GitHub para una API web desarrollada con Python.

### Configuración del entorno

Se utiliza un entorno de Codespaces preconfigurado con la extensión GitHub Copilot.

1. Abrir el Codespace con el entorno preconfigurado.
2. En **Crear codespace**, revisar las opciones y seleccionar **Crear nuevo codespace**.
3. Esperar a que se inicie Codespace; el proceso puede tardar unos minutos.
4. Los demás ejercicios del proyecto se realizan dentro de este contenedor de desarrollo.

Todas las cuentas de GitHub pueden utilizar Codespaces hasta **60 horas gratuitas por mes con dos instancias principales**.

### GitHub Copilot Free

GitHub Copilot ofrece un nivel gratuito con:

* **2000 autocompletados de código por mes**.
* **50 mensajes de chat por mes**.

Para comenzar a utilizarlo, se debe abrir Visual Studio Code, seleccionar el icono de GitHub Copilot y elegir **Iniciar sesión para usar GitHub Copilot de forma gratuita**.

Los educadores, estudiantes y algunos mantenedores de código abierto pueden recibir Copilot Pro de forma gratuita.

### API web de Python

Una vez iniciado Codespaces:

* Se carga una sección de terminal en la parte inferior.
* Codespaces instala las extensiones necesarias en el contenedor.
* Después de instalar los paquetes, Codespaces ejecuta `uvicorn` para iniciar la aplicación web.
* Cuando la aplicación inicia correctamente, la pestaña **Puertos** del terminal muestra que el servidor se ejecuta en el **puerto 8000** dentro de Codespace.

### Registro en GitHub Copilot

Si todavía no se ha realizado, es necesario registrarse mediante una prueba gratuita o una suscripción para la cuenta de GitHub Copilot.

Los educadores, estudiantes y mantenedores de código abierto pueden registrarse gratuitamente en Copilot.

## Técnicas aplicadas de GitHub Copilot

GitHub Copilot puede ayudar tanto al comenzar a escribir código como al trabajar con proyectos existentes y tareas más complejas, incluyendo corrección de código, implementación de características, documentación, pruebas y comandos del terminal.

### Mensajes implícitos

Además de escribir mensajes específicos, se pueden utilizar características que aprovechan implícitamente el contexto disponible para obtener respuestas.

Por ejemplo, ante código Python con un error, se puede seleccionar el código, abrir el chat en línea mediante `Ctrl+i` en Windows o `Cmd+i` en Mac y utilizar `/fix` para solicitar una corrección.

Los comandos de barra diagonal pueden utilizarse tanto en el chat en línea como en la interfaz de chat.

Principales comandos:

* `/fix`: corrige problemas en el código.
* `/doc`: agrega comentarios al código seleccionado.
* `/explain`: explica el código.
* `/generate`: genera código para responder a una solicitud.
* `/help`: proporciona ayuda sobre el uso del chat de Copilot.
* `/optimize`: analiza y mejora el tiempo de ejecución del código seleccionado.
* `/tests`: crea pruebas unitarias para el código seleccionado.

La combinación de comandos de barra diagonal y chat en línea permite elegir la forma de interacción más adecuada según el código y la tarea.

### Contexto selectivo

GitHub Copilot puede proporcionar sugerencias según el contexto en el que se está trabajando, incluyendo:

* Todo el área de trabajo.
* La salida del terminal.
* Los archivos abiertos en el editor.

Esto permite obtener sugerencias específicas para el proyecto sin necesidad de abrir numerosos archivos.

Por ejemplo, se puede solicitar a Copilot que genere un `Dockerfile` para empaquetar un proyecto:

```text
I need to create a Dockerfile for this project, can you generate one that will help me package it?
```

También se puede especificar un requisito adicional:

```text
Help me create a Dockerfile to package this project but make sure you are using a Virtual Environment for Python.
```

Copilot proporciona sugerencias basadas en el contexto del proyecto y explica los pasos necesarios.

El agente `@terminal` permite obtener ayuda con errores o comandos utilizando como contexto la salida del terminal. Por ejemplo:

```text
@terminal ¿Cómo se corrige el mensaje de error que veo?
```

Si el resultado no es el esperado, se puede replantear la consulta, hacerla más específica o comenzar a escribir código para que Copilot lo autocomplete.

**Contexto predeterminado:** GitHub Copilot utiliza los archivos abiertos en el editor de texto como contexto adicional.

## Ejercicio: actualización de una API web con GitHub Copilot

En este ejercicio se modifica un repositorio de Python mediante técnicas avanzadas de GitHub Copilot para agregar un punto de conexión de API. El repositorio contiene una aplicación web de Python que hospeda una API de Tiempo de Viajes.

### ¿Qué es una API?

Una API actúa como intermediario que permite que diferentes aplicaciones se comuniquen entre sí. Puede proporcionar datos o funcionalidades que otras aplicaciones pueden utilizar.

### Extensión de la API web

La API existente no expone el país o región necesario para enumerar ciudades. Se debe implementar una nueva ruta que:

* Permita solicitudes HTTP GET.
* Devuelva una respuesta JSON.
* Proporcione información de niveles históricos altos y bajos.
* Utilice un país o región, ciudad y mes determinados.

Para el ejercicio se utiliza el Codespace con el entorno preconfigurado.

### Paso 1: agregar una nueva ruta

Abrir `main.py` y utilizar el chat en línea con:

* **Windows:** `Ctrl+i`
* **Mac:** `Command+i`

Indicación:

```text
Create a new route that exposes the cities of a country/region.
```

El resultado esperado es una ruta similar a:

```python
# Create a new route that exposes the cities of a country:
@app.get('/countries/{country}')
def cities(country: str):
    return list(data[country].keys())
```

Se debe probar la nueva ruta y perfeccionar el mensaje hasta obtener el resultado deseado.

### Paso 2: crear una prueba

Una vez creada la ruta, se utiliza Copilot Chat para crear una prueba que utilice **España** como país o región.

Indicación:

```text
/tests help me to create a new test for this route that uses Spain as the country/region.
```

Después se debe probar la prueba creada. Si el resultado no es correcto, se pueden proporcionar detalles adicionales a Copilot.

Ejemplo:

```text
This test is not quite right, it is not including cities that doesn't exist. Only Seville is part of the API.
```

### Paso 3: utilizar un agente para escribir documentación

Se utiliza el modo agente de GitHub Copilot Chat para documentar el proyecto y explicar cómo ejecutarlo.

Abrir `README.md` y utilizar:

```text
I want to document how to run this project so that other developers can get started quickly by reading the README.md file.
```

Copilot ayuda a actualizar `README.md` con la información necesaria para ejecutar el proyecto.

### Resultado del ejercicio

En el ejercicio se utiliza GitHub Copilot para:

1. Generar una nueva ruta de API.
2. Crear una prueba para comprobar su exactitud.
3. Agregar documentación mediante un agente para ayudar a los desarrolladores a comprender cómo ejecutar el proyecto.

Al finalizar, se continúa con una prueba breve de conocimientos, un resumen de lo aprendido y el distintivo por completar el módulo.
