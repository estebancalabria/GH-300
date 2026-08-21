# Módulo 2: Democratizar Conocimiento Tribal con GitHub Copilot Spaces

**Duración:** 30-45 min
**Prerequisitos:** Cuenta GitHub con acceso a Copilot, navegador web

## Conocimientos previos
Un **pull request** es una solicitud para fusionar cambios de código de una rama a otra dentro de un repositorio.
Un **issue** es un ticket dentro de un repositorio para registrar tareas, bugs o mejoras pendientes.

## Objetivo
Usar Copilot Spaces para indexar documentación de un repo como fuente de consulta, y a partir de ese contexto disparar acciones reales en GitHub (crear issues, generar y mergear PRs con el Coding Agent).

---

## Paso 0 — Repo de práctica

[BROWSER] Ir a: `https://github.com/skills/scale-institutional-knowledge-using-copilot-spaces`
[BUTTON] **Copy Exercise** → crear repo público (evita gastar minutos de Actions)
[BUTTON] **Create repository** (dejar todo default)

---

## Paso 1 — Crear y "primear" el Space

[LINK] `https://github.com/copilot/spaces`
[BUTTON] **Create Space**
[FIELD] Nombre: `OctoAcme Project Management Hub`
[BUTTON] **Create Space**
[FIELD] Descripción: `Centralizing and democratizing project management knowledge for the OctoAcme organization`

### Instrucciones del Space
[TAB] **Instructions** → pegar:
```
### Purpose of this Copilot Space
- Centralize scattered project management knowledge in Copilot Spaces
- Convert tacit team insights into searchable, versioned artifacts
- Give all team members equal access to processes, decisions, and rationale
- Connect a repository as a structured knowledge source
- Extract, refine, and standardize workflows collaboratively
- Feed validated improvements back into living documentation
- Accelerate onboarding and reduce single-person dependency risk
- Enable consistent, repeatable project execution

## Issue templates for program process documents
- Stored in `.github/ISSUE_TEMPLATE/`
```
[BUTTON] **Save**

### Agregar fuente (source)
[BUTTON] **+ Add sources** → buscar `tu_usuario/skills-scale-institutional-knowledge-using-copilot-spaces`
Seleccionar carpetas `docs/` y `.github/ISSUE_TEMPLATE/` → [BUTTON] **Add**

### Crear issue para README
En el chat del Space, prompt:
```
Create an issue in the repository <usuario>/skills-scale-institutional-knowledge-using-copilot-spaces
for a README for OctoAcme Project Management Docs that has links to all the docs in the docs folder.
- Include a brief summary of the project management processes used by OctoAcme.
- README, summary, and links must be in the issue title.
- Use the "Add Content to Project Management Process Docs" template.
- Which process document do you want to update? "<new document>"
- Fill in the other fields
```
[BUTTON] **Create** (revisar el issue generado antes)

---

## Paso 2 — Resumir docs y generar PR con el Coding Agent

### Resumen de procesos
Nueva conversación en el Space, prompt:
```
Create a 3-4 paragraph summary of the project management processes used by OctoAcme
based on the documentation in the docs folder of this repository.
Focus on key workflows, personas/roles, communication strategies, and quality assurance practices.
```

### Adjuntar issue y disparar Coding Agent
1. Anotar número del issue creado en Paso 1
2. En el mismo chat, escribir (sin enviar): `@usuario/repo/issues/#` → `+` para adjuntar sin enviar
3. Verificar que aparezca título y detalle del issue
4. Enviar prompt:
```
- Using the github-coding-agent tool create a pull request based on the attached issue.
- The README should also contain a brief overview of the project management processes
  used by OctoAcme based on the summary we just created.
- The README should be in the `docs/` folder
- Add this pull request to the attached issue.
- Add <usuario> as a reviewer for the pull request
```
[DIALOG] **Allow** cuando pida permiso sobre el repo

Seguimiento: pestaña **Pull requests** del repo, o en el chat: `check open pull requests` (agente tarda 5-15 min)

### Revisar y mergear
[TAB] Pull request → revisar `docs/README.md` → [BUTTON] **Approve** → **Submit review** → **Ready to merge** → **Merge pull request** → **Confirm merge**

---

## Paso 3 — Issue y PR de mejora continua

### Issue de mejora (roles/personas nuevas)
Nueva conversación (modelo GPT-4.1), seleccionar repo, adjuntar template `.github/ISSUE_TEMPLATE/add-update-content-to-process-docs.yml`, prompt:
```
Use the attached issue template:
- Find new personas/roles that could be added to our project management documentation
- Create an issue titled "Adding more personas and roles to the project management processes"
- Include descriptions of responsibilities for each new role
- Explain how these new roles interact with existing roles
- Explain why this is important and how it will improve our project
- Target the process document: docs/octoacme-roles-and-personas.md
```
Confirmar creación del issue.

### PR desde el issue
Copiar URL del issue nuevo → pegarlo en el chat como `@usuario/repo/issues/N` (**Shift+Enter**, no Enter) → prompt:
```
Using the github-coding-agent tool:
- Create a pull request that implements the process improvements from the attached issue
- Address the gaps identified in the project management documentation
- Update existing docs or create new templates as needed
- Place all documents in the docs/ folder
- Link this pull request to the attached issue
- Add <usuario> as a reviewer
```
[DIALOG] **Allow** → revisar PR → **Approve** → **Submit review** → **Merge pull request** → **Confirm merge**

---

## Takeaways
- Copilot Spaces = hub de conocimiento con fuentes indexadas (repo, docs, issues)
- El Coding Agent puede generar PRs completos a partir de un issue adjuntado
- Ciclo completo: capturar → analizar → compartir → mejorar
- Aplicable a cualquier dominio con conocimiento tribal, no solo PM
