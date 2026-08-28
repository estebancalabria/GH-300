# GH-300 — GitHub Copilot
## Programa — 2 clases de 4 horas

## Día 1 — Copilot como asistente de desarrollo

- **1. Introducción a GitHub Copilot**
  - Qué es GitHub Copilot
  - Ecosistema de Copilot
  - Capacidades
  - Casos de uso
  - Limitaciones

- **2. Generación de código**
  - Code completion
  - Generación de funciones
  - Generación de clases
  - Refactoring
  - Documentación
  - Explicación de código

- **3. Copilot Chat**
  - Chat
  - Contexto
  - Preguntas sobre código
  - Explicación
  - Resolución de problemas

- **4. Slash Commands**
  - `/explain`
  - `/fix`
  - `/tests`
  - `/doc`
  - `/new`
  - Otros comandos disponibles

- **5. @ Commands**
  - `@workspace`
  - `@terminal`
  - Otros contextos/participantes
  - Diferencia entre `@` y `/`

- **6. Prompt Engineering**
  - **Contexto**
    - Archivos
    - Código seleccionado
    - Workspace
    - Información relevante
  - **High-level goal**
    - Qué queremos conseguir
    - Resultado esperado
  - **Especificidad**
    - Lenguaje
    - Framework
    - Restricciones
    - Convenciones
  - **Iteración**
    - Evaluar respuesta
    - Refinar prompt
    - Dividir tareas
  - **Instrucciones del proyecto**
    - Custom Instructions de GitHub Copilot
    - `AGENTS.md` / archivo equivalente según el entorno
    - Reglas y convenciones del proyecto
    - Instrucciones reutilizables

- **7. Modos de interacción**
  - **Ask**
    - Preguntar
    - Analizar
    - Explicar
  - **Edit**
    - Modificar código
    - Aplicar cambios
  - **Agent**
    - Resolver tareas
    - Usar herramientas
    - Iterar


## Día 2 — Copilot como agente

- **8. Agent Mode**
  - Qué es
  - Diferencia entre Ask, Edit y Agent
  - Planificación
  - Uso de herramientas
  - Ejecución de acciones
  - Iteración
  - Validación

- **9. Copilot Coding Agent**
  - Qué es
  - Diferencia con Agent Mode
  - Trabajar con Issues
  - Resolver tareas
  - Generar cambios
  - Pull Requests

- **10. Testing**
  - Generación de Unit Tests
  - `/tests`
  - Edge cases
  - Test coverage
  - Validación de tests generados
  - Ciclo:
    - Generar código
    - Generar tests
    - Ejecutar
    - Detectar error
    - Corregir
    - Volver a ejecutar

- **11. Code Review**
  - Revisión de código con Copilot
  - Análisis de Pull Requests
  - Detección de problemas
  - Seguridad
  - Code smells
  - Sugerencias de mejora
  - Limitaciones del review automático

- **12. Spaces**
  - Qué son
  - Contexto
  - Fuentes
  - Casos de uso

- **13. GitHub Copilot CLI**
  - Uso desde terminal
  - Generación de comandos
  - Explicación de comandos
  - Ejecución de tareas
  - Consideraciones de seguridad

- **14. MCP**
  - Qué es MCP
  - MCP Servers
  - Tools
  - Recursos/contexto
  - Cómo amplía las capacidades de Copilot
  - Seguridad

- **15. Licencias y seguridad**
  - Licenciamiento
  - Capacidades según licencia
  - Administración
  - Políticas
  - Privacidad
  - Data handling
  - Content exclusion
  - Responsible AI
  - Seguridad

- **16. Escenario integrador**
  - Issue
  - Prompt
  - Contexto
  - Generación
  - Agent
  - Tests
  - Fix
  - Code Review
  - Pull Request


---

# PLAN CLASE 2

Pensó durante 14s
Plan — Clase 2 (3.5 hs / 210 min)

1. Apertura y repaso rápido de pendientes de Clase 1 — 5 min
Custom Instructions y Ask/Edit/Agent quedan integrados en los bloques de abajo, no hace falta un repaso aparte.

2. Teórico: Copilot pago (licencias y planes) — 20 min

Free vs Pro vs Pro+ vs Business vs Enterprise
Qué cambia por plan: modelos disponibles, límites de uso, Coding Agent, políticas de administración
Gestión desde la organización (governance, policies)

3. Custom Instructions — 25 min

copilot-instructions.md (repo-wide) vs instrucciones personales
Cuándo usarlas vs cuándo usar una Skill (siempre-on vs on-demand)
Práctica: crear un copilot-instructions.md simple para el proyecto del curso

4. High-level goal (prompt engineering) — 15 min

Definir el objetivo antes de prompt-ear: qué resultado se espera, no solo "qué hacer"
Ejercicio corto: reescribir un prompt vago como high-level goal + restricciones

5. Skills — 35 min

Teoría: qué son, .github/skills/, SKILL.md, progressive disclosure
Lab que ya armamos (commit-message-writer) — hacerlo en vivo

— Break — 10 min

6. MCP (Model Context Protocol) — 35 min

Qué es, MCP Servers, tools, cómo amplía el contexto de Copilot
Diferencia con Skills (MCP = herramientas externas / datos en vivo; Skills = procedimientos reutilizables)
Demo: conectar un MCP server (ej. GitHub MCP o filesystem) y usarlo desde el chat

7. GitHub Codespaces + Copilot — 30 min

Qué es un Codespace, cómo se levanta desde un repo
Copilot dentro del Codespace (mismo Chat/Agent, contexto del entorno remoto)
Práctica: abrir un Codespace del repo del curso y correr un prompt ahí

8. Copilot Spaces — 20 min

Qué son, cómo se arma un Space con fuentes (archivos, repos, docs)
Caso de uso: contexto curado para un tema específico del proyecto

9. Cierre y dudas — 10 min
