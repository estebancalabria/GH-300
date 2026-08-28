# Clase dos - 28 de Agosto del 2026

# Repaso

* IA Responable
  * Human in the loop : Chequear todos
  * Los principios de MS
  * Que comete errores y ojo con la seguridad
* Generacion de codigo
  * Sugerencia mientras escribo
  * Inline Chat ([CTRL}+[I])
  * Generacion basada en comentario
  * Chat ([CTRL]+[SHIFT]+[I]  / [CTRL]+[ALT]+[I])
  * Terminal
* Comandos del Chat
  * / conmandos slash
      * /test
      * /fix
      * /optimize
      * /generate
      * /explain
  * (#)Hashtag / Almohadilla
      * Para agregar al contexto del chat
      * #codebase (como el reemplazo de @workspace)
        * consume mas tokens porque tiene que indexar todo el proyexcto
      * #file para citar en el chat un archivo especifico
  * @ contexto / citar agentes
      * @workspace (no estaba en vscode)
      * @terminal (en vez copiar y pegar la salida de la terminal la traes al contexto)
* Prompting
  * Contexto
    * No toma todo el proyecto, toma los archivos abiertos y lo que cite en la terminal
* Github Copilot CLI
    * Para usarlo desde la terminal
    * Lo mas parecido a claude code / codex / OpenCode entro de github copilot
* Casos de uso
    * Generar codigo
    * Pruebas
    * Documentacion
    * Tareas repetitivas

---

# Copiot Buisness

* Importante leer la info de este repo y
 * https://learn.microsoft.com/es-es/training/modules/github-copilot-management-and-customizations/


---

# Buenas Practicas (ojo para el examen)

* Chequear todo lo que hace copilot
* Ir a pasitos de bebe
* Usar Git como control de versiones interno para volver atras enseguida si copilot rompe todo

---

# Gihub Copilot Codesapces

* Con el . te abre un vscode para editar el proyecto, pero no es codespaces porque es solo para editar.
* Codespaces te genera una maquina virtual para que trabajes y si se puede, ejecutes tu proyecto
* Para abrirlo en el reposotorio uso el boton verde que dice "Code"

---

# Prompt Engineering

## High Level Goal

* Consiste en poner un comentario grande al principio de cada archivo indicando lo que hace para guiar a copilot

* Ejempllo
```
/*
 API v1
Este codigo corresponde a una api hecha con express que soporta cors y sirve para libros
Tengo un get que me devuelve la lista de libros
Un get que me devuelve un libro por su id
Un post para agregar un libro nuevo
Un put para actualizar un libro existente
Un delete para eliminar un libro por su id
La lista de libros es un json en memoria en una variable global
Si no escuentra algo devuelve un error http correpondiente
Siempre se validan los datos de entrada
*/
```

```javascript
const express = require('express');
const cors = require('cors');
const app = express();
app.use(cors());
app.use(express.json());

let libros = [
    { id: 1, titulo: 'Cien años de soledad', autor: 'Gabriel García Márquez' },
    { id: 2, titulo: '1984', autor: 'George Orwell' },
    { id: 3, titulo: 'El principito', autor: 'Antoine de Saint-Exupéry' },
    { id: 4, titulo: 'Don Quijote de la Mancha', autor: 'Miguel de Cervantes' },
    { id: 5, titulo: 'Orgullo y prejuicio', autor: 'Jane Austen' }
]; // Lista de libros en memoria

// Puerto en el que escuchará la API
const PORT = 3000;


// Rutas de la API
app.get('/libros', (req, res) => {
    res.json(libros);
});

app.get('/libros/:id', (req, res) => {
    const libro = libros.find(l => l.id === parseInt(req.params.id));
    if (!libro) return res.status(404).send('Libro no encontrado');
    res.json(libro);
});

app.post('/libros', (req, res) => {
    const { id, titulo, autor } = req.body;
    if (!id || !titulo || !autor) return res.status(400).send('Datos incompletos');
    const libro = { id, titulo, autor };
    libros.push(libro);
    res.status(201).json(libro);
});

app.put('/libros/:id', (req, res) => {
    const libro = libros.find(l => l.id === parseInt(req.params.id));
    if (!libro) return res.status(404).send('Libro no encontrado');
    const { titulo, autor } = req.body;
    if (!titulo || !autor) return res.status(400).send('Datos incompletos');
    libro.titulo = titulo;
    libro.autor = autor;
    res.json(libro);
});

app.delete('/libros/:id', (req, res) => {
    const index = libros.findIndex(l => l.id === parseInt(req.params.id));
    if (index === -1) return res.status(404).send('Libro no encontrado');
    const libro = libros.splice(index, 1);
    res.json(libro);
});

app.listen(PORT, () => {
    console.log(`API v1 escuchando en el puerto ${PORT}`);
});

```

## Copilot  Instructions

* Las instrucciones permiten definir reglas de generacion de codigo para todo el proyecto

* Para crearlas
  * Crear una carpeta que se llama .gihub
  * Crear un archivo que se llama copilot-instructions.md


> [!NOTE]
> Attenti por si cambia la forma. Siempre ir a la documentacion
> https://docs.github.com/es/copilot/how-tos/copilot-on-github/customize-copilot/add-custom-instructions/add-repository-instructions

```
---
name: instrucciones-generacion-codigo
description: Instrucciones para la generación de código en el proyecto.
applyTo: **
---

# Instrucciones para generacion de codigo

* Todas las funciones deben tener documentacion tipo JSDoc.
* Todas las funciones comienzan con el prefijo "fn_".
* La primera linea de las funciones tienen el comentario //Esteban Crack

```

> [!NOTE]
> Chequear en la ruedita de copilot Chat en el menu Instrucciones que lo este tomando



---

# Model Context Protocol

* URL
  * https://modelcontextprotocol.io/
  * https://github.com/modelcontextprotocol/servers-archived/tree/main/src
* Caracteristicas
  * Es la un protocolo para poder extender la capacidades de nuestro agente mediante herramientas nuevas

> [!WARN]
> Se pueden instlar globalmente para todos mis proyectos en la ruedita arriba del chat de Copilot, pero no lo recomiendo porque despues cada prompt tarda mucho

* Instalar un mcp para el proyecto
  * Creamos la carpeta .vscode en la raiz del proyecto
  * Creamos el archivo mcp.json

```json
{
    "servers": {
        "puppeteer": {
            "command": "npx",
            "args": [
                "-y",
                "@modelcontextprotocol/server-puppeteer"
            ]
        }
    }
}
```

* Arriba de pupeteer darle start

<img width="220" height="80" alt="image" src="https://github.com/user-attachments/assets/8636b9ca-6492-41dc-8447-4e5e4ddcd423" />
