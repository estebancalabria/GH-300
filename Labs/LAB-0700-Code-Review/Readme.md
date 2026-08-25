# Laboratorio: GitHub Copilot Code Review

## Objetivo

En este laboratorio aprenderás a utilizar GitHub Copilot para asistir en el proceso de **Code Review**, tanto localmente desde VS Code como dentro de un Pull Request de GitHub.

Al finalizar el laboratorio podrás:

- Utilizar GitHub Copilot para revisar cambios de código.
- Identificar posibles errores y vulnerabilidades.
- Obtener sugerencias de mejora y refactorización.
- Solicitar revisiones de Copilot en Pull Requests.
- Personalizar los criterios de revisión mediante instrucciones.
- Automatizar las revisiones mediante Repository Rulesets.
- Aplicar buenas prácticas para realizar Code Reviews asistidos por IA.

## Prerrequisitos

- Cuenta de GitHub con acceso a GitHub Copilot.
- Conocimientos básicos de Git y GitHub.
- Experiencia básica con Pull Requests.
- VS Code.
- Conocimientos básicos de desarrollo de software y buenas prácticas.

## Duración estimada

**60–90 minutos**

---

# Escenario

Mergington High School posee un sitio web para gestionar actividades extracurriculares.

Durante los últimos meses se incorporaron muchas funcionalidades y el sitio comenzó a ser utilizado por una gran cantidad de profesores y estudiantes.

Ahora varios profesores quieren colaborar en el desarrollo de nuevas funcionalidades. Para mantener la calidad del código, el equipo quiere utilizar **GitHub Copilot para asistir en los Code Reviews**.

Durante el laboratorio implementarás un flujo completo:

1. Crear el laboratorio a partir de GitHub Skills.
2. Ejecutar la aplicación en GitHub Codespaces.
3. Realizar una modificación en el proyecto.
4. Solicitar un Code Review local desde VS Code.
5. Crear un Pull Request.
6. Solicitar un Code Review de Copilot en GitHub.
7. Personalizar las instrucciones de revisión.
8. Solicitar una nueva revisión.
9. Automatizar las revisiones mediante Repository Rulesets.
10. Resolver el Pull Request.

---

# Parte 1: Crear el laboratorio

## Paso 1: Acceder al ejercicio

1. Abrir el navegador **Edge**.
2. Navegar a:

   `https://github.com/skills/copilot-code-review`

3. Iniciar sesión en GitHub si es necesario.
4. En el repositorio del ejercicio, seleccionar **Copy Exercise**.
5. Crear un nuevo repositorio.
6. Mantener las opciones predeterminadas.
7. Seleccionar **Create repository**.

> **Nota:** Se recomienda utilizar un repositorio público, ya que los repositorios privados pueden consumir minutos de GitHub Actions.

---

# Parte 2: Preparar el entorno

## Paso 2: Crear un Codespace

1. En el repositorio recién creado, seleccionar el botón verde **Code**.
2. Seleccionar la pestaña **Codespaces**.
3. Seleccionar **Create codespace on main**.
4. Esperar a que finalice la preparación del entorno.

El Codespace instalará automáticamente los requisitos y servicios necesarios.

> **Nota:** La preparación puede tardar entre 3 y 5 minutos.

## Paso 3: Verificar las extensiones

En VS Code, comprobar que estén instaladas y habilitadas:

- GitHub Copilot
- Python

## Paso 4: Ejecutar la aplicación

1. Abrir **Run and Debug** desde la barra lateral.
2. Seleccionar **Start Debugging**.
3. Abrir la pestaña **Ports**.
4. Localizar el puerto correspondiente a la aplicación.
5. Abrir la URL de la aplicación.
6. Verificar que el sitio web funciona correctamente.

> **Solución de problemas:** Si el área **Run and Debug** aparece vacía, abrir la Command Palette con `Ctrl + Shift + P` y ejecutar `Developer: Reload Window`.

---

# Parte 3: Code Review local con Copilot

## Objetivo

Realizar una modificación en el proyecto y utilizar GitHub Copilot para revisarla **antes de crear un Pull Request**.

---

## Paso 5: Crear una nueva rama

En VS Code:

1. Seleccionar el nombre de la rama actual en la esquina inferior izquierda.
2. Seleccionar **Create new branch…**
3. Crear la rama:

```text
add-announcement-banner
````

---

## Paso 6: Agregar un banner

Abrir:

```text
src/static/index.html
```

Después de la etiqueta `<body>`, agregar:

```html
<div class="announcement-banner">
  📢 Activity registration is open until the end of the month. Don't lose your spot!
</div>
```

---

## Paso 7: Agregar estilos

Abrir:

```text
src/static/styles.css
```

Agregar al final:

```css
.announcement-banner {
  background-color: #4caf50;
  color: white;
  text-align: center;
  padding: 15px;
  font-weight: bold;
}
```

Opcionalmente, actualizar la aplicación para comprobar visualmente el resultado.

---

## Paso 8: Solicitar un Code Review local

1. Abrir el panel **Source Control**.
2. Comprobar que existen cambios sin commit.
3. Ubicar la sección **Changes**.
4. Mostrar los iconos disponibles.
5. Seleccionar **Code Review**.
6. Esperar a que GitHub Copilot analice los cambios.

Copilot puede proporcionar comentarios relacionados con:

* Calidad del código.
* Estilo.
* Seguridad.
* Rendimiento.
* Posibles problemas.
* Mejoras.

### Niveles de revisión

VS Code permite revisar diferentes estados de los cambios:

* **Unstaged changes**
* **Staged changes**
* **Uncommitted changes**

---

## Paso 9: Analizar las recomendaciones

Abrir el panel **Comments** y revisar las recomendaciones generadas por Copilot.

Para cada sugerencia:

1. Leer el problema identificado.
2. Evaluar si la recomendación es válida.
3. Utilizar **Apply** para aplicar una sugerencia.
4. Utilizar **Discard** para descartarla.

> **Importante:** Copilot proporciona asistencia, pero el desarrollador debe evaluar las recomendaciones antes de aplicarlas.

---

## Paso 10: Crear el commit

Desde **Source Control**:

1. Seleccionar los cambios relacionados con el banner.
2. Hacer **Stage** de los cambios.
3. Escribir un mensaje de commit.
4. Seleccionar **Commit**.
5. Seleccionar **Publish Branch**.

La rama será publicada:

```text
add-announcement-banner
```

---

# Parte 4: Code Review en un Pull Request

## Objetivo

Solicitar a GitHub Copilot una revisión directamente sobre un Pull Request.

### Conceptos

GitHub Copilot puede analizar un Pull Request y proporcionar feedback sobre:

* Calidad.
* Seguridad.
* Rendimiento.
* Posibles problemas.
* Mejoras.
* Cambios recomendados.

El review de Copilot es un review de tipo **Comment**, por lo que no bloquea directamente el merge ni cuenta como una aprobación requerida.

> **Importante:** El Code Review de Copilot no reemplaza herramientas de seguridad, estándares de desarrollo ni la revisión humana.

---

## Paso 11: Crear el Pull Request

1. Ir a la pestaña **Pull requests**.
2. Seleccionar **Compare & pull request**.
3. Configurar:

```text
Compare: add-announcement-banner
Target: main
Title: Add announcement banner
```

4. Seleccionar **Create pull request**.

---

## Paso 12: Solicitar la revisión de Copilot

En el área de detalles del Pull Request:

1. Localizar **Reviewers**.
2. Seleccionar el icono de configuración.
3. Seleccionar **Copilot** como reviewer.
4. Crear el Pull Request si todavía no fue creado.
5. Esperar a que Copilot complete la revisión.

Observar los comentarios agregados por Copilot y la entrada correspondiente en la conversación del Pull Request.

---

# Parte 5: Personalizar el Code Review

## Objetivo

Definir reglas específicas para que Copilot adapte sus revisiones a los estándares del proyecto.

Las instrucciones personalizadas permiten proporcionar contexto sobre:

* Requisitos de seguridad.
* Convenciones de código.
* Calidad.
* Rendimiento.
* Estándares del equipo.
* Criterios específicos según el tipo de archivo.

---

# Actividad 1: Crear instrucciones generales

## Paso 13: Crear `copilot-instructions.md`

En VS Code, crear:

```text
.github/copilot-instructions.md
```

Agregar:

```markdown
## Security

- Validate input sanitization practices.
- Search for risks that might expose user data.
- Prefer loading configuration and content from the database instead of hard coded content. If absolutely necessary, load it from environment variables or a non-committed config file.

## Code Quality

- Use consistent naming conventions.
- Try to reduce code duplication.
- Prefer maintainability and readability over optimization.
- If a method is used a lot, try to optimize it for performance.
- Prefer explicit error handling over silent failures.
```

Guardar el archivo.

---

# Actividad 2: Crear instrucciones específicas

Las instrucciones específicas permiten definir criterios diferentes según el tipo de archivo.

> **Importante:** Los archivos específicos deben estar dentro de `.github/instructions/`.

---

## Paso 14: Instrucciones para Frontend

Crear:

```text
.github/instructions/frontend.instructions.md
```

Agregar:

```markdown
---
applyTo: "*.html,*.css,*.js"
---

## Frontend Guidelines

- Use accessibility attributes (alt text, aria labels) and color schemes.
- Use responsive design for compatibility with mobile devices.
- Validate HTML structure and semantic elements.
```

Guardar el archivo.

---

## Paso 15: Instrucciones para Backend

Crear:

```text
.github/instructions/backend.instructions.md
```

Agregar:

```markdown
---
applyTo: "backend/**/*,*.py"
---

## Backend Guidelines

- All API endpoints must be defined in the `routers` folder.
- Load example database content from the `database.py` file.
- Error handling is only logged on the server. Do not propagate to the frontend.
- Ensure all APIs are explained in the documentation.
- Verify changes in the backend are reflected in the frontend (`src/static/**`). If possible breaking changes are found, mention them to the developer.
```

Guardar el archivo.

---

# Parte 6: Volver a solicitar el Code Review

## Paso 16: Commit y sincronización

En VS Code:

1. Abrir **Source Control**.
2. Hacer Stage de los cambios.
3. Crear un commit.
4. Seleccionar **Sync Changes** para enviar los cambios a:

```text
add-announcement-banner
```

---

## Paso 17: Solicitar nuevamente la revisión

1. Volver al Pull Request en GitHub.
2. Localizar **Reviewers**.
3. Seleccionar **Re-request review** junto a Copilot.
4. Esperar a que Copilot realice una nueva revisión.
5. Comparar los comentarios con la revisión anterior.

### Pregunta de análisis

**¿Qué diferencias observas entre la primera revisión y la segunda?**

Explica cómo las instrucciones personalizadas modificaron los criterios utilizados por Copilot.

---

# Parte 7: Automatizar Code Reviews

## Objetivo

Evitar que los desarrolladores tengan que solicitar manualmente una revisión de Copilot en cada Pull Request.

Para esto utilizaremos **Repository Rulesets**.

Los Rulesets permiten establecer reglas para los Pull Requests y automatizar determinados controles sobre las ramas.

---

## Paso 18: Crear un Repository Ruleset

En GitHub:

1. Abrir la pestaña **Settings**.
2. En el menú izquierdo, expandir **Rules**.
3. Seleccionar **Rulesets**.
4. Seleccionar **New ruleset**.
5. Seleccionar **New branch ruleset**.

Configurar:

### Ruleset

```text
Ruleset Name: Require Copilot Reviews
Enforcement Status: Active
```

### Target branches

Agregar protección para la rama `main`.

Seleccionar:

* **Add target**
* **Include default branch**

Luego:

* **Add target**
* **Include by pattern**
* Escribir:

```text
main
```

* Seleccionar **Add inclusion pattern**.

---

## Paso 19: Configurar las reglas

En **Rules**, habilitar:

```text
☑ Require a pull request before merging
☑ Require conversation resolution before merging
☑ Automatically request Copilot code review
```

Seleccionar **Create**.

---

# Parte 8: Completar el Pull Request

## Paso 20: Revisar el Pull Request

Volver al Pull Request abierto.

Observar que el botón de merge puede aparecer deshabilitado debido a las nuevas reglas.

Revisar los comentarios de Copilot.

---

## Paso 21: Resolver las conversaciones

Resolver todas las conversaciones actuales y antiguas de Copilot.

> **Nota:** No es necesario implementar todas las sugerencias de Copilot para completar el laboratorio. Lo importante es analizar el feedback y resolver las conversaciones.

---

## Paso 22: Realizar el Merge

Cuando se cumplan las condiciones del Ruleset:

1. Seleccionar **Merge pull request**.
2. Seleccionar **Confirm merge**.

Si el botón de Merge permanece deshabilitado, comprobar si existen conversaciones sin resolver, incluyendo comentarios antiguos.

---

# Desafío final

Una vez completado el laboratorio, responde:

### 1. Code Review local

¿Qué ventajas tiene realizar un Code Review de Copilot en VS Code antes de crear un Pull Request?

### 2. Pull Request Review

¿Qué diferencias existen entre solicitar una revisión de Copilot en VS Code y solicitarla sobre un Pull Request?

### 3. Custom Instructions

¿Qué problema resuelven las instrucciones personalizadas del repositorio?

### 4. Path-specific Instructions

¿Por qué puede ser útil definir instrucciones diferentes para Frontend y Backend?

### 5. Repository Rulesets

¿Qué problema resuelve la automatización de Code Reviews mediante Rulesets?

### 6. Validación humana

¿Por qué un Code Review realizado por Copilot no debería considerarse un reemplazo completo de la revisión humana?

---

# Resultado esperado

Al finalizar el laboratorio habrás construido un flujo completo de **AI-assisted Code Review**:

```text
Developer
    │
    ▼
VS Code
    │
    ├── Cambios locales
    │
    ▼
GitHub Copilot Code Review
    │
    ▼
Correcciones / mejoras
    │
    ▼
Commit + Push
    │
    ▼
Pull Request
    │
    ▼
GitHub Copilot Review
    │
    ▼
Custom Instructions
    │
    ▼
Nueva revisión
    │
    ▼
Repository Ruleset
    │
    ▼
Review automático
    │
    ▼
Resolve conversations
    │
    ▼
Merge
```

## Competencias adquiridas

Al completar este laboratorio serás capaz de:

* Utilizar GitHub Copilot para Code Review local.
* Utilizar Copilot como reviewer de Pull Requests.
* Analizar problemas de calidad, seguridad y rendimiento.
* Evaluar y aplicar sugerencias generadas por IA.
* Crear instrucciones generales para Copilot.
* Crear instrucciones específicas por tipo de archivo.
* Personalizar los criterios de Code Review.
* Automatizar Code Reviews mediante Repository Rulesets.
* Integrar GitHub Copilot dentro de un flujo de desarrollo colaborativo.



