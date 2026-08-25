# Laboratorio: GitHub Copilot Instructions + Copilot Inline Chat (Ctrl+I)

## Objetivo

En este laboratorio aprenderás a personalizar el comportamiento de GitHub Copilot mediante instrucciones de repositorio y comprobarás cómo dichas instrucciones afectan a las respuestas generadas por Copilot Chat e Inline Chat.

Durante las actividades aprenderás a:

- Crear un proyecto desde cero.
- Probar GitHub Copilot sin instrucciones personalizadas.
- Crear un archivo `.github/copilot-instructions.md`.
- Activar el uso de archivos de instrucciones.
- Recargar las instrucciones del repositorio.
- Comparar resultados antes y después de aplicar instrucciones.
- Comprender los distintos niveles de personalización disponibles en GitHub Copilot.
- Crear instrucciones específicas para determinadas áreas de un proyecto.

## Referencia oficial

Documentación de GitHub:

[Agregar instrucciones personalizadas del repositorio para GitHub Copilot](https://docs.github.com/es/copilot/how-tos/copilot-on-github/customize-copilot/add-custom-instructions/add-repository-instructions)

---

# ¿Qué son las Copilot Instructions?

Las instrucciones de repositorio permiten proporcionar contexto adicional a GitHub Copilot para que comprenda mejor:

- Cómo está organizado el proyecto.
- Qué estándares debe respetar.
- Cómo generar código.
- Cómo documentar.
- Cómo escribir pruebas.
- Qué convenciones utilizan los equipos de desarrollo.

Las instrucciones se almacenan normalmente en:

```text
.github/copilot-instructions.md
```

Una vez configuradas, Copilot puede utilizarlas automáticamente al generar código, responder preguntas o revisar cambios.

---

# Parte 1 - Crear el Proyecto

## Paso 1

Crear una nueva carpeta:

```text
CopilotInstructionsLab
```

## Paso 2

Abrir la carpeta en Visual Studio Code.

## Paso 3

Verificar que están instaladas las siguientes extensiones:

- GitHub Copilot
- GitHub Copilot Chat

---

# Parte 2 - Comportamiento Inicial (Sin Instrucciones)

## Objetivo

Observar cómo responde Copilot antes de definir reglas para el proyecto.

### Paso 1

Crear el archivo:

```text
test.js
```

### Paso 2

Ubicar el cursor dentro del archivo vacío.

### Paso 3

Presionar:

```text
Ctrl + I
```

### Paso 4

Ingresar el siguiente prompt:

```text
Generá una función que ordene números
```

### Paso 5

Guardar el resultado.

Identificar esta versión como:

```text
ANTES
```

### Analizar

- ¿Cómo nombró la función?
- ¿Incluyó validaciones?
- ¿Agregó comentarios?
- ¿Modificó el array original?

---

# Parte 3 - Crear Instrucciones para Todo el Repositorio

## Objetivo

Definir reglas globales para todo el proyecto.

### Paso 1

Crear la carpeta:

```text
.github
```

### Paso 2

Crear el archivo:

```text
.github/copilot-instructions.md
```

### Paso 3

Agregar el siguiente contenido:

```markdown
# Instrucciones del repositorio

Copilot debe generar siempre funciones:

- Bien nombradas comenzando con el prefijo fn
- Con validaciones de entrada
- Sin modificar colecciones originales
- Con comentarios descriptivos encima de cada función
- Utilizando nombres de variables claros y descriptivos
- Evitando abreviaturas
```

### Paso 4

Guardar el archivo.

---

# Parte 4 - Verificar Configuración

## Paso 1

Abrir la configuración de VS Code.

## Paso 2

Buscar:

```text
Use Instruction Files
```

## Paso 3

Verificar que se encuentre habilitada la opción:

```text
GitHub > Copilot > Chat: Use Instruction Files
```

---

# Parte 5 - Recargar las Instrucciones

## Paso 1

Abrir Copilot Chat.

## Paso 2

Ingresar:

```text
reload repository instructions
```

### Resultado esperado

Copilot debería volver a cargar las instrucciones presentes en el repositorio.

---

# Parte 6 - Comparar Resultados

## Objetivo

Comprobar el efecto de las instrucciones.

### Paso 1

Crear el archivo:

```text
test2.js
```

### Paso 2

Ubicar el cursor en un espacio vacío.

### Paso 3

Presionar:

```text
Ctrl + I
```

### Paso 4

Utilizar exactamente el mismo prompt:

```text
Generá una función que ordene números
```

### Paso 5

Guardar el resultado.

Identificar esta versión como:

```text
DESPUÉS
```

### Verificar

Analizar si la nueva función:

- Utiliza prefijo `fn`
- Incluye validaciones
- Mantiene inmutabilidad
- Agrega comentarios descriptivos
- Respeta las instrucciones definidas

---

# Parte 7 - Instrucciones Arquitectónicas

## Objetivo

Guiar las decisiones de diseño de Copilot.

Modificar el archivo:

```text
.github/copilot-instructions.md
```

Agregar:

```markdown
# Arquitectura

- Utilizar Repository Pattern
- Utilizar Dependency Injection
- Aplicar principios SOLID
- Evitar dependencias directas entre capas
- Mantener la lógica de negocio separada del acceso a datos
```

---

## Actividad

Abrir Copilot Chat.

Solicitar:

```text
Generá una aplicación para gestión de productos.
```

### Analizar

Comprobar si la solución:

- Utiliza capas diferenciadas
- Separa responsabilidades
- Define servicios y repositorios
- Aplica patrones de arquitectura

---

# Parte 8 - Instrucciones de Testing

## Objetivo

Modificar la forma en que Copilot genera pruebas.

Agregar:

```markdown
# Testing

- Utilizar pytest
- Aplicar patrón AAA (Arrange Act Assert)
- Crear pruebas para casos válidos
- Crear pruebas para casos límite
- Crear pruebas de validación de errores
```

---

## Actividad

Solicitar:

```text
Generá pruebas unitarias para ProductService.
```

### Analizar

Verificar:

- Uso de pytest
- Presencia de Arrange, Act y Assert
- Cobertura de escenarios positivos y negativos

---

# Parte 9 - Instrucciones de Documentación

## Objetivo

Personalizar la documentación generada por Copilot.

Agregar:

```markdown
# Documentación

- Utilizar Google Style Docstrings
- Documentar todos los parámetros
- Documentar valores de retorno
- Agregar ejemplos cuando corresponda
```

---

## Actividad

Solicitar:

```text
Documentá la clase Product.
```

### Analizar

Observar cómo cambian las descripciones generadas.

---

# Parte 10 - Instrucciones Específicas por Ruta

## Objetivo

Aplicar reglas distintas según el área del proyecto.

### Paso 1

Crear la estructura:

```text
.github/
└── instructions/
```

### Paso 2

Crear el archivo:

```text
.github/instructions/tests.instructions.md
```

### Contenido

```yaml
---
applyTo: "**/tests/*.py"
---
```

```markdown
- Utilizar pytest exclusivamente
- Aplicar patrón AAA
- Incluir pruebas de borde
- Evitar duplicación de código
```

---

## Actividad

Crear:

```text
tests/test_library.py
```

Solicitar:

```text
Generá pruebas para LibraryService.
```

### Analizar

Determinar si Copilot aplica las reglas específicas para archivos de pruebas.

---

# Parte 11 - Instrucciones para APIs

## Objetivo

Aplicar reglas únicamente a endpoints y servicios REST.

Crear:

```text
.github/instructions/api.instructions.md
```

Contenido:

```yaml
---
applyTo: "**/api/*.py"
---
```

```markdown
- Utilizar FastAPI
- Utilizar modelos Pydantic
- Validar todas las entradas
- Incluir manejo de errores
- Utilizar respuestas tipadas
```

---

## Actividad

Solicitar:

```text
Generá un endpoint para registrar libros.
```

### Analizar

Verificar si las instrucciones específicas influyen sobre el código generado.

---

# Parte 12 - Verificar que Copilot Utiliza las Instrucciones

## Objetivo

Confirmar qué contexto utilizó Copilot.

### Paso 1

Realizar cualquier consulta mediante Copilot Chat.

### Paso 2

Expandir la sección:

```text
References
```

### Paso 3

Verificar si aparece:

```text
.github/copilot-instructions.md
```

### Paso 4

Si aparecen referencias adicionales:

```text
.github/instructions/*.instructions.md
```

analizar cuáles fueron utilizadas para generar la respuesta.

---

# Nuevos Tipos de Instrucciones (2025-2026)

GitHub Copilot incorpora distintos niveles de personalización.

## 1. Instrucciones para Todo el Repositorio

**Archivo:**

```text
.github/copilot-instructions.md
```

**Propósito:**

Aplicar reglas globales a todas las solicitudes realizadas dentro del repositorio.

### Casos de uso

- Convenciones de nombres.
- Estándares de codificación.
- Reglas de documentación.
- Estrategias de testing.
- Reglas arquitectónicas.

---

## 2. Instrucciones Específicas por Ruta

**Ubicación:**

```text
.github/instructions/
```

**Archivos:**

```text
*.instructions.md
```

**Propósito:**

Aplicar reglas únicamente a determinadas carpetas o tipos de archivo.

### Ejemplos

```text
frontend.instructions.md
```

```text
infra.instructions.md
```

```text
tests.instructions.md
```

### Casos de uso

- React en Frontend.
- Bicep para Infraestructura.
- pytest para Testing.
- Convenciones específicas según cada módulo.

---

## 3. Instrucciones para Agentes

GitHub también admite instrucciones dirigidas a agentes mediante archivos como:

```text
AGENTS.md
CLAUDE.md
GEMINI.md
OPENAI.md
```

Estas instrucciones permiten personalizar el comportamiento de agentes específicos utilizados dentro del ecosistema de GitHub Copilot.

---

# Laboratorio Integrador

## Escenario

Una empresa desea estandarizar el desarrollo de sus aplicaciones.

Se requiere que Copilot:

- Utilice Python 3.12.
- Use type hints.
- Utilice pytest.
- Genere documentación obligatoria.
- Respete principios SOLID.
- Utilice Repository Pattern.
- Genere APIs con FastAPI.
- Utilice validaciones en todas las entradas.

### Actividad

Configurar:

```text
.github/copilot-instructions.md
```

y

```text
.github/instructions/
```

para implementar dichas reglas.

Luego solicitar:

```text
Generá un sistema completo de gestión de biblioteca.
```

Analizar de qué manera las instrucciones influyen sobre:

- El diseño.
- El código generado.
- La documentación.
- Las pruebas unitarias.
- La arquitectura final.

---

# Conclusiones Esperadas

Al finalizar este laboratorio deberías ser capaz de:

- Crear instrucciones globales para GitHub Copilot.
- Crear instrucciones específicas para determinadas áreas del proyecto.
- Comprender cómo Copilot utiliza dichas instrucciones.
- Verificar cuándo una instrucción fue aplicada.
- Personalizar la generación de código según las necesidades de un equipo de desarrollo.
- Implementar estándares técnicos reutilizables para todo un repositorio.
