# GitHub Copilot Agent Mode

## Introducción

GitHub Copilot Agent Mode permite desarrollar aplicaciones mediante un enfoque autónomo dentro de un **GitHub Codespace** y el **IDE VS Code**. Permite crear aplicaciones, interpretar instrucciones mediante prompts, utilizar archivos de documentación para guiar su comportamiento e iterar sobre el código para detectar y corregir errores, refactorizarlo y desarrollar nuevas funcionalidades.

El objetivo es reducir las tareas repetitivas y permitir que el desarrollador se concentre más en la innovación y en la resolución de problemas de mayor nivel.

## Objetivos de aprendizaje

Al finalizar el módulo se podrá:

* Desarrollar con VS Code IDE dentro de un GitHub Codespace.
* Utilizar prompts con GitHub Copilot Agent Mode para crear aplicaciones.
* Utilizar archivos de documentación para proporcionar instrucciones a Agent Mode.
* Comprender cómo Agent Mode itera sobre un código base para:

  * Corregir errores.
  * Refactorizar código.
  * Desarrollar nuevas funcionalidades.

## Prerrequisitos

* Tener una cuenta de GitHub.
* Tener conocimientos fundamentales sobre GitHub Copilot.

## ¿Qué es GitHub Copilot Agent Mode?

GitHub Copilot Agent Mode representa una evolución de la asistencia de IA para el desarrollo de software. A diferencia de los asistentes tradicionales basados principalmente en sugerencias de autocompletado, Agent Mode funciona como un programador autónomo que:

* Comprende el espacio de trabajo.
* Analiza las tareas dinámicamente.
* Itera sobre sus propios resultados.
* Crea aplicaciones desde cero.
* Refactoriza código en múltiples archivos.
* Escribe y ejecuta pruebas.
* Migra código heredado a frameworks modernos.
* Genera documentación.
* Integra nuevas bibliotecas.
* Responde preguntas complejas sobre un código base.

Esto permite delegar tareas repetitivas o que requieren mucho tiempo, manteniendo al desarrollador enfocado en problemas de mayor nivel.

## Cómo funciona Agent Mode

Agent Mode puede analizar un código base completo para identificar archivos y dependencias relevantes antes de realizar modificaciones. En lugar de limitarse al contexto de un único archivo, evalúa la estructura general del proyecto para realizar cambios coherentes.

Ante una tarea, Agent Mode:

1. Determina los archivos y dependencias relevantes.
2. Propone y ejecuta cambios de código alineados con la estructura del proyecto.
3. Ejecuta comandos de terminal cuando es necesario, como:

   * Compilar código.
   * Instalar dependencias.
   * Ejecutar pruebas.
4. Supervisa sus resultados.
5. Refina sus soluciones mediante múltiples iteraciones.
6. Corrige problemas y mejora la precisión.

Este proceso permite que Copilot actúe como un colaborador de IA que mejora continuamente sus resultados mientras el desarrollador mantiene el control.

## Formas de interactuar con GitHub Copilot

GitHub Copilot ofrece diferentes niveles de asistencia:

* **Inline Suggestions:** funcionan como herramientas de autocompletado, proporcionando sugerencias de código en tiempo real.
* **Copilot Chat:** permite realizar preguntas relacionadas con el desarrollo desde un panel de chat, utilizando el contexto de los archivos y dependencias del proyecto.
* **Copilot Edits:** permite realizar modificaciones estructuradas en múltiples archivos para alcanzar objetivos específicos.
* **Agent Mode:** automatiza tareas de desarrollo de forma dinámica, refinando e iterando sobre sus resultados para resolver flujos de trabajo complejos.

## Beneficios de Agent Mode

Agent Mode permite aumentar la productividad manteniendo el control sobre el proyecto. Automatiza tareas como:

* Ediciones repetitivas.
* Gestión de dependencias.
* Testing.
* Corrección de errores.
* Refactorización.

Al iterar sobre sus propios resultados, puede detectar errores y mejorar las soluciones antes de la revisión manual.

---

# Capacidades de Agent Mode

## Operación autónoma

Agent Mode puede analizar solicitudes de desarrollo, identificar archivos relevantes, determinar comandos de terminal necesarios e implementar soluciones completas sin requerir instrucciones paso a paso.

### Ejemplo: crear un endpoint REST

Ante la tarea de crear un nuevo endpoint REST, Agent Mode puede:

* Crear las rutas API (`routes/api.js`).
* Actualizar la aplicación (`app.js`).
* Instalar dependencias necesarias (`npm install express`).
* Generar casos de prueba (`tests/api.test.js`).

Aunque funciona de forma autónoma, cada cambio propuesto puede ser revisado por el desarrollador.

## Tareas complejas de múltiples pasos

Agent Mode puede dividir tareas complejas en acciones estructuradas y secuenciales.

### Ejemplo: integrar una base de datos

Ante la tarea de integrar una nueva base de datos, puede:

1. Actualizar dependencias (`npm install mongoose`).
2. Generar la lógica de conexión (`database.js`).
3. Modificar la configuración de entorno (`.env`).
4. Crear los modelos de datos (`models/userModel.js`).
5. Escribir pruebas automatizadas (`tests/userModel.test.js`).

## Flujos de orquestación de múltiples pasos

Agent Mode puede coordinar procesos complejos mediante un flujo de **borrador → revisión → aceptación**.

### Ejemplo: agregar autenticación de usuarios

**1. Fase de borrador**

Agent Mode analiza los requisitos y genera:

* Middleware de autenticación (`middleware/auth.js`).
* Rutas de login (`routes/auth.js`).
* Utilidades para hash de contraseñas (`utils/password.js`).
* Formulario de login básico (`views/login.html`).

**2. Fase de revisión**

Agent Mode evalúa su propio trabajo e identifica:

* Posibles vulnerabilidades de seguridad en el manejo de contraseñas.
* Mejoras en el manejo de errores.
* Validaciones adicionales para casos límite.
* Pruebas unitarias para funciones críticas.

**3. Fase de aceptación**

El desarrollador revisa una implementación refinada y preparada para PR, que incluye:

* Funcionalidad completa.
* Prácticas de seguridad.
* Manejo de errores y validaciones.
* Código alineado con las convenciones del proyecto.
* Documentación y pruebas.

Cada handoff de Agent Mode consume aproximadamente **1 PRU**. Una secuencia de dos pasos de borrador y revisión suele consumir **2–3 PRUs**.

## Construcción automatizada de la base de un proyecto

Agent Mode puede automatizar tareas repetitivas de configuración.

### Ejemplo: crear un nuevo microservicio

Puede generar automáticamente:

* Estructura del proyecto (`src/`, `tests/`, `config/`).
* Configuración de paquetes (`package.json`, `Dockerfile`, `.gitignore`).
* Configuración del framework de testing (`jest.config.js` y archivos de prueba).
* Configuración del pipeline CI/CD (`.github/workflows/test.yml`).
* Plantillas de configuración de entorno (`.env.example`, `config/default.js`).
* Configuración básica de monitoreo y logging (`utils/logger.js` y endpoints de health check).

El desarrollador se concentra en:

* Lógica de negocio.
* Modelos de dominio.
* Personalización de la base generada.
* Integraciones específicas.
* Flujos de trabajo personalizados.

## Capacidades avanzadas de razonamiento

Para escenarios complejos, Agent Mode puede utilizar razonamiento premium para realizar análisis más profundos, incluyendo:

* Análisis de decisiones arquitectónicas y sus alternativas.
* Evaluación del impacto de cambios entre múltiples sistemas.
* Estrategias de optimización de rendimiento.
* Análisis y corrección de vulnerabilidades de seguridad.

El razonamiento premium utiliza modelos más avanzados, proporciona mayor contexto y análisis más profundo, pero puede duplicar el consumo de PRUs. Una solicitud puede utilizar aproximadamente **4+ PRUs**, frente a unas **2 PRUs** con el modelo estándar.

## Uso de herramientas y conocimiento del contexto

Agent Mode utiliza información del proyecto para completar las tareas, incluyendo:

* Archivos.
* Dependencias.
* Estructura del proyecto.
* Acciones realizadas previamente.

### Ejemplo: despliegue de una aplicación React

Agent Mode puede:

* Reconocer el tipo de proyecto mediante `package.json`.
* Ejecutar scripts de compilación adecuados (`npm run build`).
* Preparar scripts de despliegue alineados con el flujo de trabajo existente.

Proporcionar un contexto claro y completo permite obtener resultados más precisos.

## Mejora iterativa y autocorrección

Una de las principales capacidades de Agent Mode es resolver problemas mediante iteraciones.

### Ejemplo: pruebas unitarias con errores

Si las pruebas generadas inicialmente fallan debido a un error de sintaxis, Agent Mode puede:

1. Detectar la causa del fallo.
2. Aplicar una corrección.
3. Ejecutar nuevamente las pruebas.
4. Continuar iterando hasta obtener resultados satisfactorios.

Este proceso reduce el esfuerzo manual de debugging y mejora la confiabilidad del código.

## Control y supervisión del usuario

A pesar de su autonomía, el desarrollador mantiene el control sobre las acciones de Agent Mode.

Puede:

* Revisar los cambios propuestos.
* Revisar los cambios resumidos en un pull request.
* Solicitar modificaciones.
* Ajustar las soluciones.
* Deshacer cambios.

Esto permite combinar automatización con revisión y criterio humano.

## Limitaciones y consideraciones prácticas

Agent Mode puede presentar dificultades cuando:

* Existe lógica de dominio especializada.
* Hay reglas de negocio complejas o poco claras.
* Falta contexto crítico del proyecto.
* La lógica de negocio personalizada está mal documentada.

Estas situaciones pueden producir soluciones menos precisas o incompletas y aumentar la necesidad de revisión e intervención manual.

Por ello, comprender sus limitaciones y proporcionar contexto claro permite aprovechar mejor sus capacidades.

## Conclusión

GitHub Copilot Agent Mode combina:

* Operación autónoma.
* Razonamiento y orquestación de tareas.
* Iteración continua.
* Corrección de errores.
* Refactorización.
* Desarrollo de nuevas funcionalidades.
* Uso del contexto del proyecto.
* Supervisión y control del desarrollador.

Su objetivo es mejorar la productividad, mantener la calidad del código y acelerar el desarrollo mediante la automatización de tareas de desarrollo complejas y repetitivas, manteniendo al desarrollador en control del resultado final.
