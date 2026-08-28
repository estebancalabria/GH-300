# Laboratorio: Uso de Agent Skills en GitHub Copilot

## Objetivo
Crear, detectar y usar una Skill personalizada en GitHub Copilot (VS Code), aplicando el estándar abierto `agentskills.io`. Al finalizar vas a poder empaquetar un flujo de trabajo repetitivo como Skill y hacer que el agente la use automáticamente.

## Duración estimada
30–40 minutos

## Prerrequisitos
- Visual Studio Code con la extensión de GitHub Copilot instalada y sesión iniciada
- Un repositorio local (puede ser el mismo que venís usando en el curso)
- Copilot en modo **Agent** disponible en el Chat

---

## Paso 1 — Crear la carpeta de la Skill

Las Skills se guardan en una carpeta dentro del repo. GitHub Copilot busca automáticamente en `.github/skills/`.

[TERMINAL] Ejecutar en la raíz del proyecto:

```
mkdir -p .github/skills/commit-message-writer
```

## Paso 2 — Crear el archivo SKILL.md

[MENU] Archivo > Nuevo archivo, dentro de `.github/skills/commit-message-writer/`, crear `SKILL.md`

Contenido del archivo (frontmatter + instrucciones):

```markdown
---
name: commit-message-writer
description: >-
  Writes conventional commit messages based on staged changes.
  Use when the user asks to commit, write a commit message, or describe changes.
---

## Procedure
1. Run `git diff --staged` to see the staged changes.
2. Summarize the change in one short imperative sentence (max 72 chars).
3. Use the Conventional Commits format: type(scope): description
   - Allowed types: feat, fix, docs, refactor, test, chore
4. If the change touches multiple concerns, suggest splitting the commit.
5. Never include the full diff in the commit message.
```

> Nota: `name` y `description` son obligatorios — Copilot usa la `description` para decidir cuándo activar la Skill, así que conviene que sea específica e incluya palabras clave.

## Paso 3 — Verificar que Copilot detecta la Skill

[TAB] Abrir el Chat de Copilot (`[Ctrl]+[Shift]+[I]`)

Escribir:

```
/skills
```

[DIALOG] Debería aparecer `commit-message-writer` en la lista de Skills detectadas. Si no aparece, recargar la ventana de VS Code (`Developer: Reload Window`).

## Paso 4 — Probar la Skill en modo Agent

[TAB] Asegurarse de estar en modo **Agent** en el selector del Chat

1. Modificar algún archivo del proyecto y dejar los cambios en staging:

```
git add .
```

2. Pedirle a Copilot:

```
Write a commit message for my staged changes
```

3. Observar que en el chat aparece indicado que se está usando la Skill `commit-message-writer` antes de generar la respuesta.

## Paso 5 — Ampliar la Skill (opcional)

Las Skills pueden incluir recursos adicionales además del `SKILL.md`, por ejemplo una carpeta `references/` con ejemplos largos que no conviene tener siempre cargados (progressive disclosure).

[BROWSER] Ir a `https://github.com/github/awesome-copilot` para ver Skills de ejemplo de la comunidad e instalarlas con:

```
gh skills install github/awesome-copilot <nombre-skill>
```

---

## Cierre / Puntos clave
- Una Skill vive en una carpeta con un `SKILL.md` obligatorio (nombre + descripción + procedimiento)
- Se ubican en `.github/skills/` (repo), `.claude/skills/` o `.agents/skills/` — Copilot las descubre automáticamente
- A diferencia de las Custom Instructions (siempre activas), las Skills se activan **on-demand** cuando el prompt coincide con la descripción
- Se pueden verificar con `/skills` en el Chat
- Funcionan en VS Code, Visual Studio, Copilot CLI y Copilot Coding Agent

## Para profundizar
- https://github.com/github/awesome-copilot
- https://agentskills.io
