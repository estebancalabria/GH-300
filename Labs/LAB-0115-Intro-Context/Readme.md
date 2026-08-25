# Laboratorio: Uso de Contexto con Referencias @ en GitHub Copilot

## Objetivo

En este laboratorio aprenderás a utilizar las referencias con `@` para proporcionar contexto adicional a GitHub Copilot y obtener respuestas más precisas y relevantes.

A diferencia de otras experiencias de Copilot enfocadas en la generación de código, las referencias con `@` permiten indicar explícitamente qué información debe considerar el modelo al momento de responder.

Durante las actividades exploraremos:

1. Uso de `@workspace`
2. Uso de `@terminal`
3. Referencias a archivos específicos
4. Referencias a código dentro del proyecto
5. Comparación entre consultas con y sin contexto
6. Análisis de proyectos completos utilizando contexto enriquecido

---

# ¿Qué es una referencia con @?

Una referencia con `@` permite proporcionarle contexto adicional a Copilot.

Cuando utilizamos una referencia, Copilot puede considerar información adicional antes de generar una respuesta.

Por ejemplo:

```text
Explain the borrow process.
```

Copilot intentará responder utilizando únicamente la información visible o el contexto actual de la conversación.

En cambio:

```text
@workspace Explain the borrow process.
```

Copilot podrá analizar el proyecto completo antes de responder.

---

# ¿Qué es @workspace?

`@workspace` es una referencia que permite a Copilot utilizar información de todo el espacio de trabajo abierto en Visual Studio Code.

Cuando se utiliza `@workspace`, Copilot puede analizar:

- Archivos Python
- Archivos JavaScript
- Archivos de configuración
- Estructura del proyecto
- Clases
- Funciones
- Dependencias
- Relaciones entre archivos

Sin esta referencia, Copilot suele trabajar principalmente con:

- El archivo actual
- El código seleccionado
- El historial de conversación

Con `@workspace`, Copilot obtiene una visión mucho más amplia de la solución.

---

# Preparación del Proyecto

Crear una carpeta llamada:

```text
LibraryProject
```

Dentro de la carpeta crear los siguientes archivos:

```text
book.py
member.py
library.py
app.py
```

---

# Archivo book.py

```python
class Book:
    def __init__(self, title, author, category):
        self.title = title
        self.author = author
        self.category = category
        self.available = True

    def borrow(self):
        self.available = False

    def return_book(self):
        self.available = True
```

---

# Archivo member.py

```python
class Member:
    def __init__(self, member_id, full_name):
        self.member_id = member_id
        self.full_name = full_name
        self.active = True
```

---

# Archivo library.py

```python
from book import Book
from member import Member

class Library:

    def __init__(self):
        self.books = []
        self.members = []

    def add_book(self, book):
        self.books.append(book)

    def add_member(self, member):
        self.members.append(member)

    def get_available_books(self):
        return [
            book
            for book in self.books
            if book.available
        ]
```

---

# Archivo app.py

```python
from library import Library

library = Library()
```

---

# Parte 1 - Utilizando @workspace

## Objetivo

Comprender cómo Copilot utiliza todo el proyecto como contexto.

---

## Ejercicio 1

Abrir Copilot Chat.

Ingresar:

```text
@workspace Explain how this application works.
```

### Resultado esperado

Copilot analiza todos los archivos del proyecto y describe:

- Las clases existentes
- La finalidad de cada archivo
- La relación entre ellas

---

## Ejercicio 2

Ingresar:

```text
@workspace Which file manages the library inventory?
```

### Resultado esperado

Copilot identifica correctamente:

```text
library.py
```

como el componente principal para la gestión de libros.

---

## Ejercicio 3

Ingresar:

```text
@workspace Describe the relationship between Book and Library.
```

### Resultado esperado

Copilot explica cómo la clase Library utiliza objetos Book.

---

# Parte 2 - Comparando Resultados

## Objetivo

Observar la diferencia entre trabajar con contexto limitado y contexto ampliado.

---

## Ejercicio 1

Ingresar:

```text
How does the borrow process work?
```

Leer la respuesta.

---

## Ejercicio 2

Ingresar:

```text
@workspace How does the borrow process work?
```

### Analizar

Comparar ambas respuestas.

Identificar:

- Nivel de detalle
- Precisión
- Referencias al proyecto

---

## Ejercicio 3

Ingresar:

```text
What classes exist in this solution?
```

---

## Ejercicio 4

Ingresar:

```text
@workspace What classes exist in this solution?
```

### Resultado esperado

La segunda respuesta debería identificar correctamente las clases disponibles en el proyecto.

---

# Parte 3 - Uso de @terminal

## Objetivo

Utilizar información proveniente de la consola.

---

## Ejercicio 1

Modificar temporalmente el archivo app.py:

```python
library = Library(
```

Guardar.

Ejecutar:

```bash
python app.py
```

Se producirá un error.

---

## Ejercicio 2

Abrir Copilot Chat.

Ingresar:

```text
@terminal Explain the error shown in the terminal.
```

### Resultado esperado

Copilot analiza la salida mostrada y explica:

- El origen del error
- La causa probable
- La posible corrección

---

## Ejercicio 3

Ingresar:

```text
@terminal Suggest how to fix the problem.
```

### Resultado esperado

Copilot propone una corrección basada en la salida del terminal.

---

# Parte 4 - Referencias a Archivos

## Objetivo

Analizar archivos concretos dentro del proyecto.

---

## Ejercicio 1

Abrir Copilot Chat.

Seleccionar el archivo:

```text
book.py
```

como contexto desde la interfaz de Copilot.

Preguntar:

```text
Explain the responsibilities of this file.
```

### Resultado esperado

Copilot describe las funcionalidades de la clase Book.

---

## Ejercicio 2

Referenciar el archivo Library.

Preguntar:

```text
Suggest improvements for this implementation.
```

### Resultado esperado

Copilot identifica posibles mejoras relacionadas con validaciones, búsquedas y mantenimiento.

---

# Parte 5 - Exploración de Arquitectura

## Objetivo

Utilizar el contexto del proyecto para comprender el diseño de la aplicación.

---

## Ejercicio 1

Ingresar:

```text
@workspace Describe the architecture of this application.
```

### Resultado esperado

Copilot identifica:

- Componentes principales
- Responsabilidades
- Dependencias

---

## Ejercicio 2

Ingresar:

```text
@workspace Identify missing functionality in the library system.
```

### Resultado esperado

Copilot propone funcionalidades que todavía no han sido implementadas.

---

## Ejercicio 3

Ingresar:

```text
@workspace What features would be required to support book reservations?
```

### Resultado esperado

Copilot identifica cambios necesarios en varias partes del proyecto.

---

# Parte 6 - Análisis de Calidad

## Objetivo

Utilizar el contexto global para revisar la solución.

---

## Ejercicio 1

Ingresar:

```text
@workspace Identify potential bugs in this application.
```

### Resultado esperado

Copilot detecta posibles problemas relacionados con validaciones y lógica de negocio.

---

## Ejercicio 2

Ingresar:

```text
@workspace Suggest unit tests for this project.
```

### Resultado esperado

Copilot genera propuestas de pruebas para las distintas clases.

---

## Ejercicio 3

Ingresar:

```text
@workspace Suggest refactoring opportunities.
```

### Resultado esperado

Copilot propone mejoras sobre estructura, diseño y reutilización de código.

---

# Laboratorio Integrador

## Escenario

Suponga que acaba de incorporarse a un equipo de desarrollo y recibe esta aplicación sin documentación previa.

Utilice exclusivamente referencias de contexto para responder las siguientes preguntas:

```text
@workspace Explain the purpose of the application.
```

```text
@workspace Describe the responsibilities of each file.
```

```text
@workspace What features are missing?
```

```text
@workspace Identify technical debt.
```

```text
@workspace Suggest the next development phase.
```

---

# Conclusiones Esperadas

Al finalizar este laboratorio deberías ser capaz de:

- Comprender el propósito de las referencias con `@`.
- Utilizar `@workspace` para analizar proyectos completos.
- Utilizar `@terminal` para interpretar errores de ejecución.
- Aplicar contexto específico durante las conversaciones con Copilot.
- Obtener respuestas más precisas utilizando información relevante del proyecto.
- Diferenciar claramente una consulta con contexto de una consulta sin contexto.
