# GitHub Copilot: administración, seguridad, exclusiones y solución de problemas

## Introducción

GitHub busca impulsar una IA segura y fiable, aprovechando la IA para mejorar la eficiencia y la innovación durante todo el ciclo de vida del desarrollo de software.

Este módulo aborda:

* Planes de GitHub Copilot y sus funciones de administración y personalización.
* Protecciones contractuales y deshabilitación del código público coincidente.
* Administración de exclusiones de contenido.
* Problemas comunes y soluciones de GitHub Copilot.

## Planes de GitHub Copilot y controles de privacidad

GitHub Copilot ofrece distintos planes para responder a las necesidades de desarrolladores y organizaciones, priorizando seguridad, privacidad, cumplimiento y transparencia.

### Características de administración

| Característica                                            | Gratis/Pro | Business | Enterprise |
| --------------------------------------------------------- | ---------: | -------: | ---------: |
| Filtro de código público                                  |          ✅ |        ✅ |          ✅ |
| Administración de usuarios                                |          ❌ |        ✅ |          ✅ |
| Datos excluidos del entrenamiento de forma predeterminada |          ❌ |        ✅ |          ✅ |
| Seguridad de clase empresarial                            |          ❌ |        ✅ |          ✅ |
| Indemnización de propiedad intelectual                    |          ❌ |        ✅ |          ✅ |
| Exclusiones de contenido                                  |          ❌ |        ✅ |          ✅ |
| Autenticación SAML de inicio de sesión único              |          ❌ |        ✅ |          ✅ |
| Requiere GitHub Enterprise Cloud                          |          ❌ |        ❌ |          ✅ |
| Métricas de uso                                           |          ❌ |        ✅ |          ✅ |

*GitHub Copilot Gratis tiene limitaciones de uso.*

### Características de personalización

| Característica                                                        | Gratis/Pro | Business | Enterprise |
| --------------------------------------------------------------------- | ---------: | -------: | ---------: |
| Adaptar conversaciones al código base privado                         |          ❌ |        ❌ |          ✅ |
| Integraciones ilimitadas con extensiones de Copilot (beta pública)    |          ✅ |        ✅ |          ✅ |
| Crear una extensión privada para herramientas internas (beta pública) |          ✅ |        ✅ |          ✅ |
| Adjuntar bases de conocimiento al chat para contexto organizativo     |          ❌ |        ❌ |          ✅ |

### Factores para seleccionar un plan

* **Privacidad y seguridad:** Business y Enterprise ofrecen controles más sólidos, como exclusiones de archivos, registros de auditoría e indemnización por IP.
* **Administración de directivas:** Business y Enterprise permiten administrar las directivas de Copilot a nivel organizativo.
* **Recopilación y retención de datos:** los suscriptores individuales pueden elegir si GitHub recopila y conserva sus indicaciones y sugerencias de Copilot.
* **Privacidad e indemnización por IP:** son factores importantes para empresas que necesitan reducir riesgos legales, de seguridad y relacionados con clientes.

### GitHub Copilot Gratis

GitHub Copilot ofrece un nivel gratuito con:

* 2000 autocompletados de código al mes.
* 50 mensajes de chat al mes.

Los educadores, estudiantes y determinados mantenedores de código abierto pueden recibir Copilot Pro de forma gratuita.

## Protecciones contractuales y código público coincidente

### Protecciones contractuales

GitHub Copilot ofrece:

* **Indemnización por IP:** Business y Enterprise incluyen protección jurídica frente a reclamaciones de propiedad intelectual relacionadas con sugerencias de Copilot. Para que GitHub asuma esta responsabilidad, debe estar bloqueada la configuración de **código público coincidente**.
* **Acuerdo de protección de datos (DPA):** describe las medidas utilizadas para proteger los datos y cumplir las normativas de privacidad.
* **Centro de confianza de GitHub Copilot:** proporciona información sobre seguridad, privacidad, cumplimiento y propiedad intelectual de Copilot.

### Filtrado del código público coincidente

GitHub Copilot puede identificar y filtrar sugerencias que coincidan con código disponible públicamente, reduciendo el riesgo de incorporar código no seguro o no conforme.

| Ámbito                                              | Quién administra                           | Qué controla                                                                             |
| --------------------------------------------------- | ------------------------------------------ | ---------------------------------------------------------------------------------------- |
| Organización Business/Enterprise                    | Administradores                            | Filtro de código público para todos los miembros; necesario para la indemnización por IP |
| Cuenta personal Gratis/Pro/Pro+ con pago individual | Usuario                                    | Permitir o bloquear sugerencias coincidentes con código público                          |
| Cuenta personal proporcionada por una organización  | Usuario, sujeto a la política organizativa | La opción puede estar bloqueada y reflejar la política de la organización                |

### Administración del filtro de código público en una organización

Para organizaciones Business o Enterprise:

1. Ir a **Configuración** de la empresa u organización.
2. Seleccionar **Copilot** en **Código, planificación y automatización**.
3. Entrar en **Características** y desplazarse hasta **Privacidad**.
4. Buscar **Sugerencias que coincidan con el código público**.
5. Elegir la configuración, por ejemplo **Bloquear**.
6. Guardar los cambios.

### Administración para cuentas personales

Los titulares de licencias personales Gratis, Pro o Pro+ pueden:

1. Ir a **Configuración**.
2. Seleccionar **Copilot** en **Código, planificación y automatización**.
3. Entrar en **Características** y luego en **Privacidad**.
4. Buscar **Sugerencias que coincidan con el código público**.
5. Elegir **Permitir** o **Bloquear**.

## Exclusiones de contenido

La exclusión de contenido de GitHub Copilot permite proteger información confidencial evitando que determinados archivos, directorios o repositorios informen las sugerencias de finalización de código.

### Configuración en repositorios

1. Ir a la página principal del repositorio.
2. Seleccionar **Configuración**.
3. En **Código y automatización**, seleccionar **Copilot**.
4. En **Repositorios y rutas de acceso para excluir**, especificar los archivos o directorios.

### Configuración en organizaciones

1. Ir a **Configuración** de la organización.
2. Seleccionar **Copilot → Exclusión de contenido**.
3. Especificar los archivos o repositorios que se deben excluir.

### Impacto de las exclusiones

Cuando se excluye contenido:

* La finalización de código deja de estar disponible en los archivos afectados.
* El contenido excluido no informa las sugerencias de finalización en otros archivos.
* El contenido excluido no informa las respuestas del Chat de GitHub Copilot.

Las exclusiones pueden mejorar la seguridad y el cumplimiento, pero también reducir el contexto disponible y afectar la precisión y utilidad de las sugerencias.

Las exclusiones configuradas en una organización o repositorio dentro de una empresa se aplican a los miembros con licencia de GitHub Copilot Business o Enterprise.

### Limitaciones

* **Limitaciones del IDE:** en algunos IDE, determinadas funciones, como el participante de chat `@github` en Visual Studio Code y Visual Studio, pueden no respetar las exclusiones.
* **Información semántica:** Copilot podría utilizar información semántica de un archivo excluido si el IDE la proporciona desde un archivo no excluido, como tipos, definiciones de símbolos o llamadas a funciones.
* **Ámbito de la directiva:** la exclusión solo se aplica a miembros de la organización donde fue configurada. Otras personas con acceso a los archivos todavía pueden recibir sugerencias o respuestas que hagan referencia a ellos.

## Solución de problemas comunes

### Faltan sugerencias de código

Comprobar:

* **Conexión a Internet:** Copilot requiere una conexión activa.
* **Extensión de Copilot:** utilizar la versión más reciente.
* **Compatibilidad del IDE:** verificar que el IDE sea compatible y esté correctamente configurado.
* **Exclusiones de contenido:** comprobar si los archivos están excluidos.

### Las exclusiones no funcionan según lo esperado

* **Aplicación diferida:** los cambios pueden tardar hasta 30 minutos en aplicarse en IDE que ya tienen cargada la configuración. Para aplicarlos inmediatamente, volver a cargar la configuración.
* **Ámbito incorrecto:** verificar que los miembros correspondientes tengan aplicada la configuración adecuada.
* **Estado en el IDE:** si una exclusión se aplica al archivo, el icono de GitHub Copilot en la barra de estado aparece con una línea diagonal. Al pasar el cursor se puede comprobar si la organización o el repositorio principal deshabilitaron Copilot.
* **Limitaciones del IDE:** determinadas funciones, como Chat de GitHub Copilot, pueden no aplicar las exclusiones.

### Las sugerencias de código no son satisfactorias

Para mejorar los resultados:

* **Proporcionar contexto claro:** usar comentarios descriptivos y nombres de variables significativos.
* **Usar comandos de Copilot:** algunos IDE ofrecen comandos específicos para solicitar sugerencias; en Visual Studio Code se puede utilizar **Ctrl+Entrar**.
* **Ajustar la longitud de la indicación:** probar indicaciones más largas o detalladas para mejorar las sugerencias.
