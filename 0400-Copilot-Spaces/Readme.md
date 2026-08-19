# GitHub Copilot Spaces

## Introducción

GitHub Copilot Spaces proporciona una forma de trabajar con inteligencia artificial anclando sus respuestas en un contexto cuidadosamente mantenido. A diferencia del chat general de Copilot, que ofrece sugerencias más amplias, un espacio permite centrar el modelo en archivos específicos, problemas, solicitudes de incorporación de cambios e instrucciones adaptadas.

Un espacio permite restringir el contexto para obtener respuestas más coherentes, precisas, fundamentadas y reproducibles.

### Conceptos principales

* Qué son los espacios de Copilot y cómo se diferencian del chat general.
* Cómo un contexto bien delimitado mejora la calidad y coherencia de las respuestas.
* Cómo agregar archivos, problemas, solicitudes de incorporación de cambios e instrucciones.
* Cuándo utilizar un espacio para tareas específicas, repetibles y de dominio determinado.

## ¿Qué es un espacio de Copilot (Copilot Spaces)?

Es un chat de Copilot dedicado y fundamentado en un conjunto seleccionado de contextos.

Un espacio puede utilizar:

* Archivos de GitHub.
* Problemas.
* Solicitudes de incorporación de cambios.
* Instrucciones de texto libre.

Estos elementos proporcionan el contexto necesario para que Copilot trabaje sobre un tema específico.

## Configuración del contexto

La eficacia de un espacio depende del contexto proporcionado. Es posible adjuntar archivos específicos, problemas, solicitudes de incorporación de cambios e instrucciones adaptadas.

La selección y el orden del contexto son importantes: conviene comenzar con los archivos o instrucciones más relevantes para favorecer respuestas precisas.

### Adjuntar archivos

Desde la configuración del espacio, mediante **"Adjuntar archivos"** o **"Agregar contexto"**, se pueden seleccionar archivos o carpetas de un repositorio de GitHub.

Se pueden utilizar:

* Archivos de código fuente.
* Documentación Markdown.
* Archivos de configuración.
* Otros recursos relevantes.

Los archivos vinculados desde GitHub se referencian desde la rama predeterminada, por lo que el espacio se mantiene actualizado a medida que evoluciona el repositorio.

Cuando la configuración lo permite, también se pueden cargar archivos directamente desde la máquina local, como:

* Imágenes.
* Conjuntos de datos.
* Archivos de texto.
* Documentos enriquecidos.
* Hojas de cálculo.

### Agregar instrucciones

La sección **"Instrucciones"** permite indicar a Copilot qué debe considerar dentro del espacio.

Las instrucciones pueden definir:

* Objetivos, por ejemplo, resumir un proceso de incorporación.
* Preferencias de estilo, como utilizar un tono formal.
* Ejemplos canónicos que indiquen cómo debería ser la salida.
* Áreas de experiencia.
* Tipos de tareas en las que debe ayudar.
* Aspectos que debe evitar.
* Tareas paso a paso o mensajes de ejemplo para flujos de trabajo y solución de problemas.

Las instrucciones deben ser breves, claras, centradas y accionables. Se pueden actualizar en cualquier momento para refinar el comportamiento del espacio.

## ¿Cuándo utilizar un Espacio?

Un espacio resulta adecuado cuando se necesitan respuestas coherentes y reproducibles sobre un tema de ámbito estricto, por ejemplo:

* Un servicio determinado.
* Un runbook.
* Un cuaderno de estrategias.
* Un conjunto de datos conocido.
* Un flujo de trabajo específico.

En comparación con el chat general o con un contexto de todo el repositorio, Spaces intercambia amplitud por profundidad. Al restringir el contexto a la información más relevante, las respuestas tienden a ser más predecibles y fundamentadas, mientras que un chat amplio puede ofrecer una detección más extensa pero ser menos preciso.

### Buenas prácticas

* Mantener los espacios pequeños y enfocados debido a los límites de contexto del modelo.
* Utilizar archivos vinculados de la rama predeterminada para mantener el contenido actualizado.
* Redactar instrucciones claras y concisas.
* Incluir ejemplos canónicos para delimitar el estilo y las salidas esperadas.
* Seleccionar y ordenar el contexto comenzando por las fuentes más importantes.

# Creando tu primer espacio

Crear un espacio es sencillo. Una vez configurado y nombrado, se convierte en un área de trabajo reutilizable donde Copilot opera dentro de un ámbito claramente definido.

### Objetivos

* Crear un espacio y asignarle un nombre claro.
* Comprender la diferencia entre espacios personales y espacios propiedad de una organización.
* Agregar y estructurar contexto mediante datos adjuntos e instrucciones.
* Comprender cómo la organización y la claridad mejoran las respuestas de Copilot.

## Creación de un espacio

1. Ir a [https://github.com/copilot/spaces](https://github.com/copilot/spaces) y seleccionar **Crear espacio**.
2. Asignar un nombre al espacio.
3. Elegir si el espacio será propiedad personal o de una organización.

   * Los espacios propiedad de una organización pueden compartirse mediante el modelo de permisos integrado de GitHub.
4. Opcionalmente, agregar una descripción.

   * La descripción no afecta las respuestas de Copilot.
   * Puede ayudar a otros usuarios a comprender el contexto del espacio.
5. Seleccionar **Guardar**.

El nombre y la descripción pueden modificarse posteriormente mediante **Editar**.

## Agregar contexto a un espacio

Existen dos tipos principales de contexto:

### Instrucciones

Texto libre que describe en qué debe centrarse Copilot dentro del espacio. Permite especificar áreas de experiencia, tipos de tareas, objetivos y aspectos que debe evitar.

### Datos adjuntos

Permiten proporcionar información adicional para obtener respuestas más relevantes. Spaces también hace referencia a la versión más reciente del código en la rama principal del repositorio.

Para agregar datos adjuntos, seleccionar **Agregar** junto a **Datos adjuntos** y utilizar una de las siguientes opciones:

* **Adjuntar archivos y carpetas:** permite agregar archivos y carpetas de repositorios de GitHub, incluidos código, documentación y otro contenido relevante.
* **Vincular solicitudes de incorporación de cambios y problemas:** permite pegar las direcciones URL de problemas y solicitudes de incorporación de cambios de GitHub.
* **Cargar un archivo:** permite cargar archivos desde la máquina local, incluyendo imágenes, archivos de texto, documentos enriquecidos y hojas de cálculo.
* **Agregar contenido de texto:** permite escribir o pegar texto libre, como transcripciones, notas u otra información relevante.

Con estas opciones se puede construir un espacio con un contexto específico y reutilizable para que Copilot proporcione respuestas más precisas y fundamentadas.

# Uso compartido, detectabilidad y gobernanza

Para que un espacio ofrezca valor duradero debe ser fácil de encontrar, seguro para compartir y mantenerse actualizado. La administración incluye definir la visibilidad, respetar los permisos de GitHub, mantener el contenido actualizado y establecer una gobernanza ligera.

### Objetivos

* Administrar la visibilidad y el uso compartido dentro de la organización.
* Mantener los permisos de GitHub y controlar el acceso al contenido vinculado.
* Mejorar la detectabilidad mediante convenciones de nomenclatura y descripciones.
* Establecer procedimientos para la propiedad, actualización y revisión del espacio.

## Visibilidad y uso compartido

Los espacios deben ser fáciles de encontrar, seguros para compartir y tener una propiedad claramente definida.

Al crear un espacio:

* Establecer la visibilidad según la amplitud con la que se utilizará.
* Mantenerlo bajo propiedad personal o hacerlo visible para la organización, según corresponda.
* Compartirlo mediante vínculo.
* Utilizar la exploración de nivel de organización o catálogos cuando estén disponibles.
* Utilizar un título claro y orientado al propósito.
* Mantener el principio de **"un trabajo por espacio"**.
* Incluir una descripción breve que indique el ámbito, la audiencia prevista y las salidas esperadas.

## Seguridad y acceso

La seguridad sigue los permisos existentes de GitHub. Un espacio no concede acceso nuevo: solo expone contenido que los usuarios ya tienen derecho a ver.

Si un espacio vincula:

* Repositorios privados.
* Problemas.
* Solicitudes de incorporación de cambios.

Solo los usuarios con los permisos adecuados pueden ver ese material reflejado en las respuestas.

Como práctica recomendada:

* Evitar pegar datos confidenciales en notas de texto libre.
* Preferir archivos controlados por versiones, donde se aplican las revisiones y permisos normales.
* Asegurar que los orígenes adjuntos sean adecuados para la visibilidad seleccionada.

## Versionado y actualización

Los espacios permanecen actualizados al utilizar orígenes de GitHub en directo.

* Los archivos vinculados reflejan la rama predeterminada del repositorio.
* Los problemas y solicitudes de incorporación de cambios adjuntos evolucionan a medida que cambian.
* Esto reduce la necesidad de copiar contenido en documentos independientes.

Cuando se necesiten instrucciones específicas de una rama o una instantánea histórica, se puede:

* Restringir las referencias a los archivos pertinentes.
* Agregar un ejemplo breve en texto libre.
* Adjuntar, si el entorno lo permite, un archivo de texto con el contenido exacto que debe utilizar el espacio.

Es recomendable mantener el ámbito pequeño para que las actualizaciones sean predecibles y fundamentadas.

## Gobernanza

La gobernanza debe ser ligera pero intencionada.

Buenas prácticas:

* Asignar un propietario responsable del mantenimiento del espacio.
* Agregar una nota **"Cómo usar este Espacio"** al comienzo de las instrucciones.
* Incluir entre 1 y 3 ejemplos canónicos que definan una salida adecuada.
* Establecer convenciones de nomenclatura, por ejemplo, **"ServiceName—Onboarding Helper"**.
* Definir una cadencia de revisión, como cada versión.
* Eliminar fuentes obsoletas.
* Mantener las instrucciones alineadas con la realidad.
* Dividir un espacio en espacios más pequeños cuando abarque más de un trabajo.

## Lista de comprobación

### Nomenclatura y propósito

* [ ] Elegir un título claro y orientado a un propósito, manteniendo **"un trabajo por espacio"**.
* [ ] Escribir una descripción de 1 a 2 oraciones que indique el ámbito, la audiencia prevista y las salidas esperadas.
* [ ] Agregar una breve nota sobre cómo usar el espacio al comienzo de las instrucciones.

### Propiedad y visibilidad

* [ ] Establecer el propietario correcto, individual u organización si está disponible.
* [ ] Seleccionar la visibilidad adecuada.
* [ ] Verificar el acceso con un usuario que no sea propietario y que tenga los permisos de GitHub esperados.
* [ ] Compartir la dirección URL y agregar colaboradores cuando esté disponible.

### Seguridad y privacidad

* [ ] No pegar datos confidenciales en texto libre; preferir archivos controlados por versiones.
* [ ] Verificar que todos los orígenes adjuntos sean adecuados para la visibilidad elegida.
* [ ] Si se admiten cargas, limitar el contenido de texto que resulte apropiado compartir.
* [ ] Eliminar materiales obsoletos o confidenciales.

### Detectabilidad y documentación

* [ ] Utilizar convenciones de nomenclatura coherentes.
* [ ] Incorporar etiquetas o palabras clave en la descripción para facilitar la búsqueda.
* [ ] Anunciar o catalogar el espacio en el directorio o canal preferido de la organización.

### Revisión y gobernanza

* [ ] Asignar un mantenedor o propietario responsable de las actualizaciones.
* [ ] Establecer una cadencia de revisión, por ejemplo, mensual o por versión.
* [ ] En cada revisión:

  * [ ] Validar los vínculos.
  * [ ] Probar 2–3 indicaciones representativas.
  * [ ] Actualizar los ejemplos.
  * [ ] Recortar fuentes ruidosas.
  * [ ] Confirmar la visibilidad.
* [ ] Realizar un seguimiento de comentarios y solicitudes de mejora mediante problemas, discusiones o una lista de comprobación sencilla en la descripción.

# Lo que debes y no debes hacer al trabajar en un espacio

## Recomendaciones de uso

* Mantener las preguntas estrechamente relacionadas con los orígenes adjuntos: archivos, problemas, solicitudes de incorporación de cambios y notas.
* Tratar el espacio como un entorno centrado en una sola tarea o dominio.
* Utilizar terminología propia y consistente para reforzar la coherencia.
* Utilizar patrones de solicitud que produzcan salidas ejecutables y verificables.
* Comenzar confirmando la intención y luego agregar restricciones concretas, como formatos, intervalos de tiempo, rutas de archivos o secciones relevantes.
* Solicitar código ejecutable, consultas o comandos.
* Cuando sea útil, solicitar referencias a los orígenes incluidos para facilitar la rastreabilidad.
* Iterar cuando las respuestas se desvíen, ajustando instrucciones, agregando entre uno y tres ejemplos de alta calidad y eliminando orígenes irrelevantes o ruidosos.
* Mantener el contexto actualizado y bien ordenado.
* Vincular archivos controlados por versiones para que el espacio refleje la rama predeterminada a medida que evoluciona.
* Colocar primero los orígenes y ejemplos más importantes, ya que el orden puede influir en las respuestas.

## Lo que no debes hacer

* No mencionar personas ni otras extensiones de Copilot dentro de un espacio. Las menciones de usuarios no notifican a nadie y las extensiones no pueden invocarse desde chats de espacio.
* No esperar que Copilot extraiga contenido que no esté incluido en el espacio. Salvo que el entorno admita la búsqueda en un repositorio asociado explícitamente, Copilot no descubrirá material externo.
* No permitir que el espacio se expanda más allá de una sola tarea.
* No superar los límites de contexto del modelo. Si aparecen advertencias de tamaño o disminuye la calidad de las respuestas, reducir los orígenes o dividir el contenido en espacios más pequeños.
* No pegar datos confidenciales en notas de texto libre. Preferir archivos de repositorios o cargas cuando estén permitidas, para mantener los permisos y las revisiones estándares.


