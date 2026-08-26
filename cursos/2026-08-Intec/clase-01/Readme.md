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

## Pipeline interno

(Prompt)   --->  (agrega contexto) ---> (chequear opciono del usuario) ----> (guardrails / chequeo de seguridad)   ---->  (LLM)   ---> (chequeo de seguridad)

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

* Codigo Generado
```javascript

var libros = [
    {
        nombre : "El Quijote",
        autor : "Miguel de Cervantes",
        año : 1605,
        genero : "Novela",
        disponible : true
    },
    {
        nombre : "Cien años de soledad",
        autor : "Gabriel García Márquez",
        año : 1967,
        genero : "Realismo mágico",
        disponible : false
    },
    {
        nombre : "1984",
        autor : "George Orwell",
        año : 1949,
        genero : "Ciencia ficción",
        disponible : true
    },
    {
        nombre : "Orgullo y prejuicio",
        autor : "Jane Austen",
        año : 1813,
        genero : "Romance",
        disponible : false
    },
    {
        nombre : "La sombra del viento",
        autor : "Carlos Ruiz Zafón",
        año : 2001,
        genero : "Misterio",
        disponible : true
    }
];

//Funcion que recibe una lista de libros y devuelve solamente los libros disponibles
function obtenerLibrosDisponibles(listaLibros) {
    return listaLibros.filter(libro => libro.disponible);
}

// Función que filtra libros por un rango de años (o un año específico si no se indica el fin)
function obtenerLibrosPorAnio(listaLibros, anioInicio, anioFin) {
    const fin = anioFin !== undefined ? anioFin : anioInicio;
    return listaLibros.filter(libro => libro.año >= anioInicio && libro.año <= fin);
}

// Función que busca libros cuyo nombre contenga el texto especificado
function obtenerLibrosPorNombre(listaLibros, texto) {
    return listaLibros.filter(libro => libro.nombre.toLowerCase().includes(texto.toLowerCase()));
}

// Función que busca libros por autor
function obtenerLibrosPorAutor(listaLibros, autor) {
    return listaLibros.filter(libro => libro.autor.toLowerCase().includes(autor.toLowerCase()));
}


```

---

# Slash Commands

* Se usan en el chat
* /explain : Explica el codigo seleccionado
* /fix : Busca errores en una funcion, te muestra las correcciones sugeridas
* /doc (deprecated) :
   * Lo reemplazo por el prompt : "Generame la documentacion jsdoc de las funciones selecionadas"
* /clear : Chat Nuevo
* /tests
   * Invalid project root name in file tree: .

```javascript
const fs = require("fs");
const path = require("path");
const vm = require("vm");

const codigoLibreria = fs.readFileSync(
    path.join(__dirname, "libreria.js"),
    "utf8"
);

const contexto = {};
vm.createContext(contexto);
vm.runInContext(codigoLibreria, contexto);

const {
    obtenerLibrosDisponibles,
    obtenerLibrosPorAnio,
    obtenerLibrosPorNombre,
    obtenerLibrosPorAutor
} = contexto;

const libros = [
    {
        nombre: "El Quijote",
        autor: "Miguel de Cervantes",
        año: 1605,
        genero: "Novela",
        disponible: true
    },
    {
        nombre: "Cien años de soledad",
        autor: "Gabriel García Márquez",
        año: 1967,
        genero: "Realismo mágico",
        disponible: false
    },
    {
        nombre: "1984",
        autor: "George Orwell",
        año: 1949,
        genero: "Ciencia ficción",
        disponible: true
    },
    {
        nombre: "Orgullo y prejuicio",
        autor: "Jane Austen",
        año: 1813,
        genero: "Romance",
        disponible: false
    },
    {
        nombre: "La sombra del viento",
        autor: "Carlos Ruiz Zafón",
        año: 2001,
        genero: "Misterio",
        disponible: true
    }
];

describe("obtenerLibrosDisponibles", () => {
    test("devuelve únicamente los libros disponibles", () => {
        const resultado = obtenerLibrosDisponibles(libros);

        expect(resultado.map(libro => libro.nombre)).toEqual([
            "El Quijote",
            "1984",
            "La sombra del viento"
        ]);
    });

    test("devuelve un arreglo vacío si no hay libros disponibles", () => {
        expect(obtenerLibrosDisponibles([
            { nombre: "Libro reservado", disponible: false }
        ])).toEqual([]);
    });
});

describe("obtenerLibrosPorAnio", () => {
    test("busca libros de un año específico", () => {
        const resultado = obtenerLibrosPorAnio(libros, 1949);

        expect(resultado.map(libro => libro.nombre)).toEqual(["1984"]);
    });

    test("filtra libros dentro de un rango inclusivo", () => {
        const resultado = obtenerLibrosPorAnio(libros, 1605, 1967);

        expect(resultado.map(libro => libro.nombre)).toEqual([
            "El Quijote",
            "Cien años de soledad",
            "1984"
        ]);
    });

    test("devuelve un arreglo vacío si no hay coincidencias", () => {
        expect(obtenerLibrosPorAnio(libros, 2020, 2030)).toEqual([]);
    });
});

describe("obtenerLibrosPorNombre", () => {
    test("busca sin distinguir mayúsculas y minúsculas", () => {
        const resultado = obtenerLibrosPorNombre(libros, "QUIJOTE");

        expect(resultado.map(libro => libro.nombre)).toEqual(["El Quijote"]);
    });

    test("permite buscar coincidencias parciales", () => {
        const resultado = obtenerLibrosPorNombre(libros, "sombra");

        expect(resultado.map(libro => libro.nombre)).toEqual([
            "La sombra del viento"
        ]);
    });

    test("devuelve un arreglo vacío si no hay coincidencias", () => {
        expect(obtenerLibrosPorNombre(libros, "Fantasía")).toEqual([]);
    });
});

describe("obtenerLibrosPorAutor", () => {
    test("busca sin distinguir mayúsculas y minúsculas", () => {
        const resultado = obtenerLibrosPorAutor(libros, "ORWELL");

        expect(resultado.map(libro => libro.nombre)).toEqual(["1984"]);
    });

    test("permite buscar coincidencias parciales", () => {
        const resultado = obtenerLibrosPorAutor(libros, "García");

        expect(resultado.map(libro => libro.nombre)).toEqual([
            "Cien años de soledad"
        ]);
    });

    test("devuelve un arreglo vacío si no hay coincidencias", () => {
        expect(obtenerLibrosPorAutor(libros, "Shakespeare")).toEqual([]);
    });
});
```

> [!NOTE]
> No me voy a quedar en mi uso habitual solo con estos sino que ademas voy a explorar todos los que trae porque se actualizan todo el tiempo

---

# Copilot CLI

* Se usa principalmente para obtener ayuda de copilot en la terminal

* Para Instalarlo usar

```
npm install -g @github/copilot
```

* Modo Interactivo

```
copilot
```

```
copilot -i "explicame el commando ls"
```

* Para Salir

```
/quit
```

* Puedo

```
Mira el proyecto y decime como por terminal lo configuro para poder ejecutar los tests
```

* Sesion

```
 ╭─╮╭─╮
  ╰─╯╰─╯  Copilot v1.0.80 uses AI.
  █ ▘▝ █  Check for mistakes.
   ▔▔▔▔ 

No copilot-instructions.md found. Run /init to generate.

Tip: /model
└ Select the AI model for this session (use 'auto' to let Copilot pick automatically). Use /config model to set the
  user default, '--repo'/'--local' to set the repo default, or 'plan'/'--plan' to set the plan-mode model.
Mira el proyecto y decime como por terminal lo configuro para poder ejecutar los tests
Voy a identificar el stack y los scripts de prueba para darte la configuración exacta.

Search "**/{package.json,README.md,pyproject.toml,requirements*.txt,*.sln,*.csproj,pom.xml,build.g… No matches found

Shell Inspect workspace contents and status 8 lines…
git --no-pager status --short; Get-ChildItem -Force | Select-Object Mode,Name

El proyecto es JavaScript plano, sin manifiesto de dependencias; reviso los tests para confirmar el ejecutor necesario.

Read libreria.tests.js 137 lines read
Read libreria.js 86 lines read

Thought for 2s
I need to start by explaining the terminal commands to the user: "npm init -y" and "npm install jest --save-dev" to set up Jest. They asked how to configure it to run, so I’ll need to provide clear instructions. They mentioned "decime como por terminal lo configuro," so I want to make my response straightforward. Also, maybe I should verify if Node is installed by running "node -v" first to check the version.

Shell Check Node.js and npm availability 3 lines…
node --version; npm --version

Usá Jest. Node.js ( v22.15.0 ) y npm ya están instalados.

cd C:\Cursos\GH-300\cursos\2026-08-Intec\clase-01\vscode-workspace
npm init -y
npm install --save-dev jest
npm pkg set scripts.test="jest"
npm test

Los tests están en  libreria.tests.js  y Jest los detecta automáticamente. Para ejecutarlos en modo observación:

npm test -- --watch
ejecuta eso comandos
Configuro Jest en el workspace y ejecuto la suite.

Shell Initialize npm, install Jest, and run tests 39 lines…
npm init -y; npm install --save-dev jest; npm pkg set scripts.test="jest"; npm test

Thought for 2s
I need to fix the testMatch configuration to ensure the test file names are set up correctly. The user asked me to execute those tests, but it seems like there are no tests running, so I should configure this properly, maybe updating the npm package with `jest.testMatch`. I’ll inspect the package.json for better clarity, then consider a patch for the config. I think I can set it to `/*.tests.js` before running `npm test`.

Jest quedó instalado, pero su patrón predeterminado no reconoce el nombre  libreria.tests.js ; ajusto la configuración para incluirlo y vuelvo a ejecutarlo.

Shell Configure Jest test discovery and rerun tests 50 lines…
npm pkg set 'jest.testMatch[0]=**/*.tests.js'; npm test

Thought for 2s
I need to finalize the succinct state, but there seems to be a mismatch with the expected result because 1813 is involved. There’s no request to fix it right now. I should consider mentioning that the created package may have the lock and node modules ignored. It's worth checking the git status, as a final inspection might be needed to see if the package contents were altered. However, validation is indicating that exact requirements and tests must be executed.

Jest quedó configurado: se crearon  package.json  y  package-lock.json , se instaló Jest y  npm test  ya detecta  libreria.tests.js .

La suite ejecutó 11 tests: 10 pasan y 1 falla. El fallo es una expectativa inconsistente: el rango  1605–1967  incluye también “Orgullo y prejuicio” (1813), pero el test no lo contempla.
```

* Puedo seguir la conversacion luego con

```
copilot --resume=<ID CONVERSACION>
```

---

# Comandos @

* Citar un agente o dar contexto
   * @workspace
      * Lo forzas a ver todo el proyecto entero
      * Consume mas tokens
   * @temninal / @terminalSelection
      * Agrega al contexto del chat los datos de la terminal

---

# Comando (#)

* Podemos usar la almohadilla # para referenciar archivos especificos
   * Podes mirar el archivo #file:libreria.tests.js y corregir la prueba que falla?
