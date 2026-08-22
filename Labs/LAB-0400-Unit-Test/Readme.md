# Módulo 04: Desarrollar pruebas unitarias usando herramientas de GitHub Copilot

## Introducción

Este módulo explora el uso de GitHub Copilot y GitHub Copilot Chat para crear pruebas unitarias. Los ejercicios brindan experiencia práctica creando proyectos de pruebas unitarias y ejecutándolas en Visual Studio Code.

## Objetivos de aprendizaje

Al finalizar este módulo, vas a poder:

- Crear pruebas unitarias usando las extensiones de GitHub Copilot y GitHub Copilot Chat para Visual Studio Code.
- Crear pruebas unitarias orientadas a casos límite y condiciones específicas usando las extensiones de GitHub Copilot y GitHub Copilot Chat.
- Usar Visual Studio Code, el SDK de .NET y la extensión C# Dev Kit para crear un proyecto de pruebas y verificar que tus pruebas compilan y se ejecutan correctamente.

## Prerrequisitos

- Se recomienda uno o más años de experiencia en desarrollo de software.
- Se recomienda experiencia desarrollando aplicaciones C# con Visual Studio Code y la extensión C# Dev Kit.
- Se requiere una suscripción activa a GitHub Copilot, ya sea en tu cuenta personal de GitHub o en una cuenta gestionada por una organización/empresa. GitHub Copilot Free (con límites de uso) alcanza para este lab.
- Tené en cuenta las condiciones del trial gratuito de GitHub Copilot: se solicita un medio de pago al registrarte; no se cobra nada hasta que termina el trial, salvo que lo canceles antes de que concluya el período de 30 días.
- Se recomienda experiencia usando las extensiones de GitHub Copilot y GitHub Copilot Chat para generar sugerencias de autocompletado y explicar código existente.

---

## Actividad 0: Preparar el entorno

1. [BROWSER] Navegá al siguiente link para descargar el zip con las apps de ejemplo:
   [LINK] https://github.com/MicrosoftLearning/mslearn-github-copilot-dev/raw/refs/heads/main/DownloadableCodeProjects/Downloads/AZ2007LabAppM4.zip

2. [WINDOWS] Navegá a tu carpeta de **Descargas**.

3. [WINDOWS] Hacé clic derecho sobre **AZ2007LabAppM4.zip**, y seleccioná **Extraer todo**.

4. [DIALOG] En el diálogo **Extraer carpetas comprimidas (en zip)**, marcá **Mostrar los archivos extraídos cuando termine** y seleccioná **Extraer**.

5. [WINDOWS] Anotá la ubicación de la carpeta extraída, y luego copiá la carpeta **AccelerateDevGHCopilot** a tu Escritorio de Windows.

   > La carpeta AccelerateDevGHCopilot contiene un conjunto de apps de ejemplo, incluyendo el proyecto de código AccelerateDevGHCopilot que se usa en este ejercicio.

6. [WINDOWS] Abrí la carpeta **AccelerateDevGHCopilot** en Visual Studio Code.

7. Expandí la carpeta **Numbers** y tomate un minuto para revisar el código de **PrimeService.cs**.

   > Es importante entender el código que vas a testear. La clase `PrimeService` tiene un único método público `IsPrime(int candidate)`. Este método verifica si un entero dado es un número primo:
   > - Si `candidate` < 2 → devuelve `false`.
   > - Si `candidate` ≥ 2 → verifica divisores desde 2 hasta la raíz cuadrada de `candidate` (un factor más grande sería múltiplo de un factor menor ya verificado).
   > - Si algún divisor lo divide exactamente → devuelve `false`.
   > - Si no se encuentra ningún divisor → devuelve `true`.

   Ya estás en condiciones de completar el ejercicio.

---

## Ejercicio 1: Examinar el enfoque de pruebas unitarias

### Actividad 1: Analizar el enfoque existente de pruebas unitarias

1. Expandí el proyecto **UnitTests** en la vista **SOLUTION EXPLORER**.

2. [WINDOWS] Presioná `Ctrl + Shift + P` (o `Cmd + Shift + P` en Mac), escribí **Copilot Chat: Open Chat** y presioná Enter.

3. Agregá los siguientes archivos al contexto del Chat:
   - En **Library.ApplicationCore**:
     - LoanService.cs
     - PatronService.cs
   - En **UnitTests**:
     - ExtendLoan.cs
     - ReturnLoan.cs
     - RenewMembership.cs
     - LoanFactory.cs
     - PatronFactory.cs

4. Ingresá el siguiente prompt en la vista Chat:

   ```
   @workspace Explain the approach to unit testing that's been implemented in this workspace.
   ```

   > 📝 Este prompt le pide a GitHub Copilot que explique el enfoque de pruebas unitarias en el contexto del workspace. Agregar los archivos relevantes al contexto del Chat mejora la respuesta.

5. Revisá la respuesta de GitHub Copilot. Deberías ver una descripción similar a:

   1. **Uso de Test Factories** — `PatronFactory` y `LoanFactory` generan objetos de prueba reutilizables y consistentes (ej. patrons con estados de membresía específicos, loans en distintos estados).
   2. **Mocking de dependencias** — **NSubstitute** mockea repositorios (`IPatronRepository`, `ILoanRepository`) para aislar el comportamiento de los servicios de las dependencias reales.
   3. **Testing orientado a servicios** — Las pruebas se enfocan en `PatronService` y `LoanService`, cubriendo casos exitosos, límite y de error.
   4. **Cobertura de pruebas integral** — Se testean todos los caminos posibles de la lógica de negocio.
   5. **Assertions para el comportamiento esperado** — Se validan valores de retorno, cambios de estado y manejo de errores.
   6. **Nombres de test descriptivos** — Atributos `Fact` con `DisplayName` clarifican cada escenario.
   7. **Foco en la lógica de negocio** — Las pruebas validan las reglas de negocio, no los detalles de implementación.
   8. **Simulación de errores** — Se simulan métodos de repositorio que devuelven `null` o lanzan excepciones.
   9. **Constantes para lógica configurable** — Constantes como `LoanService.ExtendByDays` se verifican en las pruebas.

### Actividad 2: Explorar los beneficios de este enfoque

1. Ingresá el siguiente prompt:

   ```
   @workspace What are the benefits of this approach to unit testing?
   ```

2. Revisá la respuesta de GitHub Copilot.

3. Podés continuar la conversación y pedir más detalle sobre aspectos específicos — por ejemplo, los beneficios de las test factories, el mocking de dependencias, o la estructura general de las pruebas.

4. Tomate un minuto para pensar cómo extenderías el enfoque existente para testear el proyecto **Library.Infrastructure**.

   > 📝 El proyecto Library.Infrastructure contiene clases de acceso a datos que interactúan con el sistema de archivos para cargar y guardar datos.

### Actividad 3: Planificar la extensión de las pruebas unitarias

1. Agregá los siguientes archivos al contexto del Chat (mismo conjunto que en la Actividad 1):
   - En **Library.ApplicationCore**: LoanService.cs, PatronService.cs
   - En **UnitTests**: ExtendLoan.cs, ReturnLoan.cs, RenewMembership.cs, LoanFactory.cs, PatronFactory.cs

2. Ingresá el siguiente prompt:

   ```
   @workspace How can I extend the `UnitTests` project to begin testing methods in the `Library.Infrastructure` project? Provide a process overview.
   ```

3. Revisá la respuesta. Deberías ver un resumen similar a:

   1. **Agregar referencia al proyecto** — Abrir `tests/UnitTests/UnitTests.csproj` y agregar una referencia a `Library.Infrastructure`.
   2. **Identificar métodos a testear** — por ejemplo, métodos de `LoanService`.
   3. **Crear clases de prueba** — por ejemplo, `LoanServiceTests.cs` en `tests/UnitTests`.
   4. **Escribir las pruebas unitarias** — usando xUnit y NSubstitute para el mocking.
   5. **Ejecutar las pruebas** — usando la terminal integrada o el Test Explorer; confirmar que las pruebas se detectan y pasan correctamente.

   > 💡 Usá el **modo Ask** de GitHub Copilot para investigar tu enfoque de testing. Usá las respuestas para planificar, desarrollar o extender tus pruebas unitarias.

---

## Ejercicio 2: Extender las pruebas unitarias para las clases de acceso a datos

### Introducción

El proyecto **Library.Infrastructure** contiene clases de acceso a datos que interactúan con el sistema de archivos:

- `JsonData` — carga y guarda datos JSON.
- `JsonLoanRepository` — implementa `ILoanRepository` usando `JsonData`.
- `JsonPatronRepository` — implementa `IPatronRepository` usando `JsonData`.

### Actividad 1: Usar el modo Agent para crear una nueva clase de prueba

1. En la vista Chat, seleccioná el botón **Set Mode** y luego seleccioná **Agent**.

   > ℹ️ En modo Agent, GitHub Copilot puede planificar el trabajo de forma autónoma, determinar los archivos/contexto relevantes, editar tu código e invocar herramientas. Puede realizar múltiples requests premium por tarea según la complejidad.
   >
   > 📝 El modo Agent solo está disponible en Visual Studio Code. En otros entornos, usá el modo Chat para tareas similares.

2. Ingresá el siguiente prompt:

   ```
   Add `Infrastructure\JsonLoanRepository` folders to the UnitTests project. Create a class file named `GetLoan.cs` in the `JsonLoanRepository` folder and create a stub class named `GetLoan`. Add a reference to the Library.Infrastructure project inside UnitTests.csproj.
   ```

   > 📝 Esto crea la siguiente estructura de carpetas:
   > ```
   > UnitTests
   > └── Infrastructure
   >     └── JsonLoanRepository
   >         └── GetLoan.cs
   > ```
   > También agrega una referencia al proyecto `Library.Infrastructure` dentro de `UnitTests.csproj`.

3. [DIALOG] Si te pide permiso para editar archivos sensibles, seleccioná **Allow**.

4. Revisá la vista Chat. El agente muestra mensajes de estado a medida que completa las tareas; puede pausar y pedir confirmación antes de crear la estructura de carpetas.

5. [DIALOG] Si el agente pide permiso para ejecutar un comando `mkdir` en la terminal, seleccioná **Allow**.

6. Seleccioná **Continue**. Copilot entonces:
   - Ejecuta `mkdir` para crear `Infrastructure\JsonLoanRepository`.
   - Crea `GetLoan.cs` en esa carpeta.

7. Confirmá que:
   - `UnitTests.csproj` ahora referencia `Library.Infrastructure.csproj`.
   - `GetLoan.cs` existe en `Infrastructure\JsonLoanRepository`.

8. En la vista Chat, seleccioná **Keep** para aceptar todos los cambios.

9. En **SOLUTION EXPLORER**, expandí `Infrastructure\JsonLoanRepository` y confirmá que la estructura coincide con:

   ```
   UnitTests
   └── Infrastructure
       └── JsonLoanRepository
           └── GetLoan.cs
   ```

---

## Ejercicio 3: Crear pruebas unitarias usando el modo Edit

### Actividad 1: Revisar la clase JsonLoanRepository

1. En la vista Chat, seleccioná **Set Mode** y luego seleccioná **Edit**.

   > 📝 El modo Edit actualiza los archivos seleccionados; las respuestas aparecen como sugerencias de código en el editor.

2. Abrí **JsonLoanRepository.cs** (ubicado en `src/Library.Infrastructure/Data/`).

3. Revisá la clase:

   ```csharp
   using Library.ApplicationCore;
   using Library.ApplicationCore.Entities;

   namespace Library.Infrastructure.Data;

   public class JsonLoanRepository : ILoanRepository
   {
       private readonly JsonData _jsonData;

       public JsonLoanRepository(JsonData jsonData)
       {
           _jsonData = jsonData;
       }

       public async Task<Loan?> GetLoan(int id)
       {
           await _jsonData.EnsureDataLoaded();
           foreach (Loan loan in _jsonData.Loans!)
           {
               if (loan.Id == id)
               {
                   Loan populated = _jsonData.GetPopulatedLoan(loan);
                   return populated;
               }
           }
           return null;
       }

       public async Task UpdateLoan(Loan loan)
       {
           Loan? existingLoan = null;
           foreach (Loan l in _jsonData.Loans!)
           {
               if (l.Id == loan.Id)
               {
                   existingLoan = l;
                   break;
               }
           }
           if (existingLoan != null)
           {
               existingLoan.BookItemId = loan.BookItemId;
               existingLoan.PatronId = loan.PatronId;
               existingLoan.LoanDate = loan.LoanDate;
               existingLoan.DueDate = loan.DueDate;
               existingLoan.ReturnDate = loan.ReturnDate;
               await _jsonData.SaveLoans(_jsonData.Loans!);
               await _jsonData.LoadData();
           }
       }
   }
   ```

   > Notas:
   > - La clase tiene dos métodos: `GetLoan` y `UpdateLoan`.
   > - Usa un objeto `JsonData` para cargar/guardar datos de préstamos.
   > - `GetLoan` recibe un ID de préstamo, llama a `_jsonData.EnsureDataLoaded()`, busca en `_jsonData.Loans`, y devuelve un préstamo poblado o `null`.

### Actividad 2: Crear los campos y el constructor de la clase de prueba

1. Abrí **GetLoan.cs** y seleccioná la clase `GetLoan`.

2. Agregá al contexto del Chat:
   - Library.ApplicationCore: LoanService.cs
   - Library.Infrastructure: JsonData.cs, JsonLoanRepository.cs
   - UnitTests: ReturnLoan.cs, LoanFactory.cs

3. Ingresá el prompt:

   ```
   #codebase Create fields and a class constructor for the `GetLoan.cs` file. The class will be used to create unit tests for the GetLoan method in the `JsonLoanRepository.cs` file. Create the following private readonly fields: `_mockLoanRepository`, `_jsonLoanRepository`, `_configuration`, and `_jsonData`. Instantiate the fields in the `GetLoanTest` constructor. Use `ConfigurationBuilder` to create a `_configuration` object that can be used to instantiate the JsonData object.
   ```

4. Revisá la sugerencia (debería ser similar a):

   ```csharp
   using NSubstitute;
   using Library.ApplicationCore;
   using Library.ApplicationCore.Entities;
   using Library.ApplicationCore.Interfaces;
   using Library.Infrastructure.Data;
   using Microsoft.Extensions.Configuration;

   namespace UnitTests.Infrastructure.JsonLoanRepository;

   public class GetLoanTest
   {
       private readonly ILoanRepository _mockLoanRepository;
       private readonly JsonLoanRepository _jsonLoanRepository;
       private readonly IConfiguration _configuration;
       private readonly JsonData _jsonData;

       public GetLoanTest()
       {
           _mockLoanRepository = Substitute.For<ILoanRepository>();
           _configuration = new ConfigurationBuilder()
               .AddJsonFile("appsettings.json")
               .Build();
           _jsonData = new JsonData(_configuration);
           _jsonLoanRepository = new JsonLoanRepository(_jsonData);
       }
       // Add test methods here
   }
   ```

5. En la vista Chat, seleccioná **Keep** para aceptar todos los cambios.

6. Revisá y corregí los siguientes posibles problemas:
   - Si hay conflicto de nombres entre el namespace `UnitTests.Infrastructure.JsonLoanRepository` y el tipo `JsonLoanRepository`, renombrá el namespace (seguí el patrón usado en `ReturnLoan.cs` / `RenewMembership.cs`).
   - Si `ILoanRepository` no se reconoce, agregá `using Library.ApplicationCore;`.
   - Si `_configuration` no se instancia correctamente, simplificá a `_configuration = new ConfigurationBuilder().Build();`.
   - Si se sugirió `using Library.ApplicationCore.Interfaces`, eliminalo.

7. Referencia corregida:

   ```csharp
   using NSubstitute;
   using Library.ApplicationCore;
   using Library.ApplicationCore.Entities;
   using Library.Infrastructure.Data;
   using Microsoft.Extensions.Configuration;

   namespace UnitTests.Infrastructure.JsonLoanRepositoryTests;

   public class GetLoanTest
   {
       private readonly ILoanRepository _mockLoanRepository;
       private readonly JsonLoanRepository _jsonLoanRepository;
       private readonly IConfiguration _configuration;
       private readonly JsonData _jsonData;

       public GetLoanTest()
       {
           _mockLoanRepository = Substitute.For<ILoanRepository>();
           _configuration = new ConfigurationBuilder().Build();
           _jsonData = new JsonData(_configuration);
           _jsonLoanRepository = new JsonLoanRepository(_jsonData);
       }
   }
   ```

### Actividad 3: Crear una prueba unitaria para encontrar un préstamo

1. Agregá al contexto del Chat:
   - Library.ApplicationCore: LoanService.cs
   - Library.Console: Loans.json
   - Library.Infrastructure: JsonData.cs, JsonLoanRepository.cs
   - UnitTests: ReturnLoan.cs, LoanFactory.cs

2. Seleccioná el contenido de `GetLoan.cs` y luego ingresá el prompt:

   ```
   @workspace Update the selection to include a unit test for the `JsonLoanRepository.GetLoan` method. The unit test should test the case where a loan ID is found in the data. Use `_mockLoanRepository` to arrange the expected return loan. Use `_jsonLoanRepository` to return an actual loan. Asserts should verify that the return loan ID matches the expected loan ID. Use a loan ID that exists in the `Loans.json` file.
   ```

3. Revisá la sugerencia:

   ```csharp
   using NSubstitute;
   using Library.ApplicationCore;
   using Library.ApplicationCore.Entities;
   using Library.Infrastructure.Data;
   using Microsoft.Extensions.Configuration;
   using Xunit;

   namespace UnitTests.Infrastructure.JsonLoanRepositoryTests;

   public class GetLoanTest
   {
       private readonly ILoanRepository _mockLoanRepository;
       private readonly JsonLoanRepository _jsonLoanRepository;
       private readonly IConfiguration _configuration;
       private readonly JsonData _jsonData;

       public GetLoanTest()
       {
           _mockLoanRepository = Substitute.For<ILoanRepository>();
           _configuration = new ConfigurationBuilder().Build();
           _jsonData = new JsonData(_configuration);
           _jsonLoanRepository = new JsonLoanRepository(_jsonData);
       }

       [Fact(DisplayName = "JsonLoanRepository.GetLoan: Returns loan when loan ID is found")]
       public async Task GetLoan_ReturnsLoanWhenLoanIdIsFound()
       {
           // Arrange
           var loanId = 1; // Use a loan ID that exists in the Loans.json file
           var expectedLoan = new Loan
           {
               Id = loanId,
               BookItemId = 17,
               PatronId = 22,
               LoanDate = DateTime.Parse("2023-12-08T00:40:43.1808862"),
               DueDate = DateTime.Parse("2023-12-22T00:40:43.1808862"),
               ReturnDate = null
           };
           _mockLoanRepository.GetLoan(loanId).Returns(expectedLoan);

           // Act
           var actualLoan = await _jsonLoanRepository.GetLoan(loanId);

           // Assert
           Assert.NotNull(actualLoan);
           Assert.Equal(expectedLoan.Id, actualLoan?.Id);
       }
   }
   ```

4. En la vista Chat, seleccioná **Keep** para aceptar todos los cambios.

   > 📝 Si `Loan` no se reconoce, asegurate de tener `using Library.ApplicationCore.Entities;` al inicio de `GetLoan.cs`.

5. Compilá la solución **AccelerateDevGitHubCopilot** y confirmá que no haya errores.

### Actividad 4: Usar autocompletado para crear una prueba de préstamo no encontrado

1. Creá una línea en blanco después de `GetLoan_ReturnsLoanWhenLoanIdIsFound`.

2. Aceptá las sugerencias de autocompletado para generar un nuevo método de prueba.

   > 📝 Las sugerencias de código pueden aparecer línea por línea — puede que tengas que presionar `Tab` o `Enter` varias veces para completar la sugerencia.

3. Revisá el resultado (debería parecerse a):

   ```csharp
   [Fact(DisplayName = "JsonLoanRepository.GetLoan: Returns null when ID is not found")]
   public async Task GetLoan_ReturnsNullWhenIdIsNotFound()
   {
       // Arrange
       var loanId = 999; // Loan ID that does not exist in Loans.json
       _mockLoanRepository.GetLoan(loanId).Returns((Loan?)null);

       // Act
       var actualLoan = await _jsonLoanRepository.GetLoan(loanId);

       // Assert
       Assert.Null(actualLoan);
   }
   ```

   > 📝 El autocompletado puede mockear un préstamo esperado que en realidad no hace falta — podés eliminar ese código, pero el `loanId` debe ser uno que no exista en `Loans.json`.

4. Confirmá que la prueba "devuelve null cuando el ID no se encuentra" use un `loanId` que no esté en el set de datos.

### Actividad 5: Configurar el acceso a los datos JSON para las pruebas

1. Las pruebas unitarias necesitan acceso a los archivos de datos JSON (ubicados en `Library.Console\Json`). Agregá lo siguiente a `UnitTests.csproj`:

   ```xml
   <ItemGroup>
       <None Include="..\..\src\Library.Console\Json\**\*">
           <Link>Json\%(RecursiveDir)%(FileName)%(Extension)</Link>
           <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
       </None>
   </ItemGroup>
   ```

   > 📝 Esto asegura que los archivos de datos JSON se copien al directorio de salida cuando se ejecutan las pruebas.

---

## Ejercicio 4: Ejecutar las pruebas unitarias

### Actividad: Ejecutar y validar las pruebas unitarias

1. Asegurate de tener **GetLoan.cs** abierto en el editor.

2. Compilá la solución: hacé clic derecho sobre **AccelerateDevGitHubCopilot** y seleccioná **Build**. Confirmá que no haya errores.

3. Notá el botón verde de "play" a la izquierda de cada método de prueba.

4. [WINDOWS] Abrí la vista **Test Explorer** (ícono de matraz en la Activity Bar, etiquetado "Testing").

   > El Test Explorer es una vista de árbol con todos los casos de prueba del workspace — desde ahí podés ejecutar, debuguear y ver los resultados.

5. Expandí **UnitTests** y los nodos correspondientes hasta ubicar `GetLoanTest`.

6. Ejecutá **JsonLoanRepository.GetLoan: Returns loan when loan ID is found**.

7. Confirmá que el resultado aparece tanto en el Test Explorer como en el editor, con un tilde verde (passed).

8. Desde el editor de código, ejecutá **JsonLoanRepository.GetLoan: Returns null when loan ID is not found** (seleccioná el botón verde de "play" junto al método de prueba).

9. Confirmá que ambas pruebas muestran un tilde verde en el Test Explorer.

---

## Repaso

¡Felicitaciones! Completaste este ejercicio y aprendiste a usar GitHub Copilot para acelerar el desarrollo de pruebas unitarias.

Resumen de lo logrado:

- Examinaste el enfoque existente de pruebas unitarias usando el **modo Ask**.
- Usaste el **modo Agent** para crear carpetas del proyecto y una nueva clase de prueba automáticamente.
- Usaste el **modo Edit** para generar pruebas unitarias con los campos y el constructor correctos.
- Usaste el **autocompletado** de GitHub Copilot para crear pruebas adicionales.
- Ejecutaste y validaste tus pruebas unitarias usando el **Test Explorer** de Visual Studio Code.

## ¿Qué sigue?

En este ejercicio aprendiste a usar GitHub Copilot para acelerar el desarrollo de pruebas unitarias en una aplicación C#. Usaste la vista Chat en modo Ask, Agent y Edit. Usaste el modo Ask para examinar el enfoque existente de pruebas unitarias, el modo Agent para crear carpetas del proyecto y una nueva clase de prueba, y el modo Edit para crear las pruebas unitarias. También usaste el autocompletado de código de GitHub Copilot para crear una prueba unitaria adicional.

## Limpieza

Ahora que terminaste el ejercicio, tomate un minuto para verificar que no hayas hecho cambios en tu cuenta de GitHub o en tu suscripción a GitHub Copilot que no quieras conservar. Si hiciste algún cambio, revertilo ahora.

