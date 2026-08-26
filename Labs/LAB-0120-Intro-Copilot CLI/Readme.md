# Laboratorio: Introducción a GitHub Copilot CLI

## Objetivos

Al finalizar este laboratorio serás capaz de:

1. Instalar GitHub Copilot CLI.
2. Configurar una sesión de trabajo.
3. Explicar comandos complejos utilizando IA.
4. Generar comandos mediante lenguaje natural.
5. Utilizar GitHub Copilot desde la terminal para tareas de administración y desarrollo.
6. Comprender buenas prácticas de uso de Copilot CLI.

---

# Escenario

Como profesional IT, frecuentemente trabajas desde la terminal ejecutando comandos de Linux, PowerShell, Azure CLI, Docker y Git.

GitHub Copilot CLI permite interactuar mediante lenguaje natural para:

- Explicar comandos.
- Generar comandos.
- Resolver dudas técnicas.
- Acelerar tareas administrativas.
- Reducir errores de sintaxis.

---

# Prerrequisitos

- Suscripción activa de GitHub Copilot.
- Node.js instalado.
- npm instalado.
- Conexión a Internet.

---

# Ejercicio 1 - Verificar Node.js

## Paso 1

Abrir una terminal.

## Paso 2

Verificar las versiones instaladas.

```bash
node --version
npm --version
```

### Resultado esperado

Se muestran las versiones instaladas de Node.js y npm.

---

# Ejercicio 2 - Instalar GitHub Copilot CLI

## Paso 1

Instalar GitHub Copilot CLI globalmente.

```bash
npm install -g @github/copilot
```

### Resultado esperado

La instalación finaliza correctamente.

---

## Paso 2

Verificar la instalación.

```bash
copilot --help
```

### Resultado esperado

Se muestra la ayuda del producto.

---

# Ejercicio 3 - Iniciar una sesión interactiva

## Paso 1

Iniciar Copilot CLI.

```bash
copilot
```

### Resultado esperado

Se abre una sesión interactiva.

---

# Ejercicio 4 - Explicar un comando Linux

Una de las capacidades más útiles de Copilot CLI es explicar comandos existentes.

## Paso 1

Ejecutar:

```bash
copilot -i "explain tar -czvf backup.tar.gz /home/user"
```

### Resultado esperado

Copilot explica:

- El propósito del comando.
- El significado de cada parámetro.
- El resultado esperado.

---

# Ejercicio 5 - Explicar un comando Docker

## Paso 1

Ejecutar:

```bash
copilot -i "explain docker run -d -p 8080:80 nginx"
```

### Resultado esperado

Copilot explica:

- Qué imagen se ejecuta.
- Cómo funciona el mapeo de puertos.
- Qué significa el parámetro `-d`.

---

# Ejercicio 6 - Generar comandos mediante lenguaje natural

## Paso 1

Solicitar una tarea sencilla.

```bash
copilot -i "suggest a command to display the 10 largest files in the current directory"
```

### Resultado esperado

Copilot propone uno o más comandos válidos.

---

# Ejercicio 7 - Trabajar con Azure

## Paso 1

Solicitar un comando de Azure CLI.

```bash
copilot -i "suggest an Azure CLI command to create a resource group named rg-demo in eastus"
```

### Resultado esperado

Copilot genera el comando correspondiente de Azure CLI.

---

# Ejercicio 8 - Trabajar con PowerShell

## Paso 1

Solicitar ayuda para obtener procesos.

```bash
copilot -i "suggest a PowerShell command that shows the five processes using the most memory"
```

### Resultado esperado

Copilot genera una solución utilizando PowerShell.

---

# Ejercicio 9 - Buscar archivos

## Paso 1

Solicitar un comando de búsqueda.

```bash
copilot -i "suggest a command to find all Python files in the current directory and subdirectories"
```

### Resultado esperado

Copilot genera uno o varios comandos válidos.

---

# Ejercicio 10 - Comprimir una carpeta

## Paso 1

Solicitar ayuda para crear un archivo ZIP.

```bash
copilot -i "suggest a command to compress the Logs folder into logs.zip"
```

### Resultado esperado

Copilot genera el comando correspondiente.

---

# Desafío 1

Utiliza GitHub Copilot para generar comandos que permitan:

1. Mostrar espacio utilizado por una carpeta.
2. Buscar archivos modificados durante las últimas 24 horas.
3. Mostrar puertos abiertos.
4. Encontrar procesos de un usuario específico.
5. Eliminar archivos temporales.

---

# Desafío 2 - DevOps

Genera comandos para:

- Crear un repositorio Git.
- Inicializar Git.
- Crear una rama.
- Construir una imagen Docker.
- Mostrar contenedores activos.

---

# Buenas prácticas

✅ Describir claramente el objetivo.

✅ Revisar siempre el comando antes de ejecutarlo.

✅ Validar comandos destructivos.

✅ Utilizar Copilot como asistente, no como sustituto del análisis técnico.

✅ Proporcionar contexto cuando sea posible.

---

# Preguntas de reflexión

1. ¿Qué ventajas tiene utilizar lenguaje natural para generar comandos?
2. ¿Cuándo resulta útil utilizar la capacidad de explicación?
3. ¿Qué riesgos existen al ejecutar comandos sin comprenderlos?
4. ¿Cómo puede Copilot CLI mejorar la productividad de administradores y desarrolladores?

---

# Conclusiones

En este laboratorio aprendiste a:

- Instalar GitHub Copilot CLI.
- Utilizar IA desde la terminal.
- Explicar comandos existentes.
- Generar comandos mediante lenguaje natural.
- Trabajar con Linux, PowerShell, Azure CLI y Docker utilizando asistencia basada en IA.

GitHub Copilot CLI es una herramienta valiosa para profesionales de infraestructura, desarrollo, DevOps, seguridad y cloud que trabajan habitualmente desde la línea de comandos.
