# Resumen — Pruebas unitarias con GitHub Copilot

## Introducción

Las pruebas unitarias son fundamentales para garantizar la funcionalidad de los componentes individuales de un sistema.

Este módulo presenta cómo generar y mantener pruebas unitarias con **GitHub Copilot en Visual Studio Code**, utilizando:

* **Vista Copilot Chat en modo Agente**, con los modos **Preguntar (Ask)** y **Plan** para análisis y planificación.
* **Sugerencias de texto fantasma** para crear y ampliar pruebas.
* **xUnit** como marco de pruebas.
* **Visual Studio Code** y la **extensión Kit de desarrollo de C#** para hospedar y ejecutar el proyecto de pruebas.

GitHub Copilot permite acelerar la creación de pruebas unitarias, reducir errores e identificar **casos perimetrales y condiciones de límite**, especialmente en bases de código grandes donde la creación manual de pruebas puede resultar lenta.

## Temas del módulo

* Usar Visual Studio Code y el Kit de desarrollo de C# para hospedar y ejecutar pruebas unitarias.
* Generar pruebas unitarias desde la vista Copilot Chat mediante el **modo Agente**, utilizando inicialmente el **modo Preguntar** para analizar las opciones de prueba.
* Usar los agentes **Plan** y **Agent** para diseñar y automatizar flujos de trabajo de pruebas de varios archivos.
* Ampliar pruebas mediante **sugerencias de texto fantasma**.
* Corregir pruebas con errores mediante GitHub Copilot.
* Desarrollar pruebas unitarias de extremo a extremo para una aplicación de C#.

## Objetivos de aprendizaje

Al completar el módulo, podrá:

* Describir cómo **Visual Studio Code, el SDK de .NET y el Kit de desarrollo de C#** admiten pruebas unitarias en proyectos de C#.
* Usar el **modo Agente** de Copilot Chat para generar pruebas unitarias para archivos y selecciones, y el **modo Preguntar** para explorar previamente las opciones de prueba.
* Usar el agente **Plan** para diseñar una estrategia de pruebas y el agente **Agent** para automatizar flujos de trabajo de varios pasos.
* Utilizar **sugerencias de texto fantasma**, el **explorador de pruebas** y el comando `/fixTestFailure` para ampliar la cobertura y reparar pruebas con errores.
* Aplicar las funcionalidades de GitHub Copilot para simplificar el desarrollo de pruebas unitarias para una aplicación de C# en Visual Studio Code.

## Requisito importante

Para completar el entrenamiento de GitHub Copilot se necesita una **suscripción activa a GitHub Copilot**, que puede ser:

* El plan gratuito de GitHub Copilot en una cuenta personal.
* Una suscripción administrada por una organización o empresa.

Las actividades pueden generar sugerencias que coincidan con código público. En GitHub Enterprise Cloud, la configuración relacionada con estas sugerencias puede heredarse de la organización o empresa. Si la cuenta bloquea las sugerencias que coinciden con código público, las actividades del módulo podrían no funcionar según lo previsto.

## Compatibilidad de Visual Studio Code con pruebas unitarias

Para generar pruebas unitarias con GitHub Copilot, el proyecto necesita un **marco de pruebas funcional** y una forma de ejecutar las pruebas dentro de Visual Studio Code.

El entorno está compuesto por:

* **Visual Studio Code**.
* **SDK de .NET 8.0 o posterior**.
* **Extensión Kit de desarrollo de C#**.
* Un **paquete de marco de pruebas** agregado al proyecto.
* **GitHub Copilot**, encargado de generar y refinar el código de prueba.

El Kit de desarrollo de C# proporciona las funcionalidades necesarias para detectar, ejecutar, depurar y administrar pruebas unitarias.

### Funcionalidades del Kit de desarrollo de C#

* **Explorador de pruebas**: vista de árbol que muestra todos los casos de prueba del área de trabajo.
* **Ejecutar o depurar pruebas**: botones de reproducción verde junto a cada clase y método de prueba.
* **Resultados de las pruebas**: los resultados aparecen en el editor y en el Explorador de pruebas. Los enlaces de los seguimientos de pila permiten desplazarse hasta el origen del error.
* **Comandos de prueba**: comandos como `Test: Run All Tests` están disponibles en la paleta de comandos.
* **Configuración de pruebas**: permite configurar la detección de pruebas y el comportamiento durante la ejecución mediante las opciones de `Testing`.

El Kit de desarrollo de C# admite:

* **xUnit**
* **NUnit**
* **MSTest**

## Creación de proyectos de prueba

La **Paleta de comandos de Visual Studio Code** permite crear proyectos de prueba mediante:

**`.NET: Nuevo Project...`**

Se puede abrir con:

* **Ctrl + Shift + P** en Windows/Linux.
* **Cmd + Shift + P** en macOS.
* Menú **Vista → Paleta de comandos**.
* Desde el Explorador de soluciones, haciendo clic derecho en la carpeta de la solución y seleccionando **Nuevo proyecto**.

### xUnit

Seleccionar **xUnit Test Project**. El proyecto agrega:

* `Microsoft.NET.Test.Sdk`
* `xUnit`
* `xunit.runner.visualstudio`
* `coverlet.collector`

Para agregar una referencia desde el proyecto de prueba al proyecto que se está probando:

```bash
dotnet add [location of your test csproj file] reference [location of the csproj file for project to be tested]
```

### NUnit

Seleccionar **NUnit3 Test Project**. El proyecto agrega:

* `Microsoft.NET.Test.Sdk`
* `NUnit`
* `NUnit3TestAdapter`

Para agregar la referencia al proyecto en prueba:

```bash
dotnet add [location of your test csproj file] reference [location of the csproj file for project to be tested]
```

### MSTest

Seleccionar **MSTest Test Project**. El proyecto agrega:

* `Microsoft.NET.Test.Sdk`
* `MSTest.TestAdapter`
* `MSTest.TestFramework`
* `coverlet.collector`

Para agregar la referencia al proyecto en prueba:

```bash
dotnet add [location of your test csproj file] reference [location of the csproj file for project to be tested]
```

## Ejecución y administración de pruebas

Una vez creado el proyecto de pruebas, Visual Studio Code y el Kit de desarrollo de C# permiten:

* **Ejecutar o depurar desde el editor** mediante el botón de reproducción junto a una clase o método.
* **Usar el Explorador de pruebas** para ejecutar o depurar pruebas individuales, grupos o todo el conjunto.
* **Consultar resultados**, incluidos estados de aprobación, errores y duración.
* **Usar comandos de prueba**, como:

  * `Test: Run All Tests`
  * `Test: Debug Failed Tests`
  * `Test: Show Output`
* **Configurar las pruebas** mediante las opciones `Testing`, incluyendo la ejecución automática al guardar y el formato de los resultados.

## Flujo de trabajo de pruebas unitarias con GitHub Copilot

El proceso se divide en tres fases:

1. **Configurar el entorno**: usar Visual Studio Code, el SDK de .NET y el Kit de desarrollo de C# para crear el proyecto de pruebas y referenciar el proyecto en prueba.
2. **Generar código de prueba**: usar GitHub Copilot en la vista Chat para generar pruebas unitarias para el código de la aplicación.
3. **Ejecutar y mantener las pruebas**: usar el Explorador de pruebas y el Kit de desarrollo de C# para ejecutar las pruebas, y GitHub Copilot para ampliar la cobertura y corregir las pruebas con errores.

Las unidades restantes se centran en las herramientas de GitHub Copilot que permiten realizar las fases de **generación, ejecución y mantenimiento de pruebas**.

## Generación de pruebas unitarias con Copilot Chat

La **vista Chat de Visual Studio Code** es el lugar principal para generar pruebas unitarias con GitHub Copilot. Permite:

* Configurar un marco de pruebas.
* Generar pruebas para un archivo o selección.
* Refinar las pruebas según las convenciones del proyecto.
* Ejecutar las pruebas generadas e iterar sobre los errores desde una misma sesión.

### Abrir la vista Chat

Se puede abrir mediante:

* **Ctrl + Alt + I** en Windows/Linux.
* **Cmd + Alt + I** en macOS.
* Icono de GitHub Copilot → **Toggle Chat**.

La vista Chat ofrece tres configuraciones:

* **Destino del agente**: determina dónde se ejecuta el agente. `Local` permite trabajar interactivamente en el editor con acceso al área de trabajo, herramientas y modelos.
* **Agente**: define el rol de la IA. Los agentes locales integrados son **Ask**, **Plan** y **Agent**.
* **Nivel de permiso**: controla la autonomía para invocar herramientas y comandos de terminal:

  * **Aprobaciones predeterminadas**
  * **Omisión de aprobaciones**
  * **Autopilot**

Para generar pruebas unitarias se recomienda **Agente + aprobaciones predeterminadas**, ya que el Agente puede editar archivos, ejecutar comandos de terminal y volver a ejecutar pruebas, mientras las aprobaciones mantienen al usuario informado de cada invocación de herramienta.

### Modo Preguntar

El modo **Preguntar** permite analizar y planificar sin modificar archivos ni invocar herramientas.

Es útil para:

* Comparar casos de prueba para métodos complejos.
* Identificar casos perimetrales y condiciones de límite.
* Obtener recomendaciones sobre marcos de pruebas o estilos de aserción.
* Ver ejemplos de pruebas sin escribirlos en disco.

Flujo:

1. Abrir la vista Chat y seleccionar **Preguntar**.
2. Adjuntar el archivo o selección relevante.
3. Realizar una pregunta de análisis.
4. Revisar la respuesta y cambiar a **Agente** para generar las pruebas.

### Configuración con `/setupTests`

El comando `/setupTests` permite configurar un marco de pruebas cuando el proyecto todavía no lo tiene.

El modo Agente puede:

* Recomendar un marco.
* Instalar paquetes.
* Crear el proyecto de pruebas.
* Recomendar extensiones de pruebas para Visual Studio Code.

Flujo:

1. Abrir la vista Chat y seleccionar **Agente**.
2. Ejecutar `/setupTests`.
3. Confirmar las herramientas y comandos de terminal propuestos.

Es especialmente útil para proyectos nuevos o proyectos que todavía no incluyen pruebas.

### Generación con `/tests`

El comando `/tests` genera pruebas unitarias para el código activo en el editor.

En modo Agente, las pruebas se escriben directamente en un archivo de prueba adecuado. GitHub Copilot detecta el marco existente y el estilo de codificación del proyecto.

Para un archivo completo:

1. Abrir el archivo de código.
2. Abrir Copilot Chat y seleccionar **Agente**.
3. Ejecutar `/tests` con instrucciones adicionales.
4. Confirmar las herramientas utilizadas para leer el contexto, escribir y ejecutar pruebas.
5. Revisar los cambios.
6. Seleccionar **Mantener** o **Deshacer**.

El Agente agrega las pruebas a un archivo existente cuando corresponde o crea uno nuevo en la ubicación adecuada.

Para un método o bloque específico:

1. Abrir el archivo.
2. Seleccionar el método o bloque.
3. Ejecutar `/tests` indicando que se utilice la selección.
4. Revisar y mantener o descartar los cambios.

### Generación mediante lenguaje natural

No es obligatorio utilizar comandos de barra diagonal. El Agente puede generar pruebas mediante instrucciones de lenguaje natural con suficiente contexto.

Ejemplos:

* Generar pruebas xUnit para los métodos de un archivo y agregarlas al proyecto correspondiente.
* Crear pruebas unitarias para `CalculateDiscount`, incluyendo casos límite para valores negativos y cero.
* Crear pruebas de integración para una capa de acceso a datos.

También se pueden incluir pasos de verificación en el mismo mensaje, como solicitar que el Agente ejecute las pruebas después de generarlas para detectar y corregir errores.

## Agregar contexto a las indicaciones

La calidad de las pruebas generadas depende del contexto proporcionado. Se puede agregar mediante:

* **Agregar contexto**: archivos, carpetas, símbolos o selección actual.
* **Arrastrar y colocar** archivos desde el Explorador o pestañas del editor hacia Chat.
* **Menciones `#`**:

  * `#selection`: selección actual.
  * `#codebase`: permite buscar contexto relevante en el área de trabajo.
  * También se pueden mencionar archivos, carpetas o símbolos.
* **Archivos externos**: archivos Markdown con directrices o convenciones de prueba pueden adjuntarse como contexto.

Esto permite indicar explícitamente qué código debe analizar Copilot y qué convenciones debe seguir.

## Revisar y refinar los cambios

Aunque el Agente modifica directamente el proyecto, el usuario mantiene el control:

* **Revisar la diferencia**: los cambios aparecen resaltados en el editor.
* **Mantener o deshacer** los cambios.
* **Compilar y ejecutar** las pruebas desde el Explorador de pruebas o el terminal.
* **Iterar** mediante mensajes posteriores para agregar casos, refinar pruebas o cambiar nombres.

## Personalización de la generación de pruebas

Las **instrucciones personalizadas** permiten adaptar las pruebas generadas a los estándares del proyecto u organización.

Se pueden definir:

* Marcos de pruebas preferidos, como xUnit o NUnit.
* Convenciones de nombres para clases y métodos.
* Estructuras como **Arrange-Act-Assert**.
* Patrones específicos, como pruebas parametrizadas para valores límite.

Las instrucciones se almacenan en archivos `*.instructions.md` y pueden utilizar el campo `applyTo` para limitar su aplicación. Por ejemplo:

```text
applyTo: tests/**
```

limita las instrucciones a los archivos del directorio `tests/`.

Compartir estas instrucciones mediante el control de código fuente permite que todo el equipo utilice el mismo contexto de pruebas.

## Planeamiento y automatización con Plan y Agent

Las tareas de prueba más grandes pueden requerir decidir qué probar, preparar un proyecto de pruebas, generar pruebas en varios archivos y ejecutar el conjunto resultante. Para estos escenarios se utilizan los agentes **Plan** y **Agent**.

El flujo recomendado es:

1. Usar **Plan** para diseñar una estrategia de pruebas antes de escribir código.
2. Revisar y refinar el plan.
3. Entregar el plan aprobado a **Agent** para implementar el trabajo de forma autónoma y en varios pasos.

### Comparación de agentes

| Agente              | Adecuado para                                        | Uso típico en pruebas unitarias                                                      |
| ------------------- | ---------------------------------------------------- | ------------------------------------------------------------------------------------ |
| **Preguntar (Ask)** | Análisis de solo lectura y preguntas sobre el código | Explorar casos perimetrales, opciones de marco y ejemplos antes de escribir código.  |
| **Plan**            | Planes de implementación estructurados               | Diseñar estrategias de pruebas de varios archivos para revisar antes de implementar. |
| **Agent**           | Flujos autónomos y codificación de varios archivos   | Generar pruebas, ejecutarlas y corregir errores mediante iteraciones.                |

Los agentes se seleccionan desde el selector de agentes de la vista Chat y pueden cambiarse durante una sesión.

### Solicitudes Premium

Al utilizar el modo **Agent**, GitHub Copilot puede realizar varias **solicitudes Premium** para completar una sola tarea. Estas solicitudes se utilizan tanto para las indicaciones iniciadas por el usuario como para las acciones posteriores realizadas por el agente.

El total depende de:

* Complejidad de la tarea.
* Cantidad de pasos.
* Modelo seleccionado.

### Uso de Plan para diseñar una estrategia

El agente **Plan** genera un plan detallado antes de escribir código. Investiga la tarea, puede formular preguntas aclaratorias y propone un plan paso a paso.

Proceso:

1. Abrir los archivos que contienen el código que se desea probar.
2. Abrir Chat y seleccionar **Plan** o utilizar `/plan`.
3. Describir las pruebas necesarias, incluyendo marco, casos y ubicación.
4. Responder las preguntas aclaratorias.
5. Revisar y refinar el plan.
6. Enviar el plan para su implementación.

El plan normalmente incluye:

* Resumen de alto nivel.
* Desglose de pasos.
* Pasos de comprobación para ejecutar las pruebas.
* Decisiones documentadas.

La implementación puede realizarse en la misma sesión, en segundo plano o en la nube. También es posible abrir el plan en el editor para revisarlo.

Plan es especialmente útil cuando:

* La tarea abarca varios archivos.
* Se necesitan nuevas clases de prueba o accesorios.
* Existen convenciones de equipo que deben respetarse.

### Uso de Agent para automatizar pruebas

El agente **Agent** automatiza tareas de varios pasos en todo el espacio de trabajo. Puede:

* Preparar mediante scaffolding un proyecto de pruebas.
* Crear archivos de prueba.
* Ejecutar las pruebas.
* Generar informes.
* Corregir problemas encontrados durante la ejecución.

Proceso:

1. Abrir el archivo que contiene el código a probar.
2. Abrir Chat y seleccionar **Agent**.
3. Permitir que GitHub Copilot determine el contexto o agregarlo manualmente.
4. Seleccionar, si es necesario, las herramientas disponibles para el agente.
5. Definir la tarea mediante un mensaje.
6. Supervisar el trabajo del agente.
7. Confirmar o rechazar invocaciones de herramientas y comandos de terminal.
8. Revisar los archivos creados o modificados.
9. Mantener o descartar los cambios.
10. Utilizar mensajes de seguimiento para refinar las pruebas.

Entre las herramientas útiles se encuentran las de edición de archivos, terminal para ejecutar `dotnet test` y las herramientas de prueba proporcionadas por la extensión.

### Cuándo usar Plan, Agent o ambos

* **Plan primero**: cuando existe ambigüedad, múltiples archivos o convenciones que deben confirmarse. El plan funciona como un contrato revisable antes de escribir código.
* **Agent directamente**: cuando la tarea está bien definida y se desea que Copilot cree la estructura, genere y ejecute las pruebas sin planificación intermedia.
* **Plan → Agent**: cuando se necesita un plan revisable junto con una implementación autónoma. Esta combinación proporciona mayor control sobre el alcance mientras automatiza el trabajo.

## Extensión de pruebas con texto fantasma y corrección de errores

Una vez que el proyecto contiene algunos casos de prueba, GitHub Copilot permite **ampliar la cobertura y resolver errores** directamente desde Visual Studio Code.

Las principales herramientas son:

* **Texto fantasma** para agregar casos de prueba adicionales.
* **Explorador de pruebas** para diagnosticar errores.
* **`/fixTestFailure`** para corregir pruebas con errores.
* **Agent** para ejecutar pruebas, diagnosticar errores y aplicar correcciones automáticamente.

### Ampliar cobertura con texto fantasma

El **texto fantasma** es una finalización de código que aparece mientras se escribe. Copilot utiliza los patrones existentes del archivo de pruebas para sugerir casos adicionales.

Proceso:

1. Abrir un archivo de prueba con al menos uno o dos casos completos.
2. Colocar el cursor al final del último caso y presionar **Enter**.
3. Comenzar un nuevo método de prueba o escribir un comentario que describa el escenario.
4. Revisar la sugerencia generada.
5. Presionar **Tab** para aceptarla o **Esc** para descartarla.
6. Refinar la prueba o generar otra sugerencia.

Funciona mejor cuando:

* El archivo ya contiene el patrón que se desea seguir, como **Arrange-Act-Assert** o atributos de prueba parametrizados.
* El método probado está referenciado mediante una directiva `using` o espacio de nombres.
* El comentario describe claramente el escenario.

El texto fantasma es adecuado para agregar rápidamente casos perimetrales a una clase existente. Para crear una clase de prueba completamente nueva o realizar trabajos más importantes, se recomienda utilizar **Ask, Plan o Agent** desde la vista Chat.

### Corregir errores desde el Explorador de pruebas

El Explorador de pruebas proporciona un acceso directo para corregir una prueba con errores:

1. Ejecutar las pruebas.
2. En el Explorador de pruebas, colocar el puntero sobre una prueba con error.
3. Seleccionar **Corregir error de prueba**.
4. GitHub Copilot abre una sesión de Chat con la prueba y su salida como contexto.
5. Revisar la corrección propuesta.
6. **Conservar** o **Deshacer** los cambios.
7. Volver a ejecutar la prueba para confirmar la corrección.

La corrección puede afectar al código de la aplicación, al código de prueba o a ambos.

### Corrección mediante `/fixTestFailure`

El comando `/fixTestFailure` permite iniciar el proceso desde la vista Chat.

Proceso:

1. Abrir la vista Chat.
2. Ejecutar `/fixTestFailure`.
3. Opcionalmente, adjuntar archivos relacionados o salida reciente del terminal.
4. Seguir las sugerencias de GitHub Copilot.
5. Volver a ejecutar la prueba para confirmar la corrección.

Es especialmente útil cuando se necesita contexto adicional o se trabaja con varias pruebas con errores.

### Corrección automática mediante Agent

Cuando **Agent** ejecuta pruebas, puede supervisar los resultados, identificar errores, intentar corregirlos y volver a ejecutar las pruebas.

Para el mantenimiento automático:

1. Abrir Chat y seleccionar **Agent**.
2. Solicitar la ejecución de las pruebas e indicar que se corrijan los errores y se vuelvan a ejecutar.
3. Confirmar o rechazar las herramientas y comandos de terminal propuestos.
4. Revisar los cambios antes de aceptarlos.

Esto resulta útil al crear estructuras iniciales de pruebas o realizar cambios importantes que afectan a muchas pruebas.

### Elección de la herramienta

| Herramienta                                    | Uso recomendado                                                                                      |
| ---------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| **Texto fantasma**                             | Agregar casos a un archivo de pruebas existente que ya contiene el patrón deseado.                   |
| **Corregir error en el Explorador de pruebas** | Corregir rápidamente una única prueba con errores.                                                   |
| **`/fixTestFailure`**                          | Adjuntar contexto adicional o resolver varios fallos desde Chat.                                     |
| **Agent**                                      | Ejecutar pruebas, diagnosticar errores y aplicar correcciones en varios archivos durante una sesión. |

Estas herramientas completan el flujo de trabajo de pruebas unitarias: **Chat, Plan y Agent** permiten generar las pruebas iniciales; el **texto fantasma** amplía la cobertura y las herramientas de corrección mantienen el conjunto de pruebas funcionando a medida que evoluciona el código.

## Importante

Las pruebas generadas pueden no cubrir todos los escenarios. La **revisión manual y la revisión de código siguen siendo necesarias** para garantizar la calidad de las pruebas.
