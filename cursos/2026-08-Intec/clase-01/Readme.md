# Clase Uno - 26 de Agosto del 2026

# Roadmap

* IA responable
    * Forma correcta y Buenas practicas de uso de GH Copilot
    * Limitaciones de GHCopilot
    * Casos uso
    * Capacidades
* Ecosistema de GH Copilot
* Generacion de Codigo
  * Como usar GH Copilot para generar y refactizar codigo
  * Uso del Chat
  * Uso del Chat Inline
  * Comandos (slash commands /)
  * Comandos con @
* Instrucciones personalizadas
* Uso de Copilot
    * Casos uso
    * Capacidades
    * Modo, Ask, Agente
* Uso de copilot en
  * VSCode
  * Visual Studio
  * Github
* Trabajo con bases de codigo existente
* Prompt engineering para GHCopilot
    * Contexto y  que toma GHCopilot
* ----
* GHCopilot CLI
* Uso de GHCopilot en el SDLC
    * Sofware Development Cycle
    * Para Analisis, disenio, etc ademas de para desarrollas
    * Documentacion
* Modo Agente
* Code Review
* Unit Test
* MCP
  * Model Context Protocol
* Skills
* Licencias, seguridad y Gobernanza
* Integracion
  * Integrar a GH Copilto con git
  * Rollback
  * Pull Requests documentado

---

# Presentacion Profe

* Me pueden contactar en:
   * https://www.linkedin.com/in/esteban-calabria-7a44401a/
   * https://www.instagram.com/mct.esteban.calabria/
      * Seguir para poder aprobar el examen!

---

# Requerimientos

* Visual Studio Code

---

# Recursos

* Microsoft Learn
   * https://learn.microsoft.com/es-es/training/courses/gh-300t00
* Para Rendir el examen
   * https://learn.microsoft.com/en-us/credentials/certifications/github-copilot/?practice-assessment-type=certification
* Resumenes y PPTs del Profe
   * https://github.com/estebancalabria/GH-300/
* Labs oficiales
   * https://github.com/estebancalabria/GH-300/tree/main/Labs
* Para rendir el examen
   * Exam Topics
   * Ojear : https://www.youtube.com/playlist?list=PLMp-_n0HEFXWnm1JabKJbqhANE8p1yvbH

---

# Setup

* Entrar a nuestro repo de gihub y ver copilot settings
    * Mi usuario Copilot Settings
    * Chequear que plan tenemos
 
* Bajar el repo
* Abrir la IDE
* Verificar que tenemos instalada la extension o instalarla
* Mostrar el chat de copilot con [ctrl]+[shift]+[i]

---

# IA Responsable

* Hay que saberselos para el examen
   * https://www.microsoft.com/en-us/ai/principles-and-approach
      * Fairness
      * Tranparency
      * Privacy y Security
      * Accountability
      * Inclusiveness
      * Reliability and Safety

---

# Modelos

* GH Copilot tiene varios modelos para elegir
* El modo "Auto" hace un routing al modelo que considera mas adecuado segun la tarea
* Lo puedo conectar con mi propio modelo 

---

# Generacion de codigo

* Generacion de codigo contextual
   * A media que escribirs va sugiriendo codigo
   * Me nuestra en gris (ghost code) la sugerencia y la acepto con [TAB]
* Basada en comentarios
   * Ejemplo : "//Funcion que recibe una lista de libros y devuelve solamente los libros disponibles"
   * Y genera codigo
* Char Inline
   * [Ctrl]+[I]
   * Selecciono la lista de libros y le pido algo como "Generame 5 libros mas"
* Chat
   * [Ctrl]+[Shift]+I
   * Ejemplo : "Agregame un metodo para obtener libros por anio indicando inicio y opcinalmente el fin.  quiero tambien poder buscar por nombre que contenga, y por autor."


## Pipeline interno

(Prompt)   --->  (agrega contexto) ---> (chequear opciono del usuario) ----> (guardrails / chequeo de seguridad)   ---->  (LLM)   ---> (chequeo de seguridad)

