# Laboratorio: Uso de Slash Commands con GitHub Copilot en Visual Studio Code

## Objetivo

En este laboratorio aprenderás a utilizar los principales Slash Commands de GitHub Copilot para acelerar tareas habituales de desarrollo dentro de Visual Studio Code.

Durante las actividades exploraremos los siguientes comandos:

1. `/explain`
2. `/fix`
3. `/tests`
4. `/doc`
5. `/optimize`
6. `/generate`
7. `/help`

Al finalizar el laboratorio serás capaz de utilizar comandos de barra diagonal para analizar, documentar, mejorar y generar código de forma más eficiente.

---

# Requisitos

## Software

- Visual Studio Code
- Extensión GitHub Copilot
- Extensión GitHub Copilot Chat
- Python 3.x

## Verificación inicial

Crear un nuevo archivo:

```text
copilot_slash_commands.py
```

---

# Parte 1 - Comando /explain

## Objetivo

Comprender código existente utilizando lenguaje natural.

---

## Ejercicio 1

Copiar el siguiente código:

```python
def is_book_available(book):
    return book["available"] and book["copies"] > 0
```

Seleccionar el código.

Abrir Copilot Chat.

Ingresar:

```text
/explain
```

### Resultado esperado

Copilot describe:

- Qué hace la función.
- Qué parámetros recibe.
- Qué valor retorna.
- Qué condiciones evalúa.

---

## Ejercicio 2

Agregar:

```python
def calculate_late_fee(days_late):
    if days_late <= 0:
        return 0

    return days_late * 2
```

Seleccionar la función.

Ejecutar:

```text
/explain
```

### Resultado esperado

Copilot explica paso a paso la lógica implementada.

---

# Parte 2 - Comando /fix

## Objetivo

Detectar y corregir errores de programación.

---

## Ejercicio 1

Copiar:

```python
def get_book_title(book):
    return book["titel"]
```

Seleccionar la función.

Ejecutar:

```text
/fix
```

### Resultado esperado

Copilot detecta el error tipográfico:

```python
titel
```

y propone:

```python
title
```

---

## Ejercicio 2

Copiar:

```python
def average_rating(ratings):
    return sum(ratings) / len(ratings)
```

Seleccionar la función.

Ejecutar:

```text
/fix
```

### Resultado esperado

Copilot identifica posibles errores cuando la lista se encuentra vacía.

---

# Parte 3 - Comando /tests

## Objetivo

Generar pruebas unitarias automáticamente.

---

## Ejercicio 1

Copiar:

```python
def calculate_late_fee(days_late):
    if days_late <= 0:
        return 0

    return days_late * 2
```

Seleccionar la función.

Ejecutar:

```text
/tests
```

### Resultado esperado

Copilot genera pruebas para:

- Cero días de retraso.
- Valores positivos.
- Casos límite.

---

## Ejercicio 2

Agregar:

```python
def can_borrow_book(member):
    return member["active"]
```

Seleccionar el código.

Ejecutar:

```text
/tests
```

### Resultado esperado

Generación automática de casos de prueba utilizando unittest o pytest.

---

# Parte 4 - Comando /doc

## Objetivo

Generar documentación automáticamente.

---

## Ejercicio 1

Copiar:

```python
def search_books_by_author(books, author):
    return [
        book
        for book in books
        if book["author"] == author
    ]
```

Seleccionar la función.

Ejecutar:

```text
/doc
```

### Resultado esperado

Copilot agrega:

- Descripción
- Parámetros
- Valor de retorno

---

## Ejercicio 2

Seleccionar varias funciones del archivo.

Ejecutar:

```text
/doc
```

### Resultado esperado

Generación de documentación consistente para todas las funciones seleccionadas.

---

# Parte 5 - Comando /optimize

## Objetivo

Mejorar rendimiento y legibilidad del código.

---

## Ejercicio 1

Copiar:

```python
def count_available_books(books):
    total = 0

    for book in books:
        if book["available"] == True:
            total = total + 1

    return total
```

Seleccionar la función.

Ejecutar:

```text
/optimize
```

### Resultado esperado

Copilot propone una implementación más eficiente y legible.

---

## Ejercicio 2

Copiar:

```python
def search_book_by_title(books, title):
    result = []

    for book in books:
        if book["title"] == title:
            result.append(book)

    return result
```

Seleccionar la función.

Ejecutar:

```text
/optimize
```

### Resultado esperado

Copilot propone optimizaciones utilizando características modernas de Python.

---

# Parte 6 - Comando /generate

## Objetivo

Generar código completo a partir de una descripción.

---

## Ejercicio 1

Abrir Copilot Chat.

Ingresar:

```text
/generate create a class named Book with title, author, category and available properties
```

### Resultado esperado

Generación de una clase completa.

---

## Ejercicio 2

Ingresar:

```text
/generate create a function that loads books from a JSON file
```

### Resultado esperado

Generación de función para lectura de archivos JSON.

---

## Ejercicio 3

Ingresar:

```text
/generate create a console menu for a library management application
```

### Resultado esperado

Copilot genera una aplicación básica basada en menús.

---

# Parte 7 - Comando /help

## Objetivo

Descubrir funcionalidades disponibles.

---

## Ejercicio 1

Abrir Copilot Chat.

Ingresar:

```text
/help
```

### Resultado esperado

Visualización de ayuda relacionada con GitHub Copilot.

---

## Ejercicio 2

Explorar los comandos sugeridos por la ayuda.

Identificar:

- Explicación de código
- Corrección de errores
- Generación de pruebas
- Documentación
- Optimización

---

# Laboratorio Integrador

## Escenario

Se desea construir una aplicación para gestión de biblioteca.

### Paso 1

Generar una clase Book utilizando:

```text
/generate
```

### Paso 2

Documentarla utilizando:

```text
/doc
```

### Paso 3

Generar pruebas utilizando:

```text
/tests
```

### Paso 4

Modificar manualmente el código e introducir errores intencionales.

Utilizar:

```text
/fix
```

para corregirlos.

### Paso 5

Ejecutar:

```text
/optimize
```

para mejorar la implementación.

### Paso 6

Utilizar:

```text
/explain
```

para solicitar una explicación completa de la solución generada.

---

# Conclusiones Esperadas

Al finalizar este laboratorio deberías ser capaz de:

- Explicar código mediante `/explain`.
- Corregir errores mediante `/fix`.
- Generar pruebas unitarias mediante `/tests`.
- Crear documentación mediante `/doc`.
- Optimizar implementaciones mediante `/optimize`.
- Generar código desde lenguaje natural mediante `/generate`.
- Utilizar `/help` para descubrir funcionalidades disponibles.
- Seleccionar el Slash Command más adecuado según la tarea que necesites realizar.
