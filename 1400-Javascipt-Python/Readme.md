# GitHub Copilot con JavaScript y Python

## Introducción

* GitHub Copilot es un asistente de codificación con IA que proporciona sugerencias de autocompletado al escribir código o describirlo en lenguaje natural.
* Analiza el archivo y archivos relacionados para ofrecer sugerencias en el editor, utilizando OpenAI Codex para interpretar el contexto del código y comentarios.
* GitHub Codespaces es un entorno de desarrollo hospedado en la nube que puede ejecutarse con Visual Studio Code y permite personalizar proyectos de GitHub, incluyendo dependencias, bibliotecas, extensiones y configuraciones.
* El módulo muestra cómo usar GitHub Copilot para mejorar proyectos existentes y nuevos, especialmente en escritura de código, documentación y pruebas.

### Objetivos

Al finalizar el módulo se podrá:

* Configurar un repositorio de GitHub en Codespaces e instalar la extensión de GitHub Copilot.
* Crear avisos para generar sugerencias con GitHub Copilot.
* Utilizar GitHub Copilot para mejorar proyectos.
* Personalizar proyectos de JavaScript mediante mensajes en GitHub Codespaces.

### Requisitos previos

* Conocimientos básicos de JavaScript y editores de texto.
* Conocimientos básicos de Git y GitHub, incluyendo comandos como `git add` y `git push`.
* Cuenta de GitHub con una suscripción activa a GitHub Copilot, personal o administrada por una organización o empresa. Para aprender, Copilot Free con límites de uso es suficiente.

## ¿Qué es GitHub Copilot?

GitHub Copilot es un asistente de inteligencia artificial utilizado desde el IDE que puede generar código y otros contenidos a partir de solicitudes en lenguaje natural.

Las solicitudes pueden escribirse:

* Como comentarios dentro de archivos de código, por ejemplo `.py` o `.js`.
* En archivos Markdown, esperando unos segundos para que Copilot responda.
* Mediante GitHub Copilot Chat.

Copilot genera una sugerencia que puede aceptarse o rechazarse. Las sugerencias aparecen como texto gris y pueden aceptarse con `Tab`.

Copilot también puede ofrecer varias alternativas. Se pueden recorrer con `Ctrl+Enter` y seleccionar la más adecuada.

## Uso de GitHub Copilot con JavaScript y Python

GitHub Copilot puede ayudar tanto al comenzar a escribir código como al trabajar con proyectos existentes y tareas más complejas, por ejemplo:

* Actualizar código.
* Corregir errores.
* Agregar nuevas funcionalidades.
* Mejorar la funcionalidad y facilidad de uso.
* Escribir documentación.
* Crear pruebas.

GitHub Copilot Chat permite formular preguntas y recibir respuestas relacionadas con el código.

### Ingeniería de solicitudes

Una solicitud es un conjunto de instrucciones o indicaciones utilizadas para generar código. Puede ser un comentario o una entrada en GitHub Copilot Chat.

La calidad del resultado depende de cómo se construya la solicitud. Las indicaciones ambiguas pueden producir resultados que no coincidan con las necesidades.

Una indicación específica debe definir claramente el objetivo y el alcance de la tarea. Por ejemplo, en lugar de solicitar simplemente:

`Create an API endpoint`

es mejor indicar el framework, el método HTTP y el formato de los datos requeridos.

Ejemplos utilizados:

* JavaScript: crear un endpoint usando React que acepte un payload JSON mediante POST.
* Python: crear un endpoint usando FastAPI que acepte un payload JSON mediante POST.

También se puede proporcionar contexto y ejemplos mediante comentarios, código o GitHub Copilot Chat.

### Procedimientos recomendados

* Mantener las indicaciones simples inicialmente y agregar detalles progresivamente.
* Dividir tareas complejas en instrucciones más específicas.
* Recorrer las diferentes sugerencias con `Ctrl+Enter` o `Cmd+Enter` en Mac y elegir la más adecuada.
* Utilizar GitHub Copilot Chat para agregar contexto e interactuar con la respuesta.
* Si el resultado no es adecuado, reformular la solicitud o comenzar a escribir código para que Copilot lo complete automáticamente.

Ejemplo de evolución de una solicitud:

1. Crear un formulario HTML con un campo de texto y un botón.
2. Agregar un evento al botón para enviar una solicitud POST a `/generate` y mostrar la respuesta en un `div` con id `result`.

GitHub Copilot utiliza los archivos abiertos en el editor como contexto adicional. Si se necesitan sugerencias basadas en otros archivos, estos pueden abrirse o referenciarse mediante GitHub Copilot Chat.

## Ejercicio: actualización de una API web de Python con GitHub Copilot

El ejercicio consiste en modificar un repositorio de Python utilizando sugerencias de GitHub Copilot para crear un formulario HTML interactivo y un endpoint de API.

La aplicación web de Python sirve una API HTTP que genera un token pseudoaleatorio.

### ¿Qué es una API?

Una API actúa como intermediario para permitir que diferentes aplicaciones se comuniquen entre sí. Por ejemplo, una API meteorológica puede proporcionar datos históricos o funcionalidades de previsión que luego pueden utilizarse en un sitio web o aplicación.

### Extensión de la API web

La API existente tiene un endpoint para generar un token. El ejercicio agrega un nuevo endpoint que acepta texto y devuelve una lista de tokens.

El ejercicio se realiza utilizando un Codespace con el entorno preconfigurado.

### Paso 1: Agregar un modelo Pydantic

En `main.py`, se agrega un comentario para que GitHub Copilot genere automáticamente un modelo `Pydantic` similar a:

```python
class Text(BaseModel):
    text: str
```

### Paso 2: Generar un nuevo endpoint

Se solicita a GitHub Copilot un endpoint FastAPI que:

* Acepte una solicitud POST.
* Reciba un cuerpo JSON con un único campo llamado `text`.
* Devuelva un checksum del texto.

### Paso 3: Agregar las importaciones necesarias

El código generado puede requerir los módulos `base64` y `os`. GitHub Copilot Chat puede ayudar a identificar y agregar las importaciones faltantes.

También pueden agregarse manualmente:

```python
import base64
import os
```

Finalmente, se comprueba el funcionamiento del nuevo endpoint desde `/docs`, verificando que aparezca allí.

El ejercicio muestra el uso de GitHub Copilot para generar código de forma interactiva y aplicarlo a un proyecto existente.
