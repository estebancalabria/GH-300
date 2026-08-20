# Revisiones de código con GitHub Copilot

## Introducción

Las revisiones de código son fundamentales para mantener la calidad y colaboración, pero pueden generar cuellos de botella por ciclos largos, comentarios incoherentes, dificultades para proporcionar sugerencias accionables y errores que pasan desapercibidos.

GitHub Copilot actúa como **revisor colaborativo y asistente**, sin reemplazar a los revisores humanos. Puede:

* Detectar problemas y sugerir mejoras.
* Redactar resúmenes y comentarios de revisión.
* Detectar y corregir vulnerabilidades.
* Aplicar instrucciones personalizadas de revisión.
* Mantener patrones y estándares coherentes entre equipos y repositorios.
* Revisar código tanto en GitHub.com como localmente en el IDE.

El resultado buscado es acelerar las revisiones, mejorar la calidad y reducir la carga cognitiva de los equipos.

### Unidades de solicitud Premium (PRU)

Las **PRU** potencian las funcionalidades avanzadas de Copilot. Las tareas de nivel premium, como revisar solicitudes de incorporación de cambios completas, ejecutar revisiones en modo agente o realizar análisis complejos de varios pasos, consumen PRU.

Estas solicitudes proporcionan mayor capacidad de procesamiento y profundidad de contexto para obtener:

* Razonamiento más completo.
* Comprobaciones más profundas de procedimientos recomendados.
* Resultados más confiables.
* Aplicación de instrucciones personalizadas.

Es importante supervisar el consumo de PRU, optimizar el plan y utilizarlas donde aporten mayor valor.

## Objetivos de aprendizaje

* Explicar cómo GitHub Copilot simplifica las revisiones de código y las solicitudes de incorporación de cambios.
* Identificar las principales características de Copilot para revisiones.
* Solicitar e interpretar revisiones de Copilot en GitHub.com y comprender sus límites.
* Ejecutar revisiones localmente en el IDE y aplicar instrucciones personalizadas.
* Utilizar PRU para análisis más profundos y con mayor contexto.
* Automatizar revisiones entre repositorios mediante conjuntos de reglas y comprobaciones de estado.
* Aplicar las sugerencias de Copilot de forma responsable, combinándolas con juicio humano y pruebas.

## Prerrequisitos

* Cuenta de GitHub.
* GitHub Copilot habilitado. Se recomiendan Copilot Pro, Pro+, Business o Enterprise para las funcionalidades completas de revisión.
* Conocimientos básicos sobre solicitudes de cambios y revisiones de código.
* Visual Studio Code o IDE de JetBrains, opcional pero recomendado para revisiones locales.

# Lo que GitHub Copilot agrega al proceso de revisión

Copilot ayuda a reducir el trabajo de los revisores al:

* Detectar problemas comunes.
* Redactar comentarios de revisión.
* Resumir solicitudes de incorporación de cambios.
* Detectar riesgos de seguridad.
* Aplicar directrices personalizadas del equipo.
* Revisar código dentro del IDE.
* Trabajar con diferentes lenguajes y convenciones.

## Características clave

### Resúmenes de solicitudes de incorporación de cambios

Copilot puede generar automáticamente descripciones con:

* Resumen de los cambios.
* Lista de archivos afectados.

Esto proporciona contexto a los revisores antes de analizar los cambios.

### Correcciones de seguridad

La revisión de código de Copilot integrada con el análisis de código de GitHub puede detectar vulnerabilidades en distintos lenguajes.

Por ejemplo, puede detectar una entrada sin sanitizar utilizada con `eval()` y sugerir reemplazarla por un analizador seguro como `JSON.parse()`, además de proporcionar un parche alineado con las directrices del repositorio.

### Explicaciones línea a línea

Los revisores pueden seleccionar código y pedir a Copilot que explique su funcionamiento para comprender rápidamente código desconocido.

### Redacción de comentarios

Copilot puede generar comentarios claros y accionables basados en procedimientos recomendados o directrices del equipo.

### Revisiones en el IDE

Copilot también puede revisar código directamente en el IDE, permitiendo detectar y solucionar problemas antes de abrir una solicitud de incorporación de cambios.

## PRU y funcionalidades avanzadas

Asignar Copilot como revisor de una solicitud de cambios utiliza PRU cuando realiza comentarios.

Las revisiones pueden combinarse con `.github/copilot-instructions.md` para aplicar reglas específicas de legibilidad, seguridad o estilo.

Las PRU permiten pasar de comentarios genéricos a sugerencias más precisas, con explicaciones, recomendaciones y correcciones de código en línea.

## Cinco formas en que Copilot ayuda en las revisiones

* Sugerencias de revisión de código.
* Revisiones en varios lenguajes.
* Formateo de datos en solicitudes de incorporación de cambios.
* Generación de resúmenes efectivos.
* Explicación y revisión del código.

## Sugerencias de Copilot en las revisiones

Desde la vista **Archivos modificados** de una solicitud de incorporación de cambios, se puede seleccionar una línea o bloque de código y pedir a Copilot que:

* Sugiera mejoras.
* Detecte posibles problemas.
* Proponga refactorizaciones.

Por ejemplo, ante lógica repetida en Ruby, se puede solicitar una refactorización más limpia. Copilot genera una propuesta que el revisor puede incorporar al comentario junto con su propia explicación.

Esto mantiene la responsabilidad de la revisión en el humano y utiliza Copilot para generar comentarios accionables.

## Revisión en varios lenguajes

Copilot puede detectar áreas que no cumplen los procedimientos recomendados o las directrices del equipo y proponer mejoras alineadas con las convenciones del lenguaje.

Esto permite proporcionar comentarios más precisos incluso cuando el revisor no domina el lenguaje utilizado.

## Formateo de datos en solicitudes de incorporación de cambios

Copilot puede detectar tablas mal formateadas en las descripciones de las solicitudes de incorporación de cambios y proponer una versión corregida según las directrices de Markdown de la empresa.

Esto permite mantener un formato coherente y aceptar las correcciones directamente desde la revisión.

Copilot actúa como revisor automático: analiza el contenido, aplica las instrucciones de `.github/copilot-instructions.md` y proporciona una versión corregida en línea.

## Generación de resúmenes de solicitudes de cambios

Desde el editor de descripción de una solicitud de cambios, el icono de Copilot permite generar:

* Un resumen.
* Un esquema inicial de los cambios.

Aunque el desarrollador modifique posteriormente el resultado, disponer de un punto de partida estructurado ahorra tiempo y proporciona a los revisores la información necesaria.

## Explicación y revisión del código

Copilot puede explicar código desconocido y realizar una revisión inicial de las propias solicitudes de cambios antes de solicitar comentarios a los compañeros.

Esto ayuda a:

* Detectar problemas pequeños.
* Validar procedimientos recomendados.
* Aumentar la confianza en la calidad del código.

# Uso de Copilot como revisor en GitHub.com

En GitHub.com se puede agregar Copilot desde el menú **Revisores**.

Copilot genera comentarios que **no representan una aprobación ni un rechazo**, por lo que no bloquea las combinaciones. Su función es proporcionar contexto y sugerencias para los revisores humanos.

Los comentarios se comportan como los de otros revisores: pueden recibir reacciones, resolverse o comentarse.

Copilot puede señalar, entre otros aspectos:

* Tipos faltantes.
* Problemas de formato.
* Posibles errores.

## Proceso de revisión en GitHub.com

1. **Abrir o crear una solicitud de incorporación de cambios.**
2. **Agregar Copilot como revisor** desde el menú **Revisores**.
3. **Esperar la revisión.** Las revisiones suelen finalizar en menos de 30 segundos.
4. **Revisar los comentarios** que Copilot deja sobre las líneas de código correspondientes.
5. **Aplicar las sugerencias**, utilizando Copilot para generar soluciones cuando sea necesario.
6. **Validar los cambios**, ejecutando las pruebas correspondientes.

Ejemplo de solicitud:

> Sugerir una corrección para este comentario de revisión: Reemplace `exec()` por una función más segura.

Copilot puede proponer reemplazarlo por `subprocess.run()`. El desarrollador debe probar los cambios y verificar que las pruebas pasen.

Las PRU permiten analizar el comentario junto con el contexto del código para generar soluciones de mayor calidad.

## Límites de Copilot en las revisiones

Copilot tiene un papel de **asesor**:

* No aprueba ni rechaza solicitudes de incorporación de cambios.
* Sus comentarios no cuentan para las aprobaciones requeridas.
* No reemplaza a los revisores humanos.

Debe utilizarse para detectar problemas, generar sugerencias accionables y acelerar comprobaciones rutinarias. Las decisiones arquitectónicas, los inconvenientes con matices y la aprobación final corresponden a revisores humanos.

# Detección temprana y automatización de revisiones

Las revisiones pueden realizarse antes de abrir una solicitud de incorporación de cambios mediante Copilot en **Visual Studio Code o IDE de JetBrains**.

Esto permite detectar tempranamente:

* Infracciones de estilo.
* Problemas de seguridad.
* Incumplimientos de procedimientos recomendados.

También es posible automatizar las revisiones para todas las solicitudes de cambios y escalar el proceso entre repositorios y equipos.

## Revisiones locales en el IDE

Se puede crear `.github/copilot-instructions.md` con reglas como:

* Centrarse en la seguridad y evitar interpolaciones de cadenas no seguras.
* Asegurar que las funciones tengan docstrings que expliquen parámetros y tipos de valores devueltos.

Copilot aplica estas reglas a las revisiones y analiza diferencias más grandes con información contextual alineada con el estilo del repositorio.

### Caso de uso

Un desarrollador agrega código repetitivo en un servicio TypeScript. Copilot lo detecta y sugiere extraer una función auxiliar. El desarrollador puede corregirlo antes de enviar el código, reduciendo el ruido de la revisión posterior.

# Instrucciones personalizadas específicas de rutas

Las instrucciones personalizadas pueden aplicarse a rutas específicas para guiar las revisiones de Copilot o del Agente de la Nube de Copilot.

## Configuración

1. Crear `.github/instructions` en la raíz del repositorio si no existe.
2. Crear uno o varios archivos que terminen en `.instructions.md`.
3. Definir las rutas mediante `applyTo` utilizando sintaxis glob.
4. Escribir debajo del frontmatter las instrucciones de revisión en Markdown.

Ejemplos de rutas:

* `app/models/**/*.rb` para modelos Ruby.
* `**/*.ts,**/*.tsx` para archivos TypeScript.
* `**` para todos los archivos del repositorio.

Copilot seguirá las instrucciones en las revisiones o generación de código para las rutas correspondientes.

# PRU para análisis profundo en el IDE

Las revisiones locales con PRU permiten utilizar modelos más avanzados para:

* Analizar diferencias más grandes.
* Aplicar instrucciones personalizadas.
* Detectar problemas de estilo.
* Detectar brechas de seguridad.
* Detectar problemas relacionados con mejores prácticas.

El análisis se realiza en el lugar donde se escribe y prueba el código, dejando el juicio final y la aprobación en manos de los revisores humanos.

# Automatización de revisiones y escalado con conjuntos de reglas

GitHub permite configurar **conjuntos de reglas** para asignar automáticamente Copilot a las solicitudes de cambios dirigidas a ramas protegidas.

Las revisiones pueden combinarse con comprobaciones de estado:

* **Copilot:** revisa estilo y legibilidad.
* **Code scanning:** detecta vulnerabilidades.
* **Pruebas:** validan la funcionalidad.

Cada revisión de Copilot utiliza PRU, por lo que las organizaciones deben presupuestar el consumo según el volumen de revisiones y realizar un seguimiento de su uso.

La automatización permite revisar de forma coherente incluso pequeños cambios y actualizaciones de dependencias, reduciendo el riesgo de regresiones desapercibidas.

# Revisiones automáticas para una cuenta

Esta opción está disponible para planes **Copilot Pro o Copilot Pro+**.

Al habilitar la revisión automática desde la configuración personal de Copilot, cada solicitud de cambios que se abra se revisará automáticamente.

### Configuración

1. En GitHub, seleccionar la imagen de perfil y **Su Copilot**.
2. Buscar la opción de revisión de código automática de Copilot.
3. Seleccionar **Habilitado**.

A partir de ese momento, Copilot se agregará automáticamente a las solicitudes de incorporación de cambios.

# Revisiones automáticas de un repositorio

Los administradores pueden configurar revisiones automáticas únicamente en determinados repositorios mediante conjuntos de reglas de rama.

### Configuración

1. Ir a **Configuración** del repositorio.
2. Expandir **Código y automatización** y seleccionar **Reglas → Conjuntos de reglas**.
3. Seleccionar **Nuevo conjunto de reglas → Nuevo conjunto de reglas de rama**.
4. Definir el nombre, establecer el estado de cumplimiento como **Activo** y seleccionar las ramas de destino.
5. En las reglas de rama, habilitar **Requerir una solicitud de cambios antes de combinarla**.
6. Seleccionar **Solicitar revisión de solicitud de cambios de Copilot**.
7. Crear el conjunto de reglas.

Cada solicitud de cambios dirigida a las ramas configuradas incluirá automáticamente la revisión de Copilot.

También puede habilitarse **Requerir resolución de conversación antes de combinar** para fomentar que los desarrolladores revisen los comentarios de Copilot.

# Revisiones automáticas en una organización

Los propietarios de una organización pueden escalar las revisiones entre múltiples repositorios mediante conjuntos de reglas.

### Configuración

1. Seleccionar **Sus organizaciones** desde el perfil de GitHub.
2. Elegir la organización y entrar en **Configuración**.
3. Seleccionar **Repositorio → Conjuntos de reglas**.
4. Crear **Nuevo conjunto de reglas → Nuevo conjunto de reglas de rama**.
5. Definir el nombre y establecer el estado de cumplimiento como **Activo**.
6. Agregar repositorios mediante patrones de inclusión o exclusión.
7. Definir las ramas de destino.
8. Habilitar **Exigir una solicitud de cambios antes de combinar**.
9. Activar **Solicitar revisión de solicitud de cambios de Copilot**.
10. Crear el conjunto de reglas.

Esto permite mantener estándares coherentes y reducir los tiempos de revisión en toda la organización.

# Medición del impacto y optimización de PRU

Las **PRU** son el recurso utilizado por las funcionalidades de revisión más avanzadas de GitHub Copilot.

Se consumen, por ejemplo, al:

* Revisar solicitudes de cambios grandes.
* Aplicar instrucciones personalizadas a un código base completo.
* Realizar análisis profundo de cambios en el IDE.

## Objetivos

* Definir las PRU y explicar cómo habilitan las funcionalidades avanzadas.
* Medir el impacto de las revisiones basadas en PRU.
* Presupuestar y optimizar su uso.

## Concepto de PRU

Las PRU proporcionan capacidad adicional para tareas que requieren mayor contexto y razonamiento.

Las tareas rutinarias y ligeras pueden no consumir PRU, mientras que tareas como revisar un cambio de 1500 líneas en múltiples archivos, aplicar instrucciones personalizadas y comprobar seguridad y estilo requieren capacidades premium.

Las PRU permiten:

* Analizar diferencias completas.
* Interpretar directrices personalizadas.
* Generar correcciones accionables.
* Proporcionar análisis detallado y contextual.

### Ejemplo

Una refactorización masiva que afecta a decenas de archivos puede ser revisada por Copilot utilizando PRU para aplicar las reglas de estilo y seguridad del repositorio, detectar interpolaciones de cadenas inseguras y generar comentarios explicativos.

Los revisores humanos pueden concentrarse entonces en el impacto arquitectónico.

## Importancia de las PRU para los equipos

Las PRU permiten:

* **Análisis más profundo:** detectar vulnerabilidades sutiles, lógica duplicada e infracciones de estilo en diferencias grandes.
* **Coherencia:** aplicar automáticamente las mismas comprobaciones de seguridad, legibilidad y estilo.
* **Control de ráfagas de actividad:** mantener la calidad durante períodos de alta actividad mientras los revisores humanos se concentran en decisiones complejas.

### Ejemplo con múltiples lenguajes

En una arquitectura de microservicios con Go, Python y TypeScript, Copilot puede utilizar PRU para revisar cada servicio según las mejores prácticas del lenguaje, detectar una llamada peligrosa a `eval()` en JavaScript y señalar una falta de comprobación de errores en Go.

## Medición del impacto

Para evaluar las revisiones basadas en PRU se pueden seguir métricas como:

* **Plazo de solicitud de cambios:** tiempo desde la apertura hasta la combinación.
* **Indicadores de calidad:** reducción de problemas de estilo o seguridad posteriores a la combinación.
* **Experiencia del desarrollador:** percepción sobre rapidez y claridad de las revisiones.

### Ejemplo de métrica

Antes de utilizar PRU, las solicitudes de cambios grandes tardaban en promedio tres días en combinarse y generaban ajustes de estilo posteriores.

Después de habilitar revisiones con PRU, las mismas solicitudes se combinaron en un día y requirieron menos confirmaciones de seguimiento.

# Optimización del uso de PRU

* **Planificar por adelantado:** establecer alertas al alcanzar el 75 %, 90 % y 100 % del uso mensual.
* **Utilizar PRU estratégicamente:** reservarlas para cambios grandes o de alto riesgo y utilizar sugerencias estándar para ediciones sencillas.
* **Refinar los mensajes:** solicitudes claras y específicas para reducir reintentos y consumo innecesario.
* **Escalar el plan cuando sea necesario:** considerar un plan superior de Copilot si el consumo aumenta de forma constante.

### Ejemplo

Un equipo detecta que consume muchas PRU en cambios de documentación triviales. Modifica su flujo de trabajo para utilizar solicitudes que no requieren PRU para pequeñas ediciones y reservar las revisiones premium para código de producción.

Como resultado, reduce un **30 %** el consumo mensual de PRU sin perder calidad.

## Idea fundamental

Las PRU hacen posibles las funcionalidades avanzadas de revisión de Copilot. Comprender su funcionamiento, medir su impacto y optimizar su uso permite realizar revisiones más profundas y contextuales, escalar revisiones de alta calidad y mantener el juicio final y la aprobación en manos de revisores humanos.
