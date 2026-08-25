# Laboratorio: Generación de Código con GitHub Copilot en Visual Studio Code

## Objetivo

En este laboratorio aprenderás a utilizar las principales experiencias de generación de código de GitHub Copilot dentro de Visual Studio Code.

Durante las actividades exploraremos las siguientes formas de generación de código:

1. Generación mediante comentarios (Natural Language to Code)
2. Autocompletado inteligente (Ghost Text)
3. Generación y transformación mediante Inline Chat
4. Generación conversacional mediante Copilot Chat

El objetivo es comprender las capacidades fundamentales de GitHub Copilot antes de incorporar funcionalidades avanzadas.

---

# Requisitos

## Software

- Visual Studio Code
- Extensión GitHub Copilot
- Extensión GitHub Copilot Chat
- Python 3.x

## Verificación inicial

1. Abrir Visual Studio Code.
2. Confirmar que GitHub Copilot está conectado.
3. Crear una carpeta llamada:

```text
CopilotLab
```

4. Crear el archivo:

```text
library_system.py
```

---

# Parte 1 - Generación mediante Comentarios

## Objetivo

Comprender cómo GitHub Copilot transforma instrucciones escritas en lenguaje natural en código funcional.

---

## Ejercicio 1: Filtrar libros disponibles

Abrir el archivo:

```python
library_system.py
```

Escribir únicamente:

```python
# Create a function that receives a list of books and returns only the books available for loan
```

Detenerse unos segundos.

### Actividad

Observar la sugerencia generada por GitHub Copilot.

Aceptar la sugerencia utilizando:

```text
TAB
```

### Resultado esperado

Se genera una función que recibe una colección de libros y devuelve únicamente aquellos que están disponibles para préstamo.

---

## Ejercicio 2: Buscar libros por autor

Agregar:

```python
# Create a function that receives a list of books and an author name and returns all books written by that author
```

Aceptar la sugerencia.

### Resultado esperado

Se genera una función capaz de localizar libros de un autor determinado dentro de una colección.

---

## Ejercicio 3: Calcular multas

Agregar:

```python
# Create a function that calculates the late return penalty for a library member charging two dollars per day overdue
```

Aceptar la sugerencia.

### Resultado esperado

Se genera una función que calcula el importe a pagar por retraso en la devolución de un libro.

---

# Parte 2 - Autocompletado Inteligente (Ghost Text)

## Objetivo

Comprobar cómo GitHub Copilot utiliza el contexto existente para completar código.

---

## Ejercicio 1: Completar una función

Agregar:

```python
books = [
    {
        "title": "Python Fundamentals",
        "author": "John Smith",
        "available": True
    },
    {
        "title": "GitHub Copilot Guide",
        "author": "Sarah Taylor",
        "available": False
    }
]

def count_available_books(books):
```

No escribir nada más.

Esperar la sugerencia.

Aceptar con:

```text
TAB
```

### Resultado esperado

Copilot utiliza la estructura del listado de libros para completar automáticamente la implementación de la función.

---

## Ejercicio 2: Completar datos repetitivos

Escribir:

```python
members = [
    {
        "id": 1,
        "name": "Alice",
        "active": True
    },
```

Detenerse.

### Actividad

Observar cómo Copilot intenta completar el resto de la estructura.

Aceptar algunas sugerencias.

### Resultado esperado

Copilot genera registros similares siguiendo el patrón ya existente.

---

## Ejercicio 3: Completar bloques condicionales

Escribir:

```python
def can_borrow_book(member, book):
    if not member["active"]:
```

Esperar la sugerencia.

Aceptar.

### Resultado esperado

Copilot completa la lógica necesaria para determinar si un socio puede solicitar un libro.

---

# Parte 3 - Inline Chat

## Objetivo

Modificar y mejorar código existente mediante instrucciones dirigidas.

---

## Ejercicio 1: Simplificar código

Agregar:

```python
def count_available_books(books):
    total = 0

    for book in books:
        if book["available"]:
            total += 1

    return total
```

Seleccionar toda la función.

Presionar:

```text
Ctrl + I
```

Ingresar:

```text
Rewrite this function using a more concise Python approach.
```

Aceptar la propuesta.

### Resultado esperado

Copilot propone una implementación más compacta y legible.

---

## Ejercicio 2: Incorporar Type Hints

Seleccionar nuevamente la función.

Abrir Inline Chat.

Ingresar:

```text
Add type hints to this function.
```

Aceptar la propuesta.

### Resultado esperado

La función incorpora anotaciones de tipos en parámetros y valor de retorno.

---

## Ejercicio 3: Agregar documentación

Seleccionar la función.

Abrir Inline Chat.

Ingresar:

```text
Add a detailed docstring explaining parameters and return value.
```

Aceptar la propuesta.

### Resultado esperado

La función incorpora documentación descriptiva siguiendo prácticas habituales de Python.

---

## Ejercicio 4: Manejo de errores

Seleccionar la función.

Abrir Inline Chat.

Ingresar:

```text
Add input validation and error handling.
```

Aceptar la propuesta.

### Resultado esperado

La función incorpora validaciones y manejo de situaciones inesperadas.

---

# Parte 4 - Generación mediante Copilot Chat

## Objetivo

Generar código completo desde una conversación.

---

## Ejercicio 1: Crear una clase

Abrir Copilot Chat.

Ingresar:

```text
Create a Python class named Book with title, author, category and available properties.
```

Copiar el resultado al archivo.

### Resultado esperado

Se genera una clase que representa un libro dentro del sistema.

---

## Ejercicio 2: Evolución de la clase

En la misma conversación escribir:

```text
Add a method that determines whether the book can be borrowed.
```

Copiar las modificaciones.

### Resultado esperado

La clase incorpora lógica relacionada con préstamos.

---

## Ejercicio 3: Agregar comportamiento

Escribir:

```text
Add methods to borrow and return a book.
```

Aplicar los cambios.

### Resultado esperado

La clase gestiona el ciclo completo de préstamo y devolución.

---

## Ejercicio 4: Crear otra clase

Escribir:

```text
Create a Member class with member_id, full_name and active properties.
```

Copiar el resultado.

### Resultado esperado

Se genera una clase para representar socios de la biblioteca.

---

## Ejercicio 5: Relacionar clases

Escribir:

```text
Create a class called Library that manages books and members.
```

Copiar el resultado.

### Resultado esperado

Se genera una clase principal encargada de administrar la colección y los socios.

---

# Parte 5 - Conversación Contextual

## Objetivo

Comprender cómo Copilot conserva el contexto de la conversación.

---

## Actividad 1

Continuar en la misma conversación.

Ingresar:

```text
Add a method to search books by author.
```

Revisar la respuesta.

---

## Actividad 2

Ingresar:

```text
Add a method that returns all available books.
```

---

## Actividad 3

Ingresar:

```text
Generate three sample books and three sample members.
```

---

## Actividad 4

Ingresar:

```text
Create a menu driven console application using the classes already created.
```

### Resultado esperado

Copilot genera una aplicación de consola reutilizando las clases y funcionalidades creadas previamente durante la conversación.

---

# Conclusiones Esperadas

Al finalizar este laboratorio deberías ser capaz de:

- Utilizar comentarios para generar código.
- Aprovechar el autocompletado inteligente de Copilot.
- Modificar código existente mediante Inline Chat.
- Crear aplicaciones completas mediante Copilot Chat.
- Comprender cuándo utilizar cada experiencia de generación de código.
- Diferenciar claramente las capacidades fundamentales de GitHub Copilot dentro de Visual Studio Code.
