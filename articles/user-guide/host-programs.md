---
title: Formas de ejecutar un programa de preguntas y respuestas
description: 'Información general de las diferentes formas de ejecutar programas de Q #. Desde la línea de comandos, p # Jupyter notebooks y los programas host clásico en Python o en un lenguaje .NET.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/15/2020
ms.topic: article
uid: microsoft.quantum.guide.host-programs
ms.openlocfilehash: 132c138d7c392ed2b4bd3d0079180b68adae4cfc
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85887735"
---
# <a name="ways-to-run-a-q-program"></a>Formas de ejecutar un programa de preguntas y respuestas

Uno de los mayores puntos fuertes del kit de desarrollo de Quantum es su flexibilidad en plataformas y entornos de desarrollo.
Sin embargo, esto también significa que los nuevos usuarios de preguntas y respuestas se pueden confundir o saturar mediante las numerosas opciones que se encuentran en la [Guía de instalación](xref:microsoft.quantum.install).
En esta página, se explica lo que ocurre cuando se ejecuta un programa de preguntas y respuestas, y se comparan las distintas formas en que los usuarios pueden hacerlo.

Una distinción principal es que se puede ejecutar Q #:
- como aplicación independiente, donde Q # es el único lenguaje implicado y el programa se invoca directamente. En realidad, dos métodos se encuentran en esta categoría:
  - la interfaz de la línea de comandos
  - Cuadernos de Jupyter Notebook de Q#
- con un *programa host*adicional, escrito en Python o en un lenguaje .net (por ejemplo, C# o F #), que, a continuación, invoca el programa y puede procesar aún más los resultados devueltos.

Para comprender mejor estos procesos y sus diferencias, se considera un programa sencillo de Q # y se comparan las formas en que se pueden ejecutar.

## <a name="basic-q-program"></a>Programa Basic Q #

Un programa Quantum básico puede constar de la preparación de una qubit en una superposición de Estados $ \ket {0} $ y $ \ket {1} $, la medición y la devolución del resultado, que será aleatoriamente uno de estos dos Estados con la misma probabilidad.
En realidad, este proceso es el núcleo de la guía de inicio rápido del [generador de números aleatorios de Quantum](xref:microsoft.quantum.quickstarts.qrng) .

En Q #, esto se realizaría mediante el código siguiente:

```qsharp
        using (q = Qubit()) {    // allocates qubit for use (automatically in |0>)
            H(q);                // puts qubit in superposition of |0> and |1>
            return MResetZ(q);   // measures qubit, returns result (and resets it to |0> before deallocation)
        }
```

Sin embargo, este código no se puede ejecutar por sí.
Para ello, debe componer el cuerpo de una [operación](xref:microsoft.quantum.guide.basics#q-operations-and-functions), que se ejecuta cuando se llama---directamente o mediante otra operación. Por lo tanto, puede escribir una operación de la siguiente forma:
```qsharp
    operation MeasureSuperposition() : Result {
        using (q = Qubit()) {
            H(q);
            return MResetZ(q);
        }
    }
```
Ha definido una operación, `MeasureSuperposition` , que no toma ninguna entrada y devuelve un valor de tipo [result](xref:microsoft.quantum.guide.types).

Aunque los ejemplos de esta página solo se componen de *operaciones*de preguntas y respuestas, todos los conceptos que trataremos se refieren igualmente a *las funciones*de q # y, por lo tanto, hacemos referencia a ellos de forma colectiva como *llamadas*. Sus diferencias se describen en [preguntas y respuestas básicas: las operaciones y las funciones](xref:microsoft.quantum.guide.basics#q-operations-and-functions), y más detalles sobre cómo definirlas se pueden encontrar en [operaciones y funciones](xref:microsoft.quantum.guide.operationsfunctions).

### <a name="callable-defined-in-a-q-file"></a>Se puede llamar en un archivo de preguntas y respuestas

A la que se puede llamar es precisamente lo que se llama y ejecuta en Q #.
Sin embargo, requiere unas cuantas adiciones más para incluir un archivo de `*.qs` preguntas # completo.

En los *espacios de nombres*se definen todos los tipos Q # y se pueden llamar (ambos definidos y los intrínsecos al lenguaje), que proporcionan cada nombre completo al que se puede hacer referencia.

Por ejemplo, las [`H`](xref:microsoft.quantum.intrinsic.h) [`MResetZ`](xref:microsoft.quantum.measurement.mresetz) operaciones y se encuentran en los [`Microsoft.Quantum.Instrinsic`](xref:microsoft.quantum.intrinsic) espacios de [`Microsoft.Quantum.Measurement`](xref:microsoft.quantum.measurement) nombres y (parte de las bibliotecas de preguntas y [respuestas](xref:microsoft.quantum.qsharplibintro)).
Como tal, siempre se les puede llamar a través de sus nombres *completos* `Microsoft.Quantum.Intrinsic.H(<qubit>)` y `Microsoft.Quantum.Measurement.MResetZ(<qubit>)` , pero siempre esto provocaría un código muy saturado.

En su lugar, `open` las instrucciones permiten hacer referencia a las llamadas con una abreviatura más concisa, como hemos hecho en el cuerpo de la operación anterior.
El archivo de preguntas y respuestas completo que contiene nuestra operación consistiría en definir nuestro propio espacio de nombres, abriendo los espacios de nombres de los que se llamaron en la operación y, a continuación, nuestra operación:

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
> Una excepción a todo esto es el [`Microsoft.Quantum.Core`](xref:microsoft.quantum.core) espacio de nombres, que siempre se abre automáticamente.
> Por lo tanto, [`Length`](xref:microsoft.quantum.core.length) se pueden usar directamente llamadas como siempre.

### <a name="execution-on-target-machines"></a>Ejecución en equipos de destino

Ahora el modelo de ejecución general de un programa de preguntas y respuestas está claro.

<br/>
<img src="../media/hostprograms_general_execution_model.png" alt="Q# program execution diagram" width="400">

En primer lugar, el llamador específico que se va a ejecutar tiene acceso a cualquier otro tipo que se pueda llamar y que se haya definido en el mismo espacio de nombres.
También tiene acceso a los de cualquiera de las [bibliotecas de preguntas y respuestas](xref:microsoft.quantum.libraries), pero se debe hacer referencia a ellos mediante su nombre completo, o bien mediante el uso de `open` instrucciones descritas anteriormente.

A continuación, se puede llamar a en un *[equipo de destino](xref:microsoft.quantum.machines)*.
Estas máquinas de destino pueden ser hardware de Quantum real o varios simuladores disponibles como parte de QDK.
Para nuestros fines aquí, el equipo de destino más útil es una instancia del [simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator), `QuantumSimulator` , que calcula el comportamiento del programa como si se ejecutara en un equipo Quantum sin ruido.

Hasta ahora, hemos descrito lo que sucede cuando se ejecuta una acción Callable concreta.
Independientemente de si se usa Q # en una aplicación independiente o con un programa host, este proceso general es más o menos el mismo---, por lo tanto, la flexibilidad de QDK.
Por lo tanto, las diferencias entre las diferentes formas de llamar al kit de desarrollo de Quantum se revelan en el *modo* en que se llama a Q # Callable y en qué manera se devuelven los resultados.
Más concretamente, las diferencias giran en torno a 
1. que indica qué Q # Callable se va a ejecutar,
2. Cómo se proporcionan los posibles argumentos a los que se puede llamar,
3. especificar el equipo de destino en el que se va a ejecutar y
4. Cómo se devuelven los resultados.

En primer lugar, se describe cómo hacerlo con la aplicación de preguntas y respuestas independientes desde la línea de comandos y, a continuación, se sigue usando los programas host de Python y C#.
Nos reservamos la aplicación independiente de cuadernos de Jupyter Notebook en último lugar, ya que, a diferencia de las tres primeras, su funcionalidad principal no se centra en un archivo.

> [!NOTE]
> Aunque no se muestra en estos ejemplos, una diferencia entre los métodos de ejecución es que todos los mensajes impresos desde dentro del programa de preguntas y respuestas (por [`Message`](xref:microsoft.quantum.intrinsic.message) [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) ejemplo, o, por ejemplo) se imprimirán normalmente en la consola correspondiente.

## <a name="q-from-the-command-line"></a>Q # desde la línea de comandos
Una de las formas más sencillas de empezar a escribir programas de preguntas y respuestas es evitar tener que preocuparse por los archivos independientes y un segundo idioma.
El uso de Visual Studio Code o Visual Studio con la extensión QDK permite un flujo de trabajo sin problemas en el que se ejecutan Q # Calling desde un solo archivo Q #.

Para ello, se invocará en última instancia la ejecución del programa escribiendo
```dotnetcli
dotnet run
```
en la línea de comandos.
El flujo de trabajo más sencillo es cuando la ubicación del directorio del terminal es igual que el archivo de preguntas y respuestas, que se puede controlar fácilmente junto con la edición de archivos de preguntas y respuestas mediante el terminal integrado de VS Code, por ejemplo.
Sin embargo, el [ `dotnet run` comando](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) acepta numerosas opciones y el programa también se puede ejecutar desde una ubicación diferente, simplemente proporcionando `--project <PATH>` con la ubicación del archivo de preguntas y respuestas.


### <a name="add-entry-point-to-q-file"></a>Agregar punto de entrada al archivo de preguntas y respuestas

La mayoría de los archivos Q # contendrán más de un invocable, por lo que es necesario dejar que el compilador sepa *qué* llamadas se deben ejecutar cuando se proporciona el `dotnet run` comando.
Esto se hace con un cambio sencillo en el propio archivo de preguntas #: 
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

Ahora, una llamada de `dotnet run` desde la línea de comandos conduce a `MeasureSuperposition` ejecutarse y, a continuación, el valor devuelto se imprime directamente en el terminal.
Por lo tanto, verá `One` o `Zero` imprimirá. 

Tenga en cuenta que no importa si tiene más llamadas definidas debajo, solo se `MeasureSuperposition` ejecutará.
Además, no hay ningún problema si su llamador incluye [comentarios de documentación](xref:microsoft.quantum.guide.filestructure#documentation-comments) antes de su declaración, el `@EntryPoint()` atributo se puede colocar simplemente encima de ellos.

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
Tenga en cuenta que [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) y [`ForEach`](xref:microsoft.quantum.arrays.foreach) se encuentran en los [`Microsoft.Quantum.Canon`](xref:microsoft.quantum.canon) espacios de [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) nombres y, que requieren `open` instrucciones adicionales para cada uno.

Si movemos el `@EntryPoint()` atributo para que preceda a esta nueva operación (tenga en cuenta que solo puede haber una de estas líneas en un archivo), intentar ejecutarlo simplemente `dotnet run` genera un mensaje de error que indica qué opciones de línea de comandos adicionales son necesarias y cómo expresarlos.

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
> `camelCase`El compilador modifica ligeramente los nombres de argumento definidos en para que se acepten como entradas de Q #. Por ejemplo, si en lugar de `n` , usamos el nombre `numQubits` anterior, esta entrada se proporcionaría en la línea de comandos mediante en `--num-qubits 4` lugar de `-n 4` .

El mensaje de error también proporciona otras opciones que se pueden usar, incluida la forma de cambiar la máquina de destino.

### <a name="different-target-machines"></a>Distintos equipos de destino

Dado que las salidas de nuestras operaciones hasta ahora han sido los resultados esperados de su acción en qubits reales, está claro que el equipo de destino predeterminado de la línea de comandos es el simulador de quauntum de estado completo, `QuantumSimulator` .
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

### <a name="command-line-execution-summary"></a>Resumen de ejecución de línea de comandos
<br/>
<img src="../media/hostprograms_command_line_diagram.png" alt="Q# program from command line" width="700">

### <a name="non-q-dotnet-run-options"></a>Opciones que no son de Q # `dotnet run`

Como se mencionó brevemente anteriormente con la `--project` opción, el [ `dotnet run` comando](https://docs.microsoft.com/dotnet/core/tools/dotnet-run) también acepta opciones no relacionadas con los argumentos de Q # Callable.
Si se proporcionan ambos tipos de opciones, `dotnet` se deben proporcionar primero las opciones específicas de, seguida de un delimitador `--` y, a continuación, las opciones específicas de Q #.
Por ejemplo, si se especifica una ruta de acceso junto con un número qubits para la operación anterior, se ejecutaría a través de `dotnet run --project <PATH> -- -n <n>` .

## <a name="q-with-host-programs"></a>Preguntas # con programas host

Con el archivo Q # a mano, una alternativa a llamar a una operación o función directamente desde la línea de comandos es usar un *programa host* en otro lenguaje clásico. En concreto, esto se puede hacer con Python o con un lenguaje .NET como C# o F # (por motivos de brevedad, solo se detallará C# aquí).
Se requiere un poco más de configuración para habilitar la interoperabilidad, pero esos detalles se pueden encontrar en las [guías de instalación](xref:microsoft.quantum.install).

En pocas palabras, la situación incluye ahora un archivo de programa de host (por ejemplo, `*.py` o `*.cs` ) en la misma ubicación que el archivo de preguntas y respuestas.
Ahora es el programa *host* que se ejecuta y, en el transcurso de su ejecución, puede llamar a funciones y operaciones de q # específicas desde el archivo de preguntas y respuestas.
El núcleo de la interoperabilidad se basa en el compilador de Q #, de modo que el contenido del archivo Q # es accesible para el programa host, de forma que se pueda llamar.

Una de las principales ventajas de usar un programa host es que los datos clásicos devueltos por el programa de preguntas y respuestas se pueden procesar posteriormente en el idioma del host.
Esto puede constar de un procesamiento de datos avanzado (por ejemplo, algo que no se puede realizar internamente en Q #) y, después, llamar a más acciones de Q # en función de los resultados, o algo tan sencillo como trazar los resultados de Q #.

Aquí se muestra el esquema general y se describen las implementaciones específicas para Python y C# a continuación. Puede encontrar un ejemplo de uso de un programa host de F # en los [ejemplos de interoperabilidad de .net](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).

<br/>
<img src="../media/hostprograms_host_program_diagram.png" alt="Q# program from a host program" width="700">

> [!NOTE]
> El `@EntryPoint()` atributo usado para las aplicaciones de línea de comandos de Q # no se puede usar con programas host.
> Se producirá un error si está presente en el archivo Q # al que llama un host. 

Para trabajar con distintos programas host, no es necesario realizar ningún cambio en un `*.qs` archivo de preguntas y respuestas.
Todas las implementaciones del programa host siguientes funcionan con el mismo archivo de preguntas #:

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
1. Importe el `qsharp` módulo, que registra el cargador de módulos para la interoperabilidad de Q #. 
    Esto permite que los espacios de nombres de Q # aparezcan como módulos de Python, desde los que se pueden "importar" preguntas # Invocables.
    Tenga en cuenta que técnicamente no son las llamadas a preguntas y respuestas que se importan, sino códigos auxiliares de Python que permiten llamar a ellos.
    Estos se comportan como objetos de las clases de Python, en los que usamos métodos para especificar las máquinas de destino a las que se debe enviar la operación para su ejecución.

2. Importe estas Q # Callable que llamaremos directamente---en este caso, `MeasureSuperposition` y `MeasureSuperpositionArray` .
    ```python
    import qsharp
    from NamespaceName import MeasureSuperposition, MeasureSuperpositionArray
    ```
    Con el `qsharp` módulo importado, también puede importar llamadas directamente desde los espacios de nombres de la biblioteca de Q #.

3. Entre cualquier otro código de Python, ahora puede llamar a esas llamadas en máquinas de destino específicas y asignar sus retornos a variables (si devuelven un valor) para su uso posterior.

#### <a name="specifying-target-machines"></a>Especificar equipos de destino
La llamada a una operación que se va a ejecutar en un equipo de destino específico se realiza a través de diferentes métodos de Python en el objeto importado.
Por ejemplo, `.simulate(<args>)` , utiliza `QuantumSimulator` para ejecutar la operación, mientras que `.estimate_resources(<args>)` lo hace en `ResourcesEstimator` .

#### <a name="passing-inputs-to-q"></a>Pasar entradas a Q\#
Los argumentos de Q # Callable se deben proporcionar en forma de argumento de palabra clave, donde la palabra clave es el nombre del argumento en la definición de Q # Callable.
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

```python
Single qubit:
1
{'CNOT': 0, 'QubitClifford': 1, 'R': 0, 'Measure': 1, 'T': 0, 'Depth': 0, 'Width': 1, 'BorrowedWidth': 0}

Multiple qubits:
[0, 1, 1, 1]
{'CNOT': 0, 'QubitClifford': 4, 'R': 0, 'Measure': 4, 'T': 0, 'Depth': 0, 'Width': 4, 'BorrowedWidth': 0}
```

### <a name="c"></a>[C#](#tab/tabid-csharp)

Un programa host de C# tiene varios componentes y funciona muy estrechamente con algunos componentes del QDK, como los simuladores, que se basan en C#.

El compilador de preguntas # funciona aquí mediante la generación de un espacio de nombres de C# denominado de forma equivalente a partir del espacio de nombres de Q # en nuestro archivo de preguntas y respuestas.
Además, genera una clase de C# con el nombre equivalente para cada uno de los tipos de Q # Callable o los tipos definidos en ella.

En primer lugar, las clases usadas en nuestro programa host estarán disponibles con `using` instrucciones, que son aproximadamente análogo a las `open` instrucciones del archivo de preguntas #:

```csharp
using System;
using System.Threading.Tasks;
using Microsoft.Quantum.Simulation.Simulators;    // contains the target machines (e.g. QuantumSimulator, ResourcesEstimator)
using NamespaceName;                              // make the Q# namespace available
```

A continuación, se declara el espacio de nombres de C#, algunos otros bits y partes (vea el bloque de código completo a continuación) y, después, cualquier programación clásica que nos gustaría (por ejemplo, calculando argumentos para las llamadas a Q #).
Este último no es necesario en nuestro caso, pero se puede encontrar un ejemplo de este uso en el [ejemplo de interoperabilidad de .net](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet).

#### <a name="target-machines"></a>Máquinas de destino

Al volver a Q #, se debe crear una instancia del equipo de destino en el que se ejecutarán nuestras operaciones.

```csharp
            using var sim = new QuantumSimulator();
```

El uso de otras máquinas de destino es tan sencillo como crear una instancia de una diferente, aunque la manera de hacerlo y el procesamiento de las devoluciones puede ser ligeramente diferente.
Por motivos de brevedad, nos centramos [`QuantumSimulator`](xref:microsoft.quantum.machines.full-state-simulator) ahora en y incluimos lo [`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator) [siguiente](#including-the-resources-estimator).

Cada clase de C# generada a partir de las operaciones de Q # tiene un `Run` método, el primer argumento de que debe ser la instancia del equipo de destino.
Por lo tanto, para ejecutar `MeasureSuperposition` en `QuantumSimulator` , usamos `MeasureSuperposition.Run(sim)` .
Los resultados devueltos se pueden asignar a las variables en C#:

```csharp
            var singleQubitResult = await MeasureSuperposition.Run(sim);
```

> [!NOTE]
> El `Run` método se ejecuta de forma asincrónica porque es el caso del hardware Quantum real y, por lo tanto, la `await` palabra clave bloquea la ejecución hasta que se completa la tarea.

Si Q # Callable no tiene ningún resultado (es decir, tiene el tipo de valor devuelto `Unit` ), la ejecución todavía se puede realizar de la misma manera sin asignarla a una variable.
En ese caso, la línea completa simplemente consistiría en 
```csharp
await <callable>.Run(<simulator>);
```

#### <a name="arguments"></a>Argumentos

Los argumentos de la t # Callable simplemente se pasan como argumentos adicionales tras el equipo de destino.
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

En la ubicación del archivo de C#, el programa host se puede ejecutar desde la línea de comandos escribiendo
```dotnetcli
dotnet run
```
y en este caso, verá que la salida se escribe en la consola de forma similar a 
```output
Single qubit result: One
Multiple qubit result: [One,One,Zero,Zero]
```

> [!NOTE]
> Debido a la interoperabilidad del compilador con los espacios de nombres, podríamos hacer que nuestras llamadas de Q # estén disponibles sin la `using NamespaceName;` instrucción y simplemente buscar en ella el título del espacio de nombres de C#.
> Es decir, reemplazando `namespace host` por `namespace NamespaceName` .

#### <a name="including-the-resources-estimator"></a>Inclusión del estimador de recursos

[`ResourcesEstimator`](xref:microsoft.quantum.machines.resources-estimator)Requiere una implementación ligeramente diferente para recuperar la salida.

En primer lugar, en lugar de crear instancias de ellas como una variable con una `using` instrucción (como hacemos con `QuantumSimulator` ), se crean instancias de los objetos de la clase directamente a través de

```csharp
            var estimatorSingleQ = new ResourcesEstimator();
            var estimatorMultiQ = new ResourcesEstimator();
```

Tenga en cuenta que, en lugar de un único simulador de destino que se va a usar en varias operaciones de Q #, hemos creado una instancia de para cada uno. Esto se debe a que los propios objetos se modifican cuando se usan como equipos de destino, y los resultados se pueden recuperar posteriormente con el método de clase `.ToTSV()` .

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

## <a name="q-jupyter-notebooks"></a>Cuadernos de Jupyter Notebook de Q#
Los cuadernos de Jupyter Notebook usan el kernel de IQ #, que permite definir, compilar y ejecutar Q # Callable en un solo cuaderno---todo junto a instrucciones, notas y otro contenido.
Esto significa que, aunque es posible importar y usar el contenido de `*.qs` los archivos de Q #, no son necesarios en el modelo de ejecución.

Aquí veremos cómo ejecutar las operaciones de Q # definidas anteriormente, pero se proporciona una introducción más amplia al uso de cuadernos de Jupyter Notebook en la [Introducción a los cuadernos de preguntas y respuestas de Jupyter](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb).

### <a name="defining-operations"></a>Definir operaciones

En un Jupyter Notebook de preguntas y respuestas, se escribe el código de Q # como se haría desde dentro del espacio de nombres de un archivo de preguntas y respuestas.

Por lo tanto, podemos habilitar el acceso a las llamadas desde las [bibliotecas de preguntas # estándar](xref:microsoft.quantum.qsharplibintro) con `open` instrucciones para sus respectivos espacios de nombres.
Al ejecutar una celda con esta instrucción, las definiciones de esos espacios de nombres están disponibles en el área de trabajo.

> [!NOTE]
> Las llamadas de [Microsoft. Quantum. Intrinsic](xref:microsoft.quantum.intrinsic) y [Microsoft. Quantum. Canon](xref:microsoft.quantum.canon) (por ejemplo, [`H`](xref:microsoft.quantum.intrinsic.h) y [`ApplyToEach`](xref:microsoft.quantum.canon.applytoeach) ) están disponibles automáticamente para las operaciones definidas dentro de las celdas de los cuadernos de Jupyter Notebook.
> Sin embargo, esto no es cierto para el código traído de archivos de código fuente de Q # externos (un proceso que se muestra en la [Introducción a los cuadernos de preguntas y respuestas de Jupyter](https://github.com/microsoft/Quantum/blob/master/samples/getting-started/intro-to-iqsharp/Notebook.ipynb)). 
> 

Del mismo modo, la definición de operaciones solo requiere escribir el código Q # y ejecutar la celda.

<img src="../media/hostprograms_jupyter_op_def_crop.png" alt="Jupyter cell defining Q# operations" width="600">

A continuación, la salida muestra las operaciones, a las que se puede llamar desde las celdas futuras.

### <a name="target-machines"></a>Máquinas de destino

La funcionalidad para ejecutar operaciones en equipos de destino específicos se proporciona a través de [comandos de IQ # Magic](xref:microsoft.quantum.guide.quickref.iqsharp).
Por ejemplo, `%simulate` hace uso de `QuantumSimulator` y `%estimate` usa `ResourcesEstimator` :

<img src="../media/hostprograms_jupyter_no_args_sim_est_crop.png" alt="Simulate and estimate resources Jupyter cell" width="500">

### <a name="passing-inputs-to-functions-and-operations"></a>Pasar entradas a funciones y operaciones

Actualmente, los comandos mágicos de ejecución solo se pueden usar con operaciones que no toman ningún argumento. Por lo tanto, para ejecutar `MeasureSuperpositionArray` , es necesario definir una operación de "contenedor" que, a continuación, llame a la operación con los argumentos:

<img src="../media/hostprograms_jupyter_wrapper_def_sim_crop.png" alt="Wrapper function and simulate Jupyter cell" width="550">

Esta operación puede usarse de forma similar con `%estimate` y otros comandos de ejecución.
