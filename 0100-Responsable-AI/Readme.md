# Resumen

## Introducción

* Módulo sobre el uso responsable de la IA en el contexto de GitHub Copilot, una herramienta de IA generativa para desarrolladores.
* Aborda cómo utilizar Copilot eficazmente y mitigar riesgos éticos y operativos asociados al uso de IA.

### Objetivos

* Comprender y aplicar principios de uso responsable de la IA.
* Identificar limitaciones y mitigar riesgos asociados a la IA.
* Aplicar buenas prácticas para garantizar que el código generado por IA cumpla estándares éticos y requisitos específicos del proyecto.
* Reconocer la importancia de la transparencia y la responsabilidad en los sistemas de IA para generar confianza y mantener la confianza de los usuarios.

## Mitigación de riesgos de IA

* La IA ofrece oportunidades de innovación y eficiencia, pero también presenta riesgos que deben gestionarse cuidadosamente.
* Los sistemas de IA pueden tomar decisiones difíciles de interpretar, generando problemas de transparencia y responsabilidad.
* También pueden producir resultados no intencionados y perjudiciales, como decisiones sesgadas o violaciones de privacidad.
* Para mitigar estos riesgos es necesario:

  * Implementar marcos sólidos de gobernanza.
  * Garantizar la transparencia de los procesos de IA.
  * Incorporar supervisión humana.
* Estas medidas permiten aprovechar los beneficios de la IA reduciendo sus posibles impactos negativos.

## ¿Qué es la IA responsable?

* La IA responsable es un enfoque para desarrollar, evaluar y desplegar sistemas de IA de forma segura, confiable y ética.
* Los sistemas de IA son resultado de múltiples decisiones tomadas por las personas que los desarrollan y despliegan.
* La IA responsable permite orientar esas decisiones hacia resultados más beneficiosos y equitativos.
* Las personas y sus objetivos deben permanecer en el centro de las decisiones de diseño.
* Se deben respetar valores como:

  * Equidad.
  * Confiabilidad.
  * Transparencia.
* Microsoft y GitHub definen **seis principios de IA responsable**.

## Los seis principios de IA responsable de Microsoft y GitHub

### 1. Equidad (Fairness)

* Los sistemas de IA deben tratar a todas las personas de manera justa, evitando impactos diferenciados sobre grupos en situaciones similares.
* En ámbitos como tratamientos médicos, solicitudes de préstamos o empleo, deben ofrecer recomendaciones consistentes para personas con características equivalentes.
* Para detectar y mitigar sesgos se pueden:

  * Revisar los datos de entrenamiento.
  * Probar modelos con muestras demográficas equilibradas.
  * Utilizar técnicas de reducción de sesgos.
  * Monitorear el rendimiento del modelo por segmentos de usuarios.
  * Implementar controles que permitan invalidar puntuaciones injustas.
* Utilizar datos diversos y equilibrados ayuda a reducir sesgos y promover la equidad.

### 2. Confiabilidad y seguridad (Reliability and Safety)

* Los sistemas de IA deben funcionar de forma confiable, segura y consistente para generar confianza.
* Deben:

  * Funcionar según lo diseñado.
  * Responder de forma segura ante condiciones inesperadas.
  * Resistir manipulaciones perjudiciales.
  * Minimizar daños no intencionados, incluidos daños físicos, emocionales y financieros.
* La confiabilidad implica un funcionamiento consistente, sin variaciones o errores no deseados.
* Los sistemas seguros y confiables deben ser robustos, precisos y predecibles en condiciones normales.

### 3. Privacidad y seguridad (Privacy and Security)

* La IA debe proteger la privacidad de los usuarios y la seguridad de sus datos.
* Las prácticas principales incluyen:

  * Obtener consentimiento antes de recopilar datos y explicar claramente cómo serán utilizados.
  * Recopilar únicamente los datos necesarios para el funcionamiento de la IA.
  * Eliminar datos sensibles cuando ya no sean necesarios.
  * Anonimizar datos personales mediante técnicas como pseudonimización y agregación.
* Los datos sensibles deben cifrarse tanto durante la transferencia como cuando están almacenados.
* Para proteger las claves pueden utilizarse:

  * **HSM (Hardware Security Modules)**.
  * Almacenes seguros como Microsoft Azure.
  * **Envelope encryption**.
* Las organizaciones deben controlar el acceso a claves y modelos, rotar las claves regularmente, realizar copias de seguridad seguras y efectuar auditorías periódicas.
* El acceso de empleados a modelos y datos sensibles debe limitarse según su nivel de sensibilidad.

### 4. Inclusividad (Inclusiveness)

* Los sistemas de IA deben ser justos, accesibles y capaces de empoderar a todas las personas.
* Deben:

  * Funcionar correctamente para usuarios y grupos diversos.
  * Ser accesibles independientemente de las capacidades físicas o mentales.
  * Estar disponibles para diferentes regiones y geografías.
  * Incorporar perspectivas de personas de diferentes comunidades y contextos.
  * Permitir que todos los usuarios se beneficien de sus capacidades.
* Ejemplos:

  * Reconocimiento facial que funcione con diferentes tonos de piel, edades y géneros.
  * Interfaces compatibles con lectores de pantalla.
  * Traducción que contemple dialectos regionales.
  * Equipos de desarrollo con perspectivas diversas.
* La inclusión debe contemplar posibles barreras de discapacidad, idioma, infraestructura y conectividad.
* Las soluciones pueden incorporar:

  * Control por voz, subtítulos y lectores de pantalla.
  * Adaptación a diferentes idiomas y contextos culturales.
  * Funcionamiento offline y con conectividad o recursos informáticos limitados.

### 5. Transparencia (Transparency)

* Los sistemas de IA deben ser comprensibles e interpretables.
* Los desarrolladores deben:

  * Explicar claramente cómo funcionan los sistemas.
  * Justificar las decisiones de diseño.
  * Comunicar honestamente sus capacidades y limitaciones.
  * Permitir auditorías mediante registros, informes y mecanismos de auditoría.
* La transparencia contribuye a:

  * Generar confianza.
  * Garantizar responsabilidad.
  * Promover la equidad.
  * Mejorar la seguridad.
  * Favorecer la inclusión.
* Puede implementarse mediante documentación de datos y modelos, interfaces explicativas, herramientas de depuración, dashboards de pruebas y mecanismos de logging y auditoría.

### 6. Responsabilidad (Accountability)

* Las personas y organizaciones responsables de crear y desplegar sistemas de IA deben asumir responsabilidad por su funcionamiento.
* Los desarrolladores deben monitorear continuamente el rendimiento de los sistemas y mitigar los riesgos.
* La responsabilidad es especialmente importante ante casos de daños algorítmicos, sesgos y usos indebidos.
* Microsoft considera la responsabilidad un principio fundamental de su estándar de IA responsable.
* Los sistemas de IA deben rendir cuentas ante las personas y las organizaciones que los despliegan deben asumir responsabilidad por su operación.
