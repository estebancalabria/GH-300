# GitHub Copilot: productividad, personalización, SDLC, orquestación y medición de impacto

## Casos de uso con GitHub Copilot para la inteligencia artificial de los desarrolladores

### Introducción

GitHub Copilot es un asistente de codificación inteligente que ayuda a los desarrolladores a escribir código más rápido. Se integra con IDE populares y proporciona sugerencias de código contextuales adaptadas al estilo y las preferencias de codificación.

Su uso puede:

* Aumentar la productividad.
* Adaptarse a las preferencias individuales del desarrollador.
* Impactar distintas fases del ciclo de vida de desarrollo de software (SDLC).
* Ahorrar tiempo.
* Mejorar la calidad del código.
* Aumentar la satisfacción del desarrollador.

### Objetivos de aprendizaje

Al finalizar el módulo se podrá:

* Identificar cómo GitHub Copilot se integra en los flujos de trabajo de los desarrolladores y se adapta a sus preferencias de codificación.
* Explorar su impacto en las distintas fases del SDLC.
* Evaluar las limitaciones de la codificación asistida por IA y su impacto en la eficacia del desarrollo.

### Requisitos previos

* Conocimientos básicos de desarrollo de software.
* Familiaridad con al menos un lenguaje de programación.
* Cuenta de GitHub y conocimientos básicos de sus funcionalidades.
* Para acceder a GitHub Copilot se requiere una cuenta personal de GitHub o una cuenta administrada por una organización o empresa.
* Para aprendizaje, Copilot Free con límites de uso es suficiente.

### GitHub Copilot Free

GitHub Copilot ofrece un nivel gratuito con:

* **2000 autocompletados de código al mes.**
* **50 mensajes de chat al mes.**

Para comenzar desde Visual Studio Code:

1. Abrir Visual Studio Code.
2. Seleccionar el icono de GitHub Copilot.
3. Hacer clic en **"Iniciar sesión para usar GitHub Copilot de forma gratuita"**.
4. Iniciar sesión con la cuenta de GitHub en la ventana del navegador.

Los educadores, estudiantes y determinados mantenedores de código abierto pueden recibir Copilot Pro de forma gratuita.

### Impacto en el desarrollo

GitHub Copilot ayuda a los desarrolladores a:

* Codificar más rápido.
* Mantener el foco durante más tiempo.
* Afrontar desafíos más complejos con mayor confianza.

## Aumentar la productividad de los desarrolladores con IA

GitHub Copilot simplifica los flujos de trabajo de desarrollo, permitiendo centrarse en resolver problemas complejos en lugar de tareas de codificación rutinarias.

### Casos de uso para optimizar la productividad

#### Aprendizaje de nuevos lenguajes y marcos

GitHub Copilot facilita el aprendizaje mediante:

* **Sugerencias de código:** muestra ejemplos de funciones y bibliotecas desconocidas.
* **Compatibilidad con idiomas:** permite realizar transiciones entre distintos lenguajes.
* **Integración de documentación:** proporciona sugerencias relacionadas con API y parámetros de funciones, reduciendo la necesidad de consultar documentación externa.

También puede generar código y utilizar **"Explicar esto"** para explicar su funcionamiento.

#### Minimización del cambio de contexto

Ayuda a mantener el foco mediante:

* **Asistencia en el editor:** sugerencias directamente en el IDE.
* **Referencias rápidas:** sugerencias de llamadas y parámetros de API o bibliotecas.
* **Finalización de código:** automatización de patrones repetitivos sin interrumpir el flujo de trabajo.

Esto reduce la necesidad de abandonar el editor para consultar recursos externos.

#### Escritura mejorada de documentación

GitHub Copilot puede:

* Generar comentarios insertados sobre código complejo.
* Crear descripciones de funciones, parámetros y valores devueltos.
* Ayudar a generar archivos README según el código del proyecto.
* Mantener un estilo de documentación coherente.

#### Automatización de tareas rutinarias

Puede automatizar:

* **Código reutilizable:** por ejemplo, estructuras de API REST o clases.
* **Datos de ejemplo:** generación de datos realistas para pruebas.
* **Pruebas unitarias:** sugerencia y generación de pruebas.
* **Traducción y refactorización:** mejora de patrones, implementaciones y conversión entre lenguajes.

### Automatización avanzada con plantillas

GitHub Copilot puede automatizar tareas más complejas:

* Generación de modelos de base de datos, migraciones y configuraciones ORM.
* Creación de puntos de conexión REST con validación, manejo de errores y documentación.
* Generación de configuraciones para desarrollo, ensayo y producción.
* Configuración de infraestructuras completas de pruebas.

Por ejemplo, puede generar la estructura de un microservicio, incluyendo Docker, canalizaciones CI/CD y configuración básica de supervisión.

Las generaciones complejas de varios archivos consumen más PRU, aproximadamente **3–5 PRU** para el andamiaje de proyectos completos, mientras que tareas reutilizables simples suelen consumir **1–2 PRU**.

### Automatización basada en historias de usuario

GitHub Copilot puede transformar requisitos y casos de usuario en implementaciones:

* **Scaffolding de características:** estructuras completas con modelos, API y componentes front-end.
* **Lógica de negocios:** implementación basada en reglas descritas en lenguaje natural.
* **Patrones de integración:** autenticación, registro e integración con servicios externos.
* **Automatización de extremo a extremo:** generación de back-end, cambios de base de datos, documentación de API y front-end básico.
* **Calidad integrada:** manejo de errores, validación, registro y consideraciones básicas de seguridad.

Este enfoque permite pasar rápidamente del concepto a un prototipo funcional y obtener comentarios tempranos.

### Aceleración de flujos de trabajo de solicitudes de incorporación de cambios

GitHub Copilot puede generar cambios listos para revisar y reducir el tiempo entre desarrollo e implementación.

#### Generación de código lista para PR

Puede generar:

* Implementaciones completas con manejo de errores, registros y casos límite.
* Código coherente con las convenciones y patrones arquitectónicos del proyecto.
* Comentarios, documentación de funciones y actualizaciones del README.
* Pruebas unitarias, de integración y ejemplos de uso.

#### Asistencia inteligente para revisión de código

Puede ayudar a:

* Detectar problemas y sugerir mejoras antes de crear un pull request.
* Generar comentarios de revisión constructivos y específicos.
* Proponer alternativas cuando los revisores solicitan cambios.
* Mejorar documentación según los comentarios de revisión.
* Resolver conflictos de combinación considerando la intención de ambas ramas.

Pedir varios borradores de refactorización en una PR puede consumir **2–3 PRU por borrador**.

### Flujos de trabajo de desarrollo colaborativo

Copilot mejora la colaboración mediante:

* **Normalización del código:** patrones y estilos coherentes.
* **Uso compartido de conocimientos:** código basado en procedimientos recomendados del equipo.
* **Conservación del contexto:** ayuda a comprender y continuar código existente.
* **Resolución de conflictos de mezcla:** comprensión de la intención de ambas ramas.

### Flujos de trabajo de IA orquestados

GitHub Copilot puede formar parte de flujos donde distintas funcionalidades de IA trabajan coordinadamente.

#### Desarrollo con varios agentes

Un flujo puede incluir:

1. **Agente de borrador:** genera la implementación inicial.
2. **Agente de revisión:** analiza calidad, seguridad y estándares.
3. **Agente de documentación:** genera o actualiza documentación.
4. **Agente de pruebas:** crea conjuntos de pruebas.

Cada agente se especializa en un área y contribuye a generar código más completo y preparado para producción.

Cada transferencia consume aproximadamente **1 PRU** y un flujo de borrador de dos agentes suele utilizar **2–3 PRU**.

#### Funcionalidades avanzadas de razonamiento

Los modos de razonamiento premium ofrecen:

* Comprensión de bases de código grandes y relaciones complejas.
* Sugerencias avanzadas de arquitectura.
* Asistencia para refactorizaciones complejas.
* Coordinación de cambios en varios archivos.

Las ejecuciones premium agregan contexto y razonamiento, pero pueden duplicar el consumo de PRU, con aproximadamente **4+ PRU por solicitud**.

#### Finalización automatizada de historias

Copilot puede transformar casos de usuario y requisitos en características implementables mediante:

* **Análisis de requisitos:** generación de planes de implementación a partir de casos de usuario y criterios de aceptación.
* **Scaffolding de características:** creación de controladores, servicios, modelos y pruebas.
* **Configuración de integración:** generación del código necesario para integrar nuevas características.
* **Automatización de control de calidad:** incorporación de manejo de errores, registro y supervisión.

Esto reduce el tiempo entre la idea y la implementación.

### Finalización de código personalizada

GitHub Copilot adapta sus sugerencias al estilo de codificación y al contexto del proyecto:

* **Reconocimiento contextual:** analiza el entorno de desarrollo y la estructura del proyecto.
* **Aprendizaje de patrones:** adapta las sugerencias según los patrones y preferencias de codificación del desarrollador.

### Resultado en productividad

El uso de GitHub Copilot permite reducir el tiempo dedicado a tareas rutinarias, acelerar el aprendizaje de nuevas tecnologías y mantener un mayor foco durante la jornada, dejando más tiempo para resolver problemas complejos e innovar.

## Alineación con las preferencias del desarrollador

GitHub Copilot está diseñado para integrarse en los flujos de trabajo de los desarrolladores, adaptándose a sus preferencias y estilos de codificación.

### Generación y finalización de código

* **Varias sugerencias:** ante escenarios ambiguos, ofrece diferentes alternativas para que el desarrollador elija.
* **Expresiones específicas del idioma:** entiende y sugiere expresiones y procedimientos recomendados propios del lenguaje.

### Escritura de pruebas unitarias y documentación

* **Generación de casos de prueba:** sugiere pruebas relevantes, incluidos casos perimetrales.
* **Códigos auxiliares de documentación:** genera documentación inicial para funciones, clases y módulos.
* **Expansión de comentarios:** convierte comentarios breves en explicaciones más detalladas.

### Refactorización de código

* **Reconocimiento de patrones:** identifica patrones y propone alternativas más limpias o eficaces.
* **Sugerencias de sintaxis modernas:** propone características actuales del lenguaje.
* **Mantenimiento de coherencia:** alinea las refactorizaciones con el estilo existente del código base.

### Asistencia para la depuración

Aunque no es un depurador completo, GitHub Copilot puede:

* **Explicar errores:** proporcionar explicaciones en lenguaje natural y posibles correcciones.
* **Generar instrucciones de registro:** sugerir registros para diagnosticar problemas.
* **Sugerir casos de prueba:** proponer pruebas adicionales para aislar errores difíciles de reproducir.

### Soporte de ciencia de datos

GitHub Copilot también puede asistir en ciencia de datos y análisis mediante:

* **Funciones estadísticas:** implementación de funciones y pruebas estadísticas.
* **Visualización de datos:** generación de código con bibliotecas como Matplotlib, Seaborn o Plotly.
* **Preprocesamiento de datos:** manejo de valores faltantes, codificación de variables categóricas y escalado de características numéricas.
* **Evaluación de modelos:** generación de código para métricas y visualización del rendimiento.

### Preferencia por flujos de trabajo simplificados

GitHub Copilot se adapta a la preferencia por flujos que minimizan el cambio de contexto y la sobrecarga manual.

#### Experiencia de desarrollo integrada

* **Asistencia nativa del IDE:** funciona directamente en entornos de desarrollo populares.
* **Reconocimiento contextual:** comprende el contexto del proyecto y genera sugerencias alineadas con sus patrones y convenciones.
* **Configuración mínima:** funciona eficazmente sin una configuración extensa.

#### Finalización de tareas autónomas

* **Generación de características de extremo a extremo:** desde los requisitos hasta código implementable, pruebas y documentación.
* **Valores predeterminados inteligentes:** selecciona valores razonables para detalles de implementación, permitiendo centrarse en la lógica de alto nivel.
* **Mejora progresiva:** permite comenzar con código generado y refinarlo en lugar de partir desde cero.

#### Automatización con enfoque en la calidad

* **Procedimientos recomendados integrados:** incorpora consideraciones de seguridad, manejo de errores y optimización del rendimiento.
* **Mantenimiento de coherencia:** sigue las convenciones del proyecto y los estándares del equipo.
* **Cobertura completa:** incorpora pruebas y documentación adecuadas.

Al adaptarse a estas preferencias, GitHub Copilot se convierte en algo más que una herramienta de finalización de código: proporciona asistencia integrada en diferentes aspectos del proceso de desarrollo.

## IA en el ciclo de vida de desarrollo del software (SDLC)

Las funcionalidades de GitHub Copilot se extienden más allá de las tareas de codificación individuales e influyen en varias fases del SDLC, desde el planeamiento inicial hasta la implementación y el mantenimiento.

### Análisis de requisitos

Aunque GitHub Copilot no recopila directamente los requisitos, puede ayudar a convertirlos en estructuras iniciales:

* **Creación rápida de prototipos:** genera fragmentos de código a partir de descripciones de alto nivel.
* **Implementación de casos de usuario:** transforma casos de usuario en definiciones iniciales de clases o funciones.
* **Diseño de API:** sugiere estructuras de API basadas en la funcionalidad descrita.

### Diseño y desarrollo

GitHub Copilot puede aumentar la productividad mediante:

* **Generación de código reutilizable:** automatiza estructuras repetitivas.
* **Implementación de modelos de diseño:** sugiere patrones adecuados según el contexto.
* **Optimización de código:** ofrece alternativas más eficaces.
* **Traducción entre lenguajes:** ayuda a traducir conceptos o fragmentos de código entre lenguajes.

### Pruebas y control de calidad

Puede simplificar las pruebas mediante:

* **Creación de pruebas unitarias:** genera casos basados en firmas y comportamiento de funciones.
* **Generación de datos de prueba:** crea conjuntos de datos realistas.
* **Identificación de casos límite:** propone escenarios adicionales.
* **Sugerencias de aserción:** propone aserciones según el comportamiento esperado.

#### Flujos de trabajo de pruebas automatizadas

Puede organizar estrategias completas de prueba:

* **Arquitectura del conjunto de pruebas:** diseño de pruebas unitarias, de integración y de extremo a extremo.
* **Canalizaciones de automatización:** generación de configuraciones de pruebas e integración CI/CD.
* **Puertas de calidad:** comprobaciones automatizadas antes de avanzar en la canalización.
* **Pruebas de rendimiento:** generación de pruebas comparativas y de carga.

La automatización integra la garantía de calidad en el proceso de desarrollo, permitiendo entregas más rápidas manteniendo los estándares de calidad.

### Implementación

Aunque no interviene directamente en los procesos de implementación, puede ayudar con:

* **Archivos de configuración:** creación de configuraciones para distintos entornos.
* **Scripts de implementación:** sugerencia de comandos y scripts.
* **Documentación:** actualización de documentación de implementación.

### Soporte técnico y mantenimiento

GitHub Copilot puede ayudar en:

* **Corrección de errores:** sugerencia de posibles soluciones a partir de errores y código circundante.
* **Refactorización:** mejora y modernización del código existente.
* **Documentación:** sincronización de comentarios y documentación con los cambios.
* **Código heredado:** explicación y ayuda para trabajar con código desconocido o heredado.

## Construcción con flujos orquestados de trabajo de IA

La IA orquestada coordina varias funcionalidades de inteligencia artificial para controlar tareas complejas de desarrollo, combinando los puntos fuertes de distintos agentes.

### Patrón simple de orquestación de agentes

Un flujo básico de dos agentes puede incluir:

1. **Agente de borrador (GitHub Copilot):**

   * Analiza los requisitos.
   * Genera la implementación inicial.
   * Incluye funcionalidad básica y manejo de errores.
   * Crea pruebas unitarias básicas.
   * Genera documentación insertada.
   * Define puntos de integración con código existente.
2. **Agente de revisión:**

   * Evalúa la calidad frente a los estándares del proyecto.
   * Identifica vulnerabilidades de seguridad.
   * Sugiere optimizaciones de rendimiento.
   * Revisa el cumplimiento de patrones arquitectónicos.

Este enfoque permite validar los estándares de calidad antes de la revisión humana y reducir iteraciones.

Cada transferencia consume aproximadamente **1 PRU** y un flujo de dos agentes suele utilizar **2–3 PRU**.

### Funcionalidades de orquestación avanzadas

#### Integración de razonamiento de alta calidad

El razonamiento avanzado permite:

* **Toma de decisiones arquitectónicas:** analizar ventajas y desventajas considerando escalabilidad, mantenimiento y rendimiento.
* **Análisis de impacto entre sistemas:** comprender cómo los cambios afectan a otras partes de sistemas distribuidos.
* **Coordinación de refactorizaciones complejas:** organizar cambios en múltiples archivos y módulos conservando funcionalidad y rendimiento.
* **Optimización de patrones de integración:** sugerir formas óptimas de conectar nuevas características con la arquitectura existente.

Las ejecuciones Premium agregan contexto y razonamiento y pueden consumir aproximadamente **4 o más PRU por solicitud**.

#### Flujos completos de entrega de características

La IA orquestada puede cubrir la entrega completa desde los requisitos hasta la implementación:

1. **Análisis:** análisis de casos de usuario y requisitos técnicos para crear planes de implementación.
2. **Implementación:** generación del código completo de la característica.
3. **Control de calidad:** creación de conjuntos de pruebas y comprobaciones de calidad.
4. **Documentación:** generación de documentación de usuario, API y mantenimiento.
5. **Implementación:** creación de scripts de implementación y configuraciones de supervisión.

Este enfoque permite entregar características con mayor rapidez y mantener estándares de calidad en las distintas fases del desarrollo.

## Limitaciones e impacto de GitHub Copilot

Aunque GitHub Copilot ofrece ventajas significativas, es fundamental comprender sus limitaciones y medir con precisión su impacto en los procesos de desarrollo.

### Calidad y corrección del código

* **Potencial de errores:** GitHub Copilot a veces puede sugerir código que contenga errores o que no cumpla los requisitos.
* **Problemas de seguridad:** el código generado no siempre puede ajustarse a los procedimientos de seguridad recomendados, por lo que requiere una revisión cuidadosa.
* **Interpretación incorrecta del contexto:** podría comprender incorrectamente el contexto más amplio y generar sugerencias inapropiadas.

### Especificidad del lenguaje y del marco

* **Rendimiento variable:** la eficacia puede variar entre diferentes lenguajes de programación y marcos de trabajo.
* **Tecnologías de nicho:** para tecnologías menos comunes o más recientes, las sugerencias pueden ser menos precisas o relevantes.

### Dependencia de datos de entrenamiento

* **Sesgo en sugerencias:** las sugerencias reflejan patrones de los datos de entrenamiento, que pueden incluir sesgos o prácticas obsoletas.
* **Problemas de derechos de autor:** existe un debate continuo sobre las implicaciones de derechos de autor del código generado a partir de modelos entrenados.

### Resolución de problemas complejos

* **Limitación en el diseño de alto nivel:** destaca en tareas de nivel de código, pero puede no comprender decisiones arquitectónicas complejas.
* **Restricciones de creatividad:** aunque es útil, no puede reemplazar la creatividad humana en la resolución de problemas nuevos.

## Medición de las mejoras de productividad

Comprender las mejoras de productividad proporcionadas por GitHub Copilot es esencial para maximizar sus ventajas. La **API REST para las métricas de uso de GitHub Copilot** y la **Encuesta para desarrolladores de GitHub Copilot** permiten medir y analizar su influencia en el flujo de trabajo de desarrollo.

### API REST para las métricas de uso de GitHub Copilot

GitHub proporciona una API de REST para acceder a las métricas de uso de GitHub Copilot para miembros empresariales, equipos y miembros de la organización.

Estas métricas ofrecen información sobre:

* Uso diario de GitHub Copilot.
* Finalizaciones.
* Interacciones de chat.
* Participación del usuario.
* Editores utilizados.
* Lenguajes utilizados.
* Sugerencias y aceptaciones.
* Usuarios activos.

#### Resumen del uso para los miembros de la empresa

**Punto final:**

`GET /enterprises/{enterprise}/GitHub Copilot/usage`

Proporciona un desglose diario de las métricas de uso agregadas para finalizaciones y chat en todos los usuarios de una empresa, incluyendo sugerencias, aceptaciones y usuarios activos, desglosados por editor y lenguaje.

**Solicitud de ejemplo:**

```bash
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <YOUR-TOKEN>" \
  https://api.github.com/enterprises/ENTERPRISE/GitHub Copilot/usage
```

**Respuesta:**

* **Código de estado:** `200 OK`
* **Cuerpo:** matriz JSON con métricas diarias, incluidas sugerencias, aceptaciones, usuarios activos y desglose por editor e idioma.

#### Resumen del uso para un equipo empresarial

**Punto final:**

`GET /enterprises/{enterprise}/team/{team_slug}/GitHub Copilot/usage`

Proporciona un desglose diario de las métricas de uso agregadas para finalizaciones y chat en un equipo empresarial específico.

**Solicitud de ejemplo:**

```bash
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <YOUR-TOKEN>" \
  https://api.github.com/enterprises/ENTERPRISE/team/TEAM_SLUG/GitHub Copilot/usage
```

**Respuesta:**

* **Código de estado:** `200 OK`
* **Cuerpo:** matriz JSON con métricas diarias para el equipo, incluidas sugerencias, aceptaciones, usuarios activos y desglose por editor e idioma.

#### Resumen del uso para miembros de la organización

**Punto final:**

`GET /orgs/{org}/GitHub Copilot/usage`

Proporciona un desglose diario de las métricas de uso agregadas para finalizaciones y chat en toda una organización.

**Solicitud de ejemplo:**

```bash
curl -L \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <YOUR-TOKEN>" \
  https://api.github.com/orgs/ORG/GitHub Copilot/usage
```

**Respuesta:**

* **Código de estado:** `200 OK`
* **Cuerpo:** matriz JSON con métricas diarias para la organización, incluidas sugerencias, aceptaciones, usuarios activos y desglose por editor e idioma.

## Marco de medición del impacto

Para evaluar sistemáticamente el impacto de GitHub Copilot mediante la API de métricas de uso, se pueden considerar las siguientes fases:

1. **Evaluación**

   * Durante la adopción inicial, centrarse en indicadores como satisfacción del desarrollador y tasas de finalización de tareas.
   * Recopilar métricas como promedio de usuarios activos diarios, tasa de aceptación total y líneas de código aceptadas.

2. **Adopción**

   * Supervisar las métricas de productividad y habilitación a medida que Copilot se integra en el flujo de trabajo.
   * Identificar áreas donde pueda ser necesario más entrenamiento.

3. **Optimización**

   * Utilizar las métricas para relacionar el impacto de Copilot con objetivos organizativos más amplios, como reducir el tiempo de comercialización o mejorar la calidad del código.

4. **Eficiencia sostenida**

   * Evaluar continuamente la eficacia de GitHub Copilot a medida que evoluciona la organización.
   * Mantener una supervisión y ajuste continuos para garantizar mejoras de productividad a largo plazo.

## Encuesta para desarrolladores de GitHub Copilot

La Encuesta de desarrolladores de GitHub Copilot permite recopilar información de los equipos para comprender:

* Cómo se utiliza GitHub Copilot.
* Sus ventajas.
* Los desafíos de los desarrolladores.
* Su impacto en el flujo de trabajo.
* Su influencia en la dinámica del equipo.

La encuesta dispone de dos formatos:

* **Formato corto:** orientado a comentarios frecuentes y rápidos.
* **Formato largo:** orientado a análisis más profundos durante las fases de evaluación y adopción.

### Cadencia y tiempo de la encuesta

* **Encuesta corta:** puede realizarse cada dos semanas cuando se necesitan comentarios frecuentes, especialmente combinada con otros canales de feedback.
* **Encuesta larga:** se recomienda no realizarla más de una vez cada cuatro semanas, especialmente al finalizar las fases de evaluación y adopción.

### Estructuración de la encuesta

Las preguntas deben adaptarse a las necesidades específicas de la organización.

#### Encuesta corta

Se centra en:

* Satisfacción general.
* Desafíos específicos.
* Tiempo ahorrado o desperdiciado.

Preguntas de ejemplo:

* "¿Cómo se sentiría si ya no pudiera usar GitHub Copilot?"
* "Cuando uso GitHub Copilot, disfruto más codificando / escribo código de mejor calidad / completo las tareas más rápido".
* "¿Qué desafíos ha encontrado en el uso de GitHub Copilot desde su última encuesta?"

#### Encuesta larga

Permite analizar con mayor profundidad el impacto de GitHub Copilot y su efecto en el equipo.

Preguntas de ejemplo:

* "Uso GitHub Copilot para codificar en un lenguaje familiar / explorar un nuevo lenguaje / escribir código repetitivo".
* "Al utilizar GitHub Copilot, mi equipo realiza mejores revisiones del código / combina el código en producción más rápidamente".
* "¿Qué desafíos ha encontrado en el uso de GitHub Copilot desde su última encuesta?"

### Análisis de los resultados

Una vez completadas las encuestas:

* **Consideraciones de privacidad:** las respuestas deben anonimizarse y no poder rastrearse a desarrolladores individuales.
* **Seguimiento de datos:** las respuestas pueden integrarse en herramientas o hojas de cálculo de Business Intelligence (BI) para facilitar el análisis.
* **Análisis de tendencias:** realizar un seguimiento de los resultados a lo largo del tiempo para identificar tendencias y tomar decisiones informadas.

### Mejora continua

La información recopilada debe utilizarse para:

* Abordar los desafíos identificados.
* Aprovechar las ventajas notificadas por los desarrolladores.
* Ajustar el uso de la herramienta.
* Maximizar la productividad.

## Medición basada en datos

La combinación de la **API REST de métricas de uso de GitHub Copilot** y la **Encuesta de desarrolladores de GitHub Copilot** permite ir más allá de la evidencia anecdótica y obtener información concreta sobre cómo GitHub Copilot influye en el proceso de codificación.

Este enfoque controlado por datos permite:

* Tomar decisiones fundamentadas.
* Medir la influencia de GitHub Copilot en el flujo de trabajo.
* Identificar áreas donde su uso puede optimizarse.
* Evaluar mejoras de productividad.
* Comprender los desafíos de los desarrolladores.
* Mantener una mejora continua del uso de GitHub Copilot.
