---
title: Formas de ejecutar un Q# programa
description: Información general de las diferentes formas de ejecutar Q# programas. Desde el símbolo del sistema, Q# cuadernos de Jupyter Notebook y programas host clásico en Python o en un lenguaje .net.
author: gillenhaalb
ms.author: a-gibec
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2c5bdebc826bb85f6d7e0ade6232e15e29e8fb19
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231696"
---
# <a name="ways-to-run-a-no-locq-program"></a>Formas de ejecutar un Q# programa

Uno de los mayores puntos fuertes del kit de desarrollo de Quantum es su flexibilidad en plataformas y entornos de desarrollo.
Sin embargo, esto también significa que los nuevos Q# usuarios se pueden confundir o saturar mediante las numerosas opciones que se encuentran en la [Guía de instalación](xref:microsoft.quantum.install).
En esta página, se explica lo que ocurre cuando Q# se ejecuta un programa y se comparan las distintas formas en que los usuarios pueden hacerlo.

Una distinción principal es que se Q# puede ejecutar:
- como aplicación independiente, donde Q# es el único lenguaje implicado y el programa se invoca directamente. En realidad, dos métodos se encuentran en esta categoría:
  - la interfaz de la línea de comandos
  - Q# Cuadernos de Jupyter Notebook
- con un *programa host* adicional, escrito en Python o en un lenguaje .net (por ejemplo, C# o F #), que, a continuación, invoca el programa y puede procesar aún más los resultados devueltos.

Para comprender mejor estos procesos y sus diferencias, se considera un Q# programa sencillo y se comparan las formas en que se pueden ejecutar.

## <a name="basic-no-locq-program"></a>Q#Programa básico

Un programa Quantum básico puede constar de la preparación de una qubit en una superposición de Estados $ \ket {0} $ y $ \ket {1} $, la medición y la devolución del resultado, que será aleatoriamente uno de estos dos Estados con la misma probabilidad.
En realidad, este proceso es el núcleo de la guía de inicio rápido del [generador de números aleatorios de Quantum](xref:microsoft.quantum.quickstarts.qrng) .

En Q# , esto se realizaría mediante el código siguiente:

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

Sin embargo, este código no puede ejecutarse por sí solo Q# .
Para ello, debe componer el cuerpo de una [operación](xref:microsoft.quantum.qsharp.operationsandfunctions), que se ejecuta cuando se llama---directamente o mediante otra operación. Por lo tanto, puede escribir una operación de la siguiente forma:
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
Ha definido una operación, `MeasureSuperposition` , que no toma ninguna entrada y devuelve un valor de tipo [result](xref:microsoft.quantum.qsharp.typesystem-index#available-types).

Además de las operaciones, Q# también permite encapsular cálculos deterministas en funciones. Aparte de la garantía del determinismo que implica que los cálculos que actúan en qubits deben encapsularse en operaciones en lugar de funciones, hay poca diferencia entre las operaciones y la función. Hacemos referencia a ellos colectivamente como *Invocables*.

### <a name="callable-defined-in-a-no-locq-file"></a>Se puede llamar en un Q# archivo

La llamada invocativa es precisamente lo que se llama y ejecuta Q# .
Sin embargo, requiere algunas adiciones más para incluir un `*.qs` Q# archivo completo.

Todos los Q# tipos y llamadas (que se definen y los intrínsecos al lenguaje) se definen dentro de los *espacios de nombres*, que proporcionan cada nombre completo al que se puede hacer referencia a continuación.

Por ejemplo, las [`H`](xref:Microsoft.Quantum.Intrinsic.H) [`MResetZ`](xref:Microsoft.Quantum.Measurement.MResetZ) operaciones y se encuentran en los [`Microsoft.Quantum.Instrinsic`](xref:Microsoft.Quantum.Intrinsic) espacios de [`Microsoft.Quantum.Measurement`](xref:Microsoft.Quantum.Measurement) nombres y (parte de las [ Q# bibliotecas estándar](xref:microsoft.quantum.libraries.standard.intro)).
Como tal, siempre se les puede llamar a través de sus nombres *completos* `Microsoft.Quantum.Intrinsic.H(<qubit>)` y `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` , pero siempre esto provocaría un código muy saturado.

En su lugar, `open` las instrucciones permiten hacer referencia a las llamadas con una abreviatura más concisa, como hemos hecho en el cuerpo de la operación anterior.
Q#Por lo tanto, el archivo completo que contiene nuestra operación consistiría en definir nuestro propio espacio de nombres, abriendo los espacios de nombres de los que se llamaron en la operación y, a continuación, nuestra operación:

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

> [!NOTE]
> También se pueden asignar *alias* a los espacios de nombres cuando se abren, lo que puede resultar útil si se producen conflictos entre los nombres de tipo o los tipos en dos espacios de nombres.
> Por ejemplo, en su lugar podríamos usar `open Microsoft.Quantum.Instrinsic as NamespaceWithH;` anteriormente y, a continuación, llamar a `H` mediante `NamespaceWithH.H(<qubit>)` .

> [!NOTE]
> Una excepción a todo esto es el [`Microsoft.Quantum.Core`](xref:Microsoft.Quantum.Core) espacio de nombres, que siempre se abre automáticamente.
> Por lo tanto, [`Length`](xref:Microsoft.Quantum.Core.Length) se pueden usar directamente llamadas como siempre.

### <a name="running-on-target-machines"></a>Ejecutar en máquinas de destino

Ahora se borra el modelo de ejecución general de un Q# programa.

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

En primer lugar, el llamador específico que se va a ejecutar tiene acceso a cualquier otro tipo que se pueda llamar y que se haya definido en el mismo espacio de nombres.
También tiene acceso a los de cualquiera de las [ Q# bibliotecas](xref:microsoft.quantum.libraries), pero se debe hacer referencia a ellos mediante su nombre completo o mediante el uso de `open` instrucciones descritas anteriormente.

A continuación, se puede llamar a en un *[equipo de destino](xref:microsoft.quantum.machines)*.
Estas máquinas de destino pueden ser hardware de Quantum real o varios simuladores disponibles como parte de QDK.
Para nuestros fines aquí, el equipo de destino más útil es una instancia del [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator` , que calcula el comportamiento del programa como si se estuviera ejecutando en un equipo Quantum sin ruido.

Hasta ahora, hemos descrito lo que ocurre cuando Q# se ejecuta una función invocable específica.
Con independencia de si Q# se usa en una aplicación independiente o con un programa host, este proceso general es más o menos el mismo---, por lo tanto, la flexibilidad de QDK.
Por lo tanto, las diferencias entre las formas de llamar al kit de desarrollo de Quantum se revelan en el *modo* en que Q# se ejecuta la llamada para ejecutarse y en qué manera se devuelven los resultados.
Más concretamente, las diferencias giran en torno a:

- Que indica qué Q# se puede llamar para ejecutarse
- Cómo se proporcionan los argumentos que se pueden llamar
- Especificar el equipo de destino en el que se va a ejecutar
- Cómo se devuelven los resultados

En primer lugar, se describe cómo hacerlo con la Q# aplicación independiente desde el símbolo del sistema y, a continuación, se sigue usando los programas host de Python y C#.
Nos reservamos la aplicación independiente de Q# cuadernos de Jupyter Notebook por última vez, porque a diferencia de las tres primeras, su funcionalidad principal no se centra en un Q# archivo local.

> [!NOTE]
> Aunque no se muestra en estos ejemplos, una diferencia entre los métodos de ejecución es que todos los mensajes impresos desde dentro del Q# programa (por [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) [`DumpMachine`](xref:Microsoft.Quantum.Diagnostics.DumpMachine) ejemplo, o, por ejemplo) siempre se imprimirán en la consola correspondiente.

## <a name="no-locq-from-the-command-prompt"></a>Q# desde el símbolo del sistema
Una de las maneras más fáciles de empezar a escribir Q# programas es evitar preocuparse por archivos independientes y un segundo idioma.
El uso de Visual Studio Code o Visual Studio con la extensión QDK permite un flujo de trabajo sin problemas en el que se ejecutan Q# llamadas desde un solo Q# archivo.

Para ello, se ejecutará el programa en última instancia.

```dotnetcli
dotnet run
```

en el símbolo del sistema.
El flujo de trabajo más sencillo es cuando la ubicación del directorio del terminal es igual que el Q# archivo, que se puede controlar fácilmente junto Q# con la edición de archivos mediante el terminal integrado en vs Code, por ejemplo.
Sin embargo, el [ `dotnet run` comando](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) acepta numerosas opciones y el programa también se puede ejecutar desde una ubicación diferente, simplemente proporcionando `--project <PATH>` con la ubicación del Q# archivo.


### <a name="add-entry-point-to-no-locq-file"></a>Agregar punto de entrada a Q# archivo

La mayoría Q# de los archivos contendrán más de una a la que se puede llamar, por lo que es necesario dejar que el compilador sepa *qué* llamadas se ejecutan cuando se proporciona el `dotnet run` comando.
Esto se hace con un simple cambio en el Q# propio archivo: 
    - Agregue una línea `@EntryPoint()` que preceda directamente a la que se puede llamar.

Por lo tanto, el archivo anterior se convertiría en
```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // for the H operation
    open Microsoft.Quantum.Measurement;   // for MResetZ

    @EntryPoint()
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }
}
```

Ahora, una llamada de `dotnet run` desde el símbolo del sistema conduce a `MeasureSuperposition` ejecutarse y, a continuación, el valor devuelto se imprime directamente en el terminal.
Por lo tanto, verá `One` o `Zero` imprimirá. 

Tenga en cuenta que no importa si tiene más llamadas definidas debajo, solo se `MeasureSuperposition` ejecutará.
Además, no hay ningún problema si su llamador incluye [comentarios de documentación](xref:microsoft.quantum.qsharp.comments#documentation-comments) antes de su declaración, el `@EntryPoint()` atributo se puede colocar simplemente encima de ellos.

### <a name="callable-arguments"></a>Argumentos Invocables

Hasta ahora, solo hemos considerado una operación que no toma ninguna entrada.
Supongamos que deseamos realizar una operación similar, pero en varios qubits---el número de que se proporciona como argumento.
Este tipo de operación podría escribirse como
```qsharp
    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {              // allocate a register of n qubits
            ApplyToEach(H, qubits);              // apply H to each qubit in the register
            return ForEach(MResetZ, qubits);     // perform MResetZ on each qubit, returns the resulting array
        }
    }
```
donde el valor devuelto es una matriz de los resultados de la medición.
Tenga en cuenta que [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) y [`ForEach`](xref:Microsoft.Quantum.Arrays.ForEach) se encuentran en los [`Microsoft.Quantum.Canon`](xref:Microsoft.Quantum.Canon) espacios de [`Microsoft.Quantum.Arrays`](xref:Microsoft.Quantum.Arrays) nombres y, que requieren `open` instrucciones adicionales para cada uno.

Si movemos el `@EntryPoint()` atributo para que preceda a esta nueva operación (tenga en cuenta que solo puede haber una línea de este tipo en un archivo), intentar ejecutarlo simplemente `dotnet run` genera un mensaje de error que indica qué opciones de línea de comandos adicionales son necesarias y cómo expresarlos.

El formato general de la línea de comandos es realmente `dotnet run [options]` , y los argumentos que se pueden llamar se proporcionan allí.
En este caso, falta el argumento `n` y se muestra que es necesario proporcionar la opción `-n <n>` . `MeasureSuperpositionArray` `n=4` Por lo tanto, para ejecutar para qubits, usamos

```dotnetcli
dotnet run -n 4
```

producir una salida similar a

```output
[Zero,One,One,One]
```

Esto se extiende a varios argumentos.

> [!NOTE]
> `camelCase`El compilador modifica ligeramente los nombres de argumento definidos en para que se acepten como Q# entradas. Por ejemplo, si en lugar de `n` , usamos el nombre `numQubits` anterior, esta entrada se proporcionaría en la línea de comandos mediante en `--num-qubits 4` lugar de `-n 4` .

El mensaje de error también proporciona otras opciones que se pueden usar, incluida la forma de cambiar la máquina de destino.

### <a name="different-target-machines"></a>Distintos equipos de destino

Dado que las salidas de nuestras operaciones hasta ahora han sido los resultados esperados de su acción en qubits reales, está claro que el equipo de destino predeterminado de la línea de comandos es el simulador de Quantum de estado completo, `QuantumSimulator` .
Sin embargo, podemos indicar a las llamadas que se ejecuten en un equipo de destino específico con la opción `--simulator` (o la abreviatura `-s` ).

Por ejemplo, podríamos ejecutarlo en [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) :

```dotnetcli
dotnet run -n 4 -s ResourcesEstimator
```

A continuación, la salida impresa es

```output
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

Para más información sobre lo que indican estas métricas, consulte [estimación de recursos: métricas notificadas](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).

### <a name="command-line-run-summary"></a>Resumen de ejecución de línea de comandos
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-no-locq-dotnet-run-options"></a>Opciones no Q# `dotnet run` disponibles

Como se mencionó brevemente anteriormente con la `--project` opción, el [ `dotnet run` comando](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) también acepta opciones no relacionadas con los argumentos a los que se Q# puede llamar.
Si se proporcionan ambos tipos de opciones, `dotnet` se deben proporcionar primero las opciones específicas de, seguida de un delimitador `--` y, a continuación, las Q# Opciones específicas de.
Por ejemplo, la especificación de una ruta de acceso junto con un número qubits para la operación anterior se ejecutaría a través de `dotnet run --project <PATH> -- -n <n>` .

## <a name="no-locq-with-host-programs"></a>Q# con programas host

Con nuestro Q# archivo a mano, una alternativa a llamar a una operación o a una función directamente desde el símbolo del sistema es usar un *programa host* en otro idioma clásico. En concreto, esto se puede hacer con Python o con un lenguaje .NET como C# o F # (por motivos de brevedad, solo se detallará C# aquí).
Se requiere un poco más de configuración para habilitar la interoperabilidad, pero esos detalles se pueden encontrar en las [guías de instalación](xref:microsoft.quantum.install).

En pocas palabras, la situación incluye ahora un archivo de programa host (por ejemplo, `*.py` o `*.cs` ) en la misma ubicación que el Q# archivo.
Ahora es el programa *host* que se ejecuta y mientras se está ejecutando, puede llamar a las Q# operaciones y funciones específicas desde el Q# archivo.
El núcleo de la interoperabilidad se basa en el Q# compilador, por lo que el contenido del Q# archivo es accesible para el programa host, de modo que se pueda llamar.

Una de las principales ventajas de usar un programa host es que los datos clásicos devueltos por el Q# programa se pueden procesar posteriormente en el idioma del host.
Esto puede constar de un procesamiento de datos avanzado (por ejemplo, algo que no se puede realizar internamente en Q# ) y, a continuación, llamar a acciones adicionales en Q# función de los resultados, o algo tan sencillo como trazar los Q# resultados.

Aquí se muestra el esquema general y se describen las implementaciones específicas para Python y C# a continuación. Puede encontrar un ejemplo de uso de un programa host de F # en los [ejemplos de interoperabilidad de .net](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> El `@EntryPoint()` atributo usado para Q# las aplicaciones no se puede usar con programas host.
> Se producirá un error si está presente en el Q# archivo al que llama un host. 

Para trabajar con distintos programas host, no es necesario realizar ningún cambio en un `*.qs` Q# archivo.
Todas las implementaciones del programa host siguientes funcionan con el mismo Q# archivo:

```qsharp
namespace NamespaceName {
    open Microsoft.Quantum.Intrinsic;     // contains H
    open Microsoft.Quantum.Measurement;   // MResetZ
    open Microsoft.Quantum.Canon;         // ApplyToEach
    open Microsoft.Quantum.Arrays;        // ForEach

    operation MeasureSuperposition() : Result {
        using (q = Qubit()) { 
            H(q);
            return MResetZ(q);
        }
    }

    operation MeasureSuperpositionArray(n : Int) : Result[] {
        using (qubits = Qubit[n]) {  
            ApplyToEach(H, qubits); 
            return ForEach(MResetZ, qubits);    
        }
    }
}
```

Seleccione la pestaña correspondiente al idioma de su host de interés.

### <a name="python"></a>[Python](#tab/tabid-python)
Un programa host de Python se construye de la siguiente manera:
1. Importe el `qsharp` módulo, que registra el cargador de módulos para la Q# interoperabilidad. 
    Esto permite Q# que los espacios de nombres aparezcan como módulos de Python, desde los que podemos "importar" a los que se puede Q# llamar.
    Tenga en cuenta que técnicamente no son las llamadas Q# que se importan, sino códigos auxiliares de Python que permiten llamar a ellos.
    Estos se comportan como objetos de clases de Python. Usamos métodos en estos objetos para especificar las máquinas de destino a las que se enviará la operación al ejecutar el programa.

2. Importe las invocaciones Q# que llamaremos directamente---en este caso, `MeasureSuperposition` y `MeasureSuperpositionArray` .
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    Con el `qsharp` módulo importado, también puede importar llamadas directamente desde los espacios de nombres de la Q# biblioteca.

3. Entre cualquier otro código de Python, ahora puede llamar a esas llamadas en máquinas de destino específicas y asignar sus retornos a variables (si devuelven un valor) para su uso posterior.

#### <a name="specifying-target-machines"></a>Especificar equipos de destino
La llamada a una operación que se va a ejecutar en un equipo de destino específico se realiza a través de diferentes métodos de Python en el objeto importado.
Por ejemplo, `.simulate(<args>)` , utiliza `QuantumSimulator` para ejecutar la operación, mientras que `.estimate_resources(<args>)` lo hace en `ResourcesEstimator` .

#### <a name="passing-inputs-to-q"></a>Pasar entradas a Q\#
Los argumentos de la que se Q# puede llamar deben proporcionarse en forma de argumento de palabra clave, donde la palabra clave es el nombre del argumento en la definición que se Q# puede llamar.
Es decir, `MeasureSuperpositionArray.simulate(n=4)` es válido, mientras que `MeasureSuperpositionArray.simulate(4)` produciría un error.

Por lo tanto, el programa host de Python 

```python
import qsharp
from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray

single_qubit_result = MeasureSuperposition.simulate()
single_qubit_resources = MeasureSuperposition.estimate_resources()

multi_qubit_result = MeasureSuperpositionArray.simulate(n=4)
multi_qubit_resources = MeasureSuperpositionArray.estimate_resources(n=4)

print('Single qubit:\n' + str(single_qubit_result))
print(single_qubit_resources)

print('\nMultiple qubits:\n' + str(multi_qubit_result))
print(multi_qubit_resources)
```

da como resultado una salida similar a la siguiente:

```output
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

#### <a name="using-no-locq-code-from-other-projects-or-packages"></a>Usar Q# código de otros proyectos o paquetes

De forma predeterminada, el `import qsharp` comando carga todos los `.qs` archivos de la carpeta actual y hace que sus Q# operaciones y funciones estén disponibles para su uso dentro del script de Python.

Para cargar Q# código desde otra carpeta, la [ `qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) se puede usar para agregar una referencia a un `.csproj` archivo para un Q# proyecto (es decir, un proyecto que haga referencia a `Microsoft.Quantum.Sdk` ).
Este comando compilará todos `.qs` los archivos de la carpeta que contengan `.csproj` y sus subcarpetas. También cargará de forma recursiva los paquetes a los que se hace referencia a través `PackageReference` de o los Q# proyectos a los que se hace referencia a través `ProjectReference` de en ese `.csproj` archivo.

Por ejemplo, el siguiente código de Python importa un proyecto externo, haciendo referencia a su ruta de acceso relativa a la carpeta actual, e invoca una de sus Q# operaciones:

```python
import qsharp
qsharp.projects.add("../qrng/Qrng.csproj")
from Qrng import SampleQuantumRandomNumberGenerator
print(f"Qrng result: {SampleQuantumRandomNumberGenerator.simulate()}")
```

Esto resulta en una salida similar a la siguiente:

```output
Adding reference to project: ../qrng/Qrng.csproj
Qrng result: 0
```

Para cargar paquetes externos que contienen Q# código, use la [ `qsharp.packages` API](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages).

Si el Q# código de la carpeta actual depende de los proyectos o paquetes externos, es posible que vea errores durante `import qsharp` la ejecución, ya que las dependencias no se han cargado todavía.
Para cargar los paquetes o proyectos externos necesarios Q# durante el `import qsharp` comando, asegúrese de que la carpeta con el script de Python contiene un `.csproj` archivo al que hace referencia `Microsoft.Quantum.Sdk` . En ese `.csproj` , agregue la propiedad `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` a `<PropertyGroup>` . Esto le indicará Q# Cómo cargar de forma recursiva `ProjectReference` los `PackageReference` elementos o encontrados en ese elemento `.csproj` durante el `import qsharp` comando.

Por ejemplo, este es un `.csproj` archivo simple que hace que se Q# cargue el `Microsoft.Quantum.Chemistry` paquete automáticamente:

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> Actualmente, esta `<IQSharpLoadAutomatically>` propiedad personalizada es necesaria para los hosts de Python, pero en el futuro, esto puede convertirse en el comportamiento predeterminado de un `.csproj` archivo ubicado en la misma carpeta que el script de Python.

> [!NOTE]
> Actualmente el `<QsharpCompile>` valor de `.csproj` se omite en los hosts de Python y `.qs` `.csproj` se cargan y compilan todos los archivos de la carpeta de (incluidas las subcarpetas). La compatibilidad con `.csproj` la configuración se mejorará en el futuro (consulte [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) para obtener más detalles).


### <a name="c"></a>[C#](#tab/tabid-csharp)

Un programa host de C# tiene varios componentes y funciona muy estrechamente con algunos componentes del QDK, como los simuladores, que se basan en C#.

El Q# compilador funciona aquí generando un espacio de nombres de C# denominado de forma equivalente a partir del Q# espacio de nombres en el Q# archivo.
Además, genera una clase de C# con nombre equivalente para cada una de las Q# llamadas o tipos definidos en ella.

En primer lugar, las clases que se usan en nuestro programa host estarán disponibles con `using` instrucciones, que son aproximadamente análogo a las `open` instrucciones del Q# archivo:

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (for example, QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

Después, declaramos nuestro espacio de nombres de C#, algunos otros bits y partes (vea el bloque de código completo a continuación) y, después, cualquier programación clásica que nos gustaría (por ejemplo, calculando argumentos para las Q# llamadas).
Este último no es necesario en nuestro caso, pero se puede encontrar un ejemplo de este uso en el  [ejemplo de interoperabilidad de .net](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet).

#### <a name="target-machines"></a>Máquinas de destino

Al volver a Q# , se debe crear una instancia del equipo de destino en el que se ejecutarán nuestras operaciones.

```csharp
            using var sim = new QuantumSimulator();
```

El uso de otras máquinas de destino es tan sencillo como crear una instancia de una diferente, aunque la manera de hacerlo y el procesamiento de las devoluciones puede ser ligeramente diferente.
Por motivos de brevedad, nos centramos [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) ahora en y incluimos lo [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [siguiente](#including-the-resources-estimator).

Cada clase de C# generada a partir de las Q# operaciones tiene un `Run` método, el primer argumento de que debe ser la instancia del equipo de destino.
Por lo tanto, para ejecutar `MeasureSuperposition` en `QuantumSimulator` , usamos `MeasureSuperposition.Run(sim)` .
Los resultados devueltos se pueden asignar a las variables en C#:

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> El `Run` método se ejecuta de forma asincrónica porque es el caso del hardware Quantum real y, por lo tanto, la `await` palabra clave bloquea el procesamiento hasta que se completa la tarea.

Si el que Q# se puede llamar no tiene ningún resultado (por ejemplo, tiene el tipo de valor devuelto `Unit` ), la ejecución todavía se puede realizar de la misma manera sin asignarla a una variable.
En ese caso, la línea completa simplemente consistiría en 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a>Argumentos

Los argumentos de los que Q# se pueden llamar se pasan simplemente como argumentos adicionales después del equipo de destino.
Por lo tanto, los resultados de `MeasureSuperpositionArray` en `n=4` qubits se capturaban mediante 

```csharp
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);
```

Por tanto, un programa host de C# completo podría ser similar a

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine($"Multiple qubit result: {multiQubitResult}");
        }
    }
}
```

En la ubicación del archivo de C#, el programa host se puede ejecutar desde el símbolo del sistema. para ello, escriba
```dotnetcli
dotnet run
```
y en este caso, verá que la salida se escribe en la consola de forma similar a 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> Debido a la interoperabilidad del compilador con los espacios de nombres, podríamos hacer que las Q# llamadas a las llamadas estén disponibles sin la `using NamespaceName;` instrucción y simplemente hacer coincidir el título del espacio de nombres de C# con ella.
> Es decir, reemplazando `namespace host` por `namespace NamespaceName` .

#### <a name="including-the-resources-estimator"></a>Inclusión del estimador de recursos

[`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator)Requiere una implementación ligeramente diferente para recuperar la salida.

En primer lugar, en lugar de crear instancias de ellas como una variable con una `using` instrucción (como hacemos con `QuantumSimulator` ), se crean instancias de los objetos de la clase directamente a través de

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

Tenga en cuenta que, en lugar de un único simulador de destino que se va a usar en varias Q# operaciones, hemos creado una instancia de para cada uno. Esto se debe a que los propios objetos se modifican cuando se usan como equipos de destino, y los resultados se pueden recuperar posteriormente con el método de clase `.ToTSV()` .

Para ejecutar las operaciones en los estimadores de recursos, usamos

```csharp
            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);
```
y, a continuación, recupere los resultados como valores separados por tabulaciones (TSV) con `estimatorSingleQ.ToTSV()` y `estimatorMultiQ.ToTSV()` .

Por lo tanto, un programa host de C# completo que usa `QuantumSimulator` y `ResourcesEstimator` puede tener la forma:

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;
using NamespaceName;

namespace host
{
    static class Program
    {
        static async Task Main(string[] args)
        {
            using var sim = new QuantumSimulator();
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();

            var singleQubitResult = await MeasureSuperposition.Run(sim);
            var multiQubitResult = await MeasureSuperpositionArray.Run(sim, 4);

            await MeasureSuperposition.Run(estimatorSingleQ);
            await MeasureSuperpositionArray.Run(estimatorMultiQ, 4);

            Console.WriteLine($"Single qubit result: {singleQubitResult}");
            Console.WriteLine("Single qubit resources:");
            Console.WriteLine(estimatorSingleQ.ToTSV());

            Console.WriteLine($"\nMultiple qubit result: {multiQubitResult}");
            Console.WriteLine("Multiple qubit resources:");
            Console.WriteLine(estimatorMultiQ.ToTSV());
        }
    }
}
```


lo que produciría una salida similar a

```output
Single qubit result: One
Single qubit resources:
Metric          Sum
CNOT            0
QubitClifford   1
R               0
Measure         1
T               0
Depth           0
Width           1
BorrowedWidth   0

Multiple qubit result: [One,One,One,Zero]
Multiple qubit resources:
Metric          Sum
CNOT            0
QubitClifford   4
R               0
Measure         4
T               0
Depth           0
Width           4
BorrowedWidth   0
```

***

## <a name="no-locq-jupyter-notebooks"></a>Q# Cuadernos de Jupyter Notebook
Q# Los cuadernos de Jupyter Notebook usan el Q# kernel I, que permite definir, compilar y ejecutar Q# llamadas en un solo cuaderno---todo, junto con instrucciones, notas y otro contenido.
Esto significa que, aunque es posible importar y usar el contenido de `*.qs` Q# los archivos, no son necesarios en el modelo de ejecución.

Aquí veremos cómo ejecutar las Q# operaciones definidas anteriormente, pero se proporciona una introducción más amplia al uso de Q# cuadernos de Jupyter notebooks en la [Introducción a los Q# cuadernos de Jupyter](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).

### <a name="defining-operations"></a>Definir operaciones

En un Q# Jupyter Notebook, escriba Q# el código tal y como lo haríamos dentro del espacio de nombres de un Q# archivo.

Por lo tanto, se puede habilitar el acceso a las llamadas desde las [ Q# bibliotecas estándar](xref:microsoft.quantum.libraries.standard.intro) con `open` instrucciones para sus respectivos espacios de nombres.
Al ejecutar una celda con esta instrucción, las definiciones de esos espacios de nombres están disponibles en el área de trabajo.

> [!NOTE]
> Las llamadas de [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic) y [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon) (por ejemplo, [`H`](xref:Microsoft.Quantum.Intrinsic.H) y [`ApplyToEach`](xref:Microsoft.Quantum.Canon.ApplyToEach) ) están disponibles automáticamente para las operaciones definidas dentro de las celdas de Q# cuadernos de Jupyter Notebook.
> Sin embargo, esto no es cierto para el código que se incorpora desde Q# archivos de origen externos (un proceso que se muestra en los [cuadernos de introducción a Q# y Jupyter](https://github.com/microsoft/Quantum/blob/main/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)). 
> 

Del mismo modo, la definición de operaciones solo requiere escribir el Q# código y ejecutar la celda.

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="773">

A continuación, la salida muestra las operaciones, a las que se puede llamar desde las celdas futuras.

### <a name="target-machines"></a>Máquinas de destino

La funcionalidad para ejecutar operaciones en máquinas de destino específicas se proporciona a través de [ Q# comandos mágicos](xref:microsoft.quantum.guide.quickref.iqsharp).
Por ejemplo, `%simulate` hace uso de `QuantumSimulator` y `%estimate` usa `ResourcesEstimator` :

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Jupyter cell simulating a Q# operation and running resource estimation" width="773">

### <a name="passing-inputs-to-functions-and-operations"></a>Pasar entradas a funciones y operaciones

Para pasar entradas a las Q# operaciones, los argumentos se pueden pasar como `key=value` pares al comando de ejecución mágica.
Por lo tanto, para ejecutar `MeasureSuperpositionArray` con cuatro qubits, podemos ejecutar `%simulate MeasureSuperpositionArray n=4` :

<img src="../media/hostprograms_jupyter_args_sim_crop.png" alt="Jupyter cell simulating a Q# operation with arguments" width="773">

Este patrón se puede usar de forma similar con `%estimate` y otros comandos de ejecución.

### <a name="using-no-locq-code-from-other-projects-or-packages"></a>Usar Q# código de otros proyectos o paquetes

De forma predeterminada, un Q# Jupyter Notebook carga todos los `.qs` archivos de la carpeta actual y hace que sus Q# operaciones y funciones estén disponibles para su uso desde dentro del cuaderno. El [ `%who` comando mágico](xref:microsoft.quantum.iqsharp.magic-ref.who) muestra todas las Q# operaciones y funciones disponibles actualmente.

Para cargar Q# código desde otra carpeta, el [ `%project` comando Magic](xref:microsoft.quantum.iqsharp.magic-ref.project) se puede usar para agregar una referencia a un `.csproj` archivo para un Q# proyecto (es decir, un proyecto que haga referencia a `Microsoft.Quantum.Sdk` ). Este comando compilará los `.qs` archivos de la carpeta que contengan `.csproj` (y las subcarpetas). También cargará de forma recursiva los paquetes a los que se hace referencia a través `PackageReference` de o los Q# proyectos a los que se hace referencia a través `ProjectReference` de en ese `.csproj` archivo. 

Como ejemplo, las siguientes celdas simulan una Q# operación desde un proyecto externo, donde se hace referencia a la ruta de acceso del proyecto en relación con la carpeta actual:

<img src="../media/hostprograms_jupyter_project_crop.png" alt="Jupyter cell simulating a Q# operation from an external project" width="773">

Para cargar paquetes externos que contienen Q# código, use el [ `%package` comando mágico](xref:microsoft.quantum.iqsharp.magic-ref.package).
La carga de un paquete también estará disponible para los comandos mágicos personalizados o para mostrar los codificadores contenidos en los ensamblados que formen parte del paquete.

Para cargar los paquetes externos o Q# los proyectos en el inicialización del cuaderno, asegúrese de que la carpeta del cuaderno contiene un `.csproj` archivo al que hace referencia `Microsoft.Quantum.Sdk` . En ese `.csproj` , agregue la propiedad `<IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>` a `<PropertyGroup>` . Esto le indicará Q# Cómo cargar de forma recursiva todos los `ProjectReference` `PackageReference` elementos que se encuentren en ese en `.csproj` el momento de la carga del Bloc de notas.

Por ejemplo, este es un `.csproj` archivo simple que hace que se Q# cargue el `Microsoft.Quantum.Chemistry` paquete automáticamente:

```xml
<Project Sdk="Microsoft.Quantum.Sdk/0.12.20072031">
    <PropertyGroup>
        <OutputType>Library</OutputType>
        <TargetFramework>netstandard2.1</TargetFramework>
        <IQSharpLoadAutomatically>true</IQSharpLoadAutomatically>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="Microsoft.Quantum.Chemistry" Version="0.12.20072031" />
    </ItemGroup>
</Project>
```

> [!NOTE]
> Actualmente, esta `<IQSharpLoadAutomatically>` propiedad personalizada es necesaria Q# para los hosts de Jupyter Notebook, pero en el futuro, esto puede convertirse en el comportamiento predeterminado de un `.csproj` archivo ubicado en la misma carpeta que el archivo del Bloc de notas.

> [!NOTE]
> En la actualidad `<QsharpCompile>` `.csproj` , Jupyter Notebook los hosts omiten la configuración de Q# , y todos los `.qs` archivos de la carpeta de `.csproj` (incluidas las subcarpetas) se cargan y compilan. La compatibilidad con `.csproj` la configuración se mejorará en el futuro (consulte [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) para obtener más detalles).
