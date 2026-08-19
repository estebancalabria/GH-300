# Resumen — GitHub Copilot e Ingeniería de Solicitudes

## Introducción

GitHub Copilot, con tecnología de OpenAI, acelera los flujos de desarrollo de software desde la creación inicial de código hasta implementaciones listas para producción. Puede comprender el contexto del proyecto a partir de datos de entrenamiento que incluyen lenguaje natural y miles de millones de líneas de código fuente disponibles públicamente, incluidos repositorios públicos de GitHub.

Esto permite generar sugerencias contextuales, acelerar cambios de código y automatizar tareas de desarrollo rutinarias.

Para aprovechar al máximo Copilot es fundamental conocer la **ingeniería de solicitudes (prompt engineering)**, es decir, cómo indicar con precisión y eficacia lo que se necesita. La claridad y estrategia de las solicitudes influyen en la calidad del código generado y en la cantidad de iteraciones necesarias.

El módulo aborda:

* Principios y buenas prácticas de ingeniería de solicitudes.
* Estrategias avanzadas, como la solicitud de roles y la administración del historial de chat.
* Cómo Copilot procesa las solicitudes para generar respuestas y sugerencias de código.
* Flujo de datos de las sugerencias de código y del chat.
* Rol de los LLM en GitHub Copilot.
* Creación de solicitudes eficaces para mejorar precisión y relevancia.
* Relación entre solicitudes y respuestas de Copilot.
* Gestión de los datos de las solicitudes, incluida la transmisión segura y el filtrado de contenido.

## Ingeniería de solicitudes

La **ingeniería de solicitudes** es el proceso de crear instrucciones claras para guiar sistemas de IA como GitHub Copilot y generar código adecuado al contexto y necesidades específicas del proyecto.

Una solicitud correctamente diseñada busca obtener código:

* Sintácticamente correcto.
* Funcional.
* Adecuado al contexto del proyecto.

## Principios de ingeniería de solicitudes: las 4 S

Las cuatro reglas fundamentales para crear solicitudes efectivas son:

### 1. Single — Única

Centrar la solicitud en una única tarea o pregunta bien definida para obtener respuestas precisas y útiles.

### 2. Specific — Específica

Utilizar instrucciones explícitas y detalladas para obtener sugerencias de código más aplicables y precisas.

### 3. Short — Corta

Mantener las solicitudes concisas y directas, equilibrando detalle y claridad sin sobrecargar a Copilot.

### 4. Surround — Enmarcada

Proporcionar contexto mediante nombres de archivo descriptivos y archivos relacionados abiertos. Esto permite que Copilot genere sugerencias más adaptadas.

## Buenas prácticas

### Proporcionar claridad

Las solicitudes deben ser claras, específicas y centradas en una única tarea.

### Proporcionar contexto

Agregar información contextual ayuda a Copilot a comprender mejor los requisitos. Los comentarios colocados en el código pueden aportar detalles adicionales.

Copilot también utiliza las pestañas abiertas en paralelo en el editor de código para obtener contexto sobre los requisitos del código.

### Proporcionar ejemplos

Los ejemplos permiten aclarar requisitos y expectativas, haciendo más concretos los conceptos abstractos.

Los ejemplos bien diseñados ayudan a Copilot a identificar patrones y generar sugerencias iniciales más precisas, reduciendo las iteraciones necesarias. Son especialmente útiles para:

* Código reutilizable.
* Plantillas de pruebas.
* Implementaciones repetitivas.
* Características más grandes basadas en patrones existentes.

### Iteración

La primera solicitud no siempre produce código listo para producción. La interacción debe tratarse como un diálogo iterativo con Copilot.

Si el resultado no es adecuado:

1. Revisar el código sugerido.
2. Enriquecer la solicitud con detalles o ejemplos.
3. Volver a solicitar una solución.
4. Iterar hasta obtener el resultado esperado.

Cada iteración aprovecha la comprensión previa de los requisitos y puede acelerar la obtención de código de mayor calidad.

## Cómo aprende Copilot de las solicitudes

GitHub Copilot utiliza modelos de IA entrenados con grandes cantidades de datos. Los ejemplos permiten orientar al modelo hacia patrones y convenciones específicas.

### Aprendizaje sin ejemplos

Copilot genera código basándose en su entrenamiento previo. Es adecuado para patrones comunes y funcionalidades estándar.

### Aprendizaje con un ejemplo

Un ejemplo ayuda a generar respuestas más compatibles con el contexto y las convenciones específicas del código.

### Aprendizaje con varios ejemplos

Varios ejemplos permiten generar implementaciones más sofisticadas, incluyendo diferentes escenarios y casos límite.

Estos enfoques ayudan a mejorar la precisión y reducir el trabajo de revisión manual.

## Cadena de mensajes y administración del historial

Las funcionalidades complejas pueden requerir conversaciones extendidas con GitHub Copilot. Cada turno puede agregar información sobre la implementación, pero mantener historiales demasiado largos aumenta el contexto y el procesamiento necesario.

Ejemplo de una conversación progresiva:

1. Crear una función de autenticación de usuario.
2. Agregar control de errores para credenciales no válidas.
3. Agregar pruebas unitarias.
4. Agregar comentarios JSDoc.
5. Optimizar el rendimiento.

Los avisos largos con todo el historial pueden consumir **2–3 PRU por turno**, mientras que resumir el contexto o restablecer la conversación puede mantener el consumo más cerca de **1 PRU por solicitud**.

### Buenas prácticas para administrar el historial

* **Resumir el contexto** cuando la conversación se vuelve extensa.
* **Restablecer la conversación** al comenzar una nueva funcionalidad y proporcionar solamente el contexto necesario.
* **Usar referencias concisas** al trabajo anterior en lugar de repetir implementaciones completas.

## Solicitud de roles

La **solicitud de roles** consiste en indicar a GitHub Copilot que actúe como un tipo específico de experto. Esto puede mejorar la calidad y relevancia de las soluciones para tareas especializadas.

### Rol de experto en seguridad

Puede orientar a Copilot hacia:

* Saneamiento de entrada.
* Protección contra ataques comunes.
* Patrones de validación estándar del sector.
* Buenas prácticas de seguridad.

### Rol de optimización del rendimiento

Puede orientar hacia:

* Algoritmos y estructuras de datos optimizados.
* Uso eficiente de memoria.
* Consideraciones de escalabilidad.
* Sugerencias de supervisión del rendimiento.

### Rol de especialista en pruebas

Puede orientar hacia:

* Cobertura exhaustiva.
* Casos extremos.
* Implementaciones ficticias.
* Pruebas de condiciones de error.

La solicitud de roles incorpora conocimientos de dominio en las implementaciones iniciales, ayudando a reducir los ciclos de revisión y acelerar la preparación de código para producción.

## Flujo de proceso de solicitud de usuario de GitHub Copilot

GitHub Copilot convierte los mensajes del usuario en sugerencias de código o respuestas mediante un flujo de entrada y salida.

### Flujo de entrada

#### 1. Transmisión segura de solicitudes y recopilación de contexto

El mensaje del usuario se transmite mediante **HTTPS**, protegiendo la información durante su envío a los servidores de GitHub Copilot.

Copilot recibe el mensaje, que puede ser un chat o un comentario en lenguaje natural dentro del código, y recopila contexto adicional:

* Código anterior y posterior a la posición del cursor.
* Nombre y tipo del archivo.
* Información de las pestañas abiertas adyacentes.
* Estructura del proyecto y rutas de archivos.
* Lenguajes y marcos de programación.
* Contexto mediante **Fill-in-the-Middle (FIM)**, considerando el código anterior y posterior para generar sugerencias más precisas.

Este proceso convierte la solicitud de alto nivel en una tarea de codificación concreta.

#### 2. Filtro de proxy

El contexto y la solicitud pasan de forma segura a un servidor proxy alojado en un inquilino de Microsoft Azure propiedad de GitHub.

El proxy filtra el tráfico y bloquea intentos de manipular la solicitud o revelar información sobre cómo el modelo genera las sugerencias.

#### 3. Filtrado de toxicidad

Antes de la generación de código se aplican mecanismos de filtrado para evitar contenido dañino u ofensivo, incluyendo:

* **Discursos de odio y contenido inapropiado:** detección y prevención de lenguaje ofensivo o contenido potencialmente dañino.
* **Datos personales:** filtrado de información como nombres, direcciones o números de identificación para proteger la privacidad y seguridad de los datos.

#### 4. Generación de código con LLM

La solicitud filtrada y analizada se envía a modelos **LLM**, que generan sugerencias de código basadas en la solicitud y el contexto disponible.

El objetivo es generar código relevante, funcional y adaptado a los requisitos específicos del proyecto.

### Flujo de salida

#### 5. Procesamiento posterior y validación

Después de que el modelo genera la respuesta:

* El filtro de toxicidad elimina contenido dañino u ofensivo.
* El servidor proxy realiza comprobaciones finales de calidad, seguridad y estándares éticos.
* Se comprueban errores o vulnerabilidades comunes, como **XSS** o **inyección SQL**.
* Opcionalmente, los administradores pueden habilitar un filtro de **código público coincidente**, que evita sugerencias de más de aproximadamente **150 caracteres** cuando se parecen mucho a código público existente en GitHub.

Si una parte de la respuesta no supera las comprobaciones, puede truncarse o descartarse.

#### 6. Entrega de sugerencias y bucle de retroalimentación

Solo las respuestas que superan los filtros se entregan al usuario.

Copilot inicia posteriormente un bucle de retroalimentación basado en las acciones del usuario para:

* Ampliar sus conocimientos a partir de sugerencias aceptadas.
* Aprender y mejorar mediante modificaciones y rechazos de sugerencias.

#### 7. Repetición para solicitudes posteriores

El proceso se repite con cada nuevo mensaje. Copilot controla continuamente las solicitudes, comprende su intención y genera código en respuesta.

Con las interacciones posteriores, aplica los datos acumulados y los detalles de contexto para mejorar la comprensión de la intención del usuario y refinar sus funcionalidades de generación de código.

## Datos de GitHub Copilot

GitHub Copilot controla los datos de acuerdo con el entorno, las características y las configuraciones utilizadas.

### Datos para sugerencias de código

GitHub Copilot en el editor de código **no conserva las solicitudes ni el código u otro contexto utilizado para proporcionar sugerencias con el objetivo de entrenar los modelos fundamentales**. Las solicitudes se descartan una vez devuelta la sugerencia.

Los suscriptores individuales de GitHub Copilot pueden optar por no compartir sus solicitudes con GitHub para el perfeccionamiento del modelo fundamental.

### Datos para el chat de GitHub Copilot

El chat de GitHub Copilot permite interacciones conversacionales con el asistente de IA.

Sus principales características son:

* **Formato:** Copilot formatea la respuesta para facilitar su visualización, resalta fragmentos de código y puede ofrecer opciones para integrarlos directamente en el código.
* **Interacción:** el usuario puede realizar preguntas de seguimiento, solicitar aclaraciones o proporcionar información adicional.
* **Historial:** la interfaz mantiene el historial de conversaciones para conservar el contexto de interacciones posteriores.
* **Retención:** para el chat de Copilot utilizado fuera del editor de código, GitHub normalmente conserva solicitudes, sugerencias y contexto auxiliar durante **28 días**. Las políticas específicas para el chat dentro del editor pueden variar.

El mismo comportamiento se aplica a **CLI, Móvil y el chat de GitHub Copilot en GitHub.com**.

## Tipos de solicitudes admitidos por el chat de GitHub Copilot

El chat puede procesar diferentes tipos de solicitudes relacionadas con programación:

* **Preguntas directas:** consultas sobre conceptos, bibliotecas o problemas de solución de errores.
* **Solicitudes relacionadas con código:** generación, modificación, corrección o explicación de código.
* **Consultas abiertas:** preguntas generales sobre conceptos, procedimientos recomendados o mejoras.
* **Solicitudes contextuales:** fragmentos de código o escenarios específicos para obtener asistencia personalizada.

Esta variedad permite utilizar Copilot como un compañero de codificación integral.

## Ventanas de contexto limitadas

La ventana de contexto determina cuánto código y texto puede procesar el modelo simultáneamente para generar sugerencias.

Según el contenido proporcionado:

* La ventana de contexto suele oscilar entre **200 y 500 líneas de código** o hasta unos miles de tokens.
* Puede variar según la implementación y versión de Copilot.
* El chat de Copilot funciona actualmente con una ventana de contexto de **4000 tokens**.

Por esta limitación, los problemas complejos pueden dividirse en consultas más pequeñas y específicas, proporcionando únicamente los fragmentos de código relevantes. Esto puede mejorar la capacidad del modelo para generar respuestas precisas y útiles.

## Modelos de lenguaje grande (LLM) de GitHub Copilot

GitHub Copilot utiliza **modelos de lenguaje grande (LLM)** para ayudar a escribir código y generar sugerencias contextualizadas.

### ¿Qué son los LLM?

Los LLM son modelos de inteligencia artificial diseñados y entrenados para comprender, generar y manipular lenguaje humano.

Sus características principales son:

* **Gran volumen de datos de entrenamiento:** se entrenan con grandes cantidades de texto de diversos orígenes, adquiriendo una amplia comprensión del lenguaje, el contexto y diferentes formas de comunicación.
* **Comprensión contextual:** generan texto coherente y relevante según el contexto disponible.
* **Aprendizaje automático e inteligencia artificial:** utilizan redes neuronales con millones o miles de millones de parámetros ajustados durante el entrenamiento para comprender y predecir texto.
* **Versatilidad:** pueden adaptarse y ajustarse para tareas especializadas y diferentes dominios e idiomas.

### Rol de los LLM en GitHub Copilot

GitHub Copilot utiliza LLM para proporcionar sugerencias de código compatibles con el contexto.

El modelo considera:

* El archivo actual.
* Otros archivos abiertos.
* Las pestañas abiertas en el IDE.

Este enfoque permite generar finalizaciones de código más precisas y pertinentes, adaptadas al contexto y mejorando la productividad.

## Ajuste de los LLM

El **ajuste preciso (fine-tuning)** permite adaptar LLM previamente entrenados a tareas o dominios específicos.

Consiste en entrenar el modelo con un conjunto de datos más pequeño y específico de una tarea, denominado **conjunto de datos de destino**, aprovechando los conocimientos y parámetros obtenidos del modelo previamente entrenado con un conjunto de datos de origen más grande.

El ajuste permite adaptar los LLM a tareas específicas y mejorar su rendimiento.

## Optimización de LoRA

El entrenamiento completo tradicional requiere ajustar todas las partes de una red neuronal, lo que puede ser lento y consumir muchos recursos.

**LoRA (Low-Rank Adaptation)** permite adaptar modelos previamente entrenados sin realizar nuevamente todo el entrenamiento.

Su funcionamiento se basa en:

* Agregar componentes entrenables más pequeños a cada capa del modelo previamente entrenado.
* Mantener sin modificar el modelo original.
* Reducir tiempo y consumo de recursos.

Según el contenido, LoRA supera a otros métodos de adaptación como adaptadores y ajuste de prefijos.

En términos sencillos, **LoRA permite mejorar los LLM para requisitos específicos de codificación trabajando con una cantidad menor de componentes entrenables y recursos**.
