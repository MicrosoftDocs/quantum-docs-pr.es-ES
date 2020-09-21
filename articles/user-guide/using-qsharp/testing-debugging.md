---
title: Prueba y depuración
description: Aprenda a usar pruebas unitarias, hechos y aserciones y funciones de volcado para probar y depurar programas Quantum.
author: tcNickolas
ms.author: mamykhai
ms.date: 06/01/2020
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2f2181d388a59c1c6c5a0f13c9aa49d5fa1e51ae
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833167"
---
# <a name="testing-and-debugging"></a>Prueba y depuración

Al igual que con la programación clásica, es esencial poder comprobar que los programas Quantum funcionan según lo previsto y para poder diagnosticar un comportamiento incorrecto.
En esta sección, trataremos las herramientas que ofrece Q# para probar y depurar programas Quantum.

## <a name="unit-tests"></a>Pruebas unitarias

Un enfoque común para probar programas clásico es escribir programas pequeños denominados *pruebas unitarias*, que ejecutan código en una biblioteca y comparan su salida con alguna salida esperada.
Por ejemplo, puede asegurarse de que `Square(2)` devuelve `4` desde que conoce *un priori* que es $2 ^ 2 = $4.

Q# admite la creación de pruebas unitarias para programas Quantum y que se pueden ejecutar como pruebas en el marco de pruebas unitarias de [xUnit](https://xunit.github.io/) .

### <a name="creating-a-test-project"></a>Crear un proyecto de prueba

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Abra Visual Studio 2019. Vaya al menú **archivo** y seleccione **nuevo > proyecto..**.. En la esquina superior derecha, busque `Q#` y seleccione la plantilla ** Q# proyecto de prueba** .

#### <a name="command-line--visual-studio-code"></a>[Línea de comandos/Visual Studio Code](#tab/tabid-vscode)

Desde la línea de comandos favorita, ejecute el siguiente comando:
```dotnetcli
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

El nuevo proyecto tiene un único archivo `Tests.qs` , lo que proporciona un lugar cómodo para definir nuevas Q# pruebas unitarias.
Inicialmente, este archivo contiene una prueba unitaria `AllocateQubit` de ejemplo que comprueba que una qubit recién asignada se encuentra en el estado $ \ket {0} $ e imprime un mensaje:

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            AssertMeasurement([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

Cualquier Q# operación o función que toma un argumento de tipo `Unit` y devuelve `Unit` se puede marcar como una prueba unitaria mediante el `@Test("...")` atributo. En el ejemplo anterior, el argumento para ese atributo, `"QuantumSimulator"` , especifica el destino en el que se ejecuta la prueba. Una sola prueba puede ejecutarse en varios destinos. Por ejemplo, agregue un atributo `@Test("ResourcesEstimator")` delante de `AllocateQubit` . 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
Guarde el archivo y ejecute todas las pruebas. Ahora debería haber dos pruebas unitarias, una en `AllocateQubit` la que se ejecuta en `QuantumSimulator` y otra en la que se ejecuta en `ResourcesEstimator` . 

El Q# compilador reconoce los destinos integrados `"QuantumSimulator"` , `"ToffoliSimulator"` y `"ResourcesEstimator"` como destinos de ejecución válidos para las pruebas unitarias. También es posible especificar cualquier nombre completo para definir un destino de ejecución personalizado. 

### <a name="running-no-locq-unit-tests"></a>Ejecutar Q# pruebas unitarias

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Como programa de instalación única por solución, vaya al menú **prueba** y seleccione **configuración de pruebas > arquitectura de procesador predeterminada > x64**.

> [!TIP]
> La configuración predeterminada de la arquitectura del procesador para Visual Studio se almacena en el archivo de opciones de solución ( `.suo` ) para cada solución.
> Si elimina este archivo, deberá seleccionar **x64** como su arquitectura de procesador.

Compile el proyecto, abra el menú **prueba** y seleccione **Windows > explorador de pruebas**. **AllocateQubit** se muestra en la lista de pruebas en el grupo **pruebas no ejecutadas** . Seleccione **ejecutar todas** o ejecutar esta prueba individual.

#### <a name="command-line--visual-studio-code"></a>[Línea de comandos/Visual Studio Code](#tab/tabid-vscode)

Para ejecutar las pruebas, navegue hasta la carpeta del proyecto (la carpeta que contiene `Tests.csproj` ) y ejecute el comando:

```bash
$ dotnet restore
$ dotnet test
```

Debería obtener una salida similar a la siguiente:

```
Build started, please wait...
Build completed.

Test run for C:\Users\chgranad.REDMOND\tmp\Tests\bin\Debug\netcoreapp2.0\Tests.dll(.NETCoreApp,Version=v2.0)
Microsoft (R) Test Execution Command Line Tool Version 15.3.0-preview-20170628-02
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.5864002]   Discovering: Tests
[xUnit.net 00:00:00.7073844]   Discovered:  Tests
[xUnit.net 00:00:00.7453826]   Starting:    Tests
[xUnit.net 00:00:00.9590439]   Finished:    Tests

Total tests: 1. Passed: 1. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.9607 Seconds
```

Las pruebas unitarias se pueden filtrar según su nombre o destino de ejecución:

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

La función intrínseca <xref:microsoft.quantum.intrinsic.message> tiene el tipo `(String -> Unit)` y permite la creación de mensajes de diagnóstico.

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Después de ejecutar una prueba en el explorador de pruebas y hacer clic en la prueba, se muestra un panel con información sobre la serie de pruebas: estado de superación/error, tiempo transcurrido y un vínculo a la salida. Haga clic en **salida** para abrir la salida de la prueba en una nueva ventana.

![resultados de la prueba](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[Línea de comandos/Visual Studio Code](#tab/tabid-vscode)

El estado de superación o error de cada prueba se imprime en la consola mediante `dotnet test` .
En el caso de las pruebas con errores, las salidas también se imprimen en la consola para ayudar a diagnosticar el error.

***

## <a name="facts-and-assertions"></a>Hechos y aserciones

Dado que las funciones de Q# no tienen efectos secundarios _lógicos_ , nunca puede observar, desde dentro de un Q# programa, cualquier otro tipo de efecto de ejecutar una función cuyo tipo de salida sea la tupla vacía `()` .
Es decir, una máquina de destino puede elegir no ejecutar ninguna función que devuelva `()` con la garantía de que esta omisión no modificará el comportamiento de ningún Q# código siguiente.
Este comportamiento hace que las funciones devuelvan `()` (como `Unit` ) una herramienta útil para insertar aserciones y lógica de depuración en Q# programas. 

Veamos un ejemplo sencillo:

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

Aquí, la palabra clave `fail` indica que el cálculo no debe continuar y genera una excepción en el equipo de destino que ejecuta el Q# programa.
Por definición, un error de este tipo no se puede observar desde dentro Q# , ya que el equipo de destino ya no ejecuta el Q# código después de alcanzar una `fail` instrucción.
Por lo tanto, si continuamos después de una llamada a `PositivityFact` , podemos estar seguros de que su entrada fue positiva.

Tenga en cuenta que se puede implementar el mismo comportamiento que `PositivityFact` el uso [`Fact`](xref:microsoft.quantum.diagnostics.fact) de la función del <xref:microsoft.quantum.diagnostics> espacio de nombres:

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

Por otro lado, las *aserciones*se usan de forma similar a los hechos, pero pueden depender del estado de la máquina de destino. En consecuencia, se definen como operaciones, mientras que los hechos se definen como funciones (como en el ejemplo anterior).
Para entender la distinción, considere el siguiente uso de un hecho dentro de una aserción:

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

Aquí se usa la operación <xref:microsoft.quantum.environment.getqubitsavailabletouse> para devolver el número de qubits disponibles para su uso.
Dado que esto depende del estado global del programa y su entorno de ejecución, nuestra definición de `AssertQubitsAreAvailable` también debe ser una operación.
Sin embargo, podemos usar ese estado global para producir un `Bool` valor simple como entrada para la `Fact` función.

[El](xref:microsoft.quantum.libraries.standard.prelude)preparativo, que se basa en estas ideas, ofrece dos aserciones especialmente útiles <xref:microsoft.quantum.diagnostics.assertmeasurement> y <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> ambas se modelan como operaciones en `()` . Cada una de estas aserciones toma un operador Pauli que describe una medida determinada de interés, un registro Quantum en el que se realiza una medida y un resultado hipotético.
Los equipos de destino que funcionan por simulación no están limitados por [el teorema sin clonación](https://en.wikipedia.org/wiki/No-cloning_theorem)y pueden realizar tales mediciones sin alterar el registro que pasa a dichas aserciones.
Un simulador puede, de forma similar a la `PositivityFact` función anterior, detener el cálculo si el resultado hipotético no se observa en la práctica:

```qsharp
using (register = Qubit()) 
{
    H(register);
    AssertMeasurement([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

En el hardware de Quantum físico, donde el teorema sin clonación impide el examen de un estado de Quantum, las `AssertMeasurement` `AssertMeasurementProbability` operaciones y simplemente devuelven `()` sin ningún otro efecto.

El <xref:microsoft.quantum.diagnostics> espacio de nombres proporciona varias funciones más de la `Assert` familia, con las que puede comprobar condiciones más avanzadas. 

## <a name="dump-functions"></a>Funciones de volcado de memoria

Para ayudar a solucionar problemas de los programas Quantum, el <xref:microsoft.quantum.diagnostics> espacio de nombres ofrece dos funciones que pueden volcar en un archivo el estado actual del equipo de destino: <xref:microsoft.quantum.diagnostics.dumpmachine> y <xref:microsoft.quantum.diagnostics.dumpregister> . La salida generada de cada depende del equipo de destino.

### <a name="dumpmachine"></a>DumpMachine

El simulador de Quantum de estado completo distribuido como parte del kit de desarrollo de Quantum escribe en el archivo la [función de onda](https://en.wikipedia.org/wiki/Wave_function) del sistema Quantum completo, como una matriz unidimensional de números complejos, en la que cada elemento representa la amplitud de la probabilidad de medir el estado de base de cálculo $ \ket{n} $, donde $ \ket{n} = \ket{b_ {n-1}... b_1b_0} $ para bits $ \{ b_i \} $. Por ejemplo, en un equipo con solo dos qubits asignados y en el estado Quantum $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} , \end{align} $ $ al llamar a <xref:microsoft.quantum.diagnostics.dumpmachine> se genera este resultado:

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

La primera fila proporciona un comentario con los identificadores del qubits correspondiente en su orden significativo.
El resto de las filas describen la amplitud de probabilidad de medir el vector de estado de base $ \ket{n} $ en formatos cartesianos y polares. En detalle para la primera fila:

* **`∣0❭:`** esta fila corresponde al `0` Estado de base de cálculo
* **`0.707107 +  0.000000 i`**: la amplitud de probabilidad en formato cartesiano.
* **` == `**: el `equal` signo separa ambas representaciones equivalentes.
* **`**********  `**: Una representación gráfica de la magnitud, el número de `*` es proporcional a la probabilidad de medir este vector de estado.
* **`[ 0.500000 ]`**: el valor numérico de la magnitud
* **`    ---`**: Una representación gráfica de la fase de amplitud (vea la salida siguiente).
* **`[ 0.0000 rad ]`**: valor numérico de la fase (en radianes).

Tanto la magnitud como la fase se muestran con una representación gráfica. La representación de la magnitud es directa: muestra una barra de `*` ; cuanto mayor es la probabilidad, mayor será la barra. En la fase, se muestran los siguientes símbolos para representar el ángulo en función de los intervalos:

```
[ -π/16,   π/16)       ---
[  π/16,  3π/16)        /-
[ 3π/16,  5π/16)        / 
[ 5π/16,  7π/16)       +/ 
[ 7π/16,  9π/16)      ↑   
[ 8π/16, 11π/16)    \-    
[ 7π/16, 13π/16)    \     
[ 7π/16, 15π/16)   +\     
[15π/16, 19π/16)   ---    
[17π/16, 19π/16)   -/     
[19π/16, 21π/16)    /     
[21π/16, 23π/16)    /+    
[23π/16, 25π/16)      ↓   
[25π/16, 27π/16)       -\ 
[27π/16, 29π/16)        \ 
[29π/16, 31π/16)        \+
[31π/16,   π/16)       ---
```

Los ejemplos siguientes muestran `DumpMachine` para algunos Estados comunes:

### `∣0❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

### `∣1❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣1❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
```

### `∣+❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
```

### `∣-❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:    -0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]  ---     [  3.14159 rad ]
```


  > [!NOTE]
  > El identificador de un qubit se asigna en tiempo de ejecución y no está necesariamente alineado con el orden en el que se asignó qubit o su posición dentro de un registro qubit.


#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > Para buscar un identificador de qubit en Visual Studio, coloque un punto de interrupción en el código e inspeccione el valor de una variable qubit, por ejemplo:
  > 
  > ![Mostrar el identificador de qubit en Visual Studio](~/media/qubit_id.png)
  >
  > el qubit con el índice `0` de `register2` tiene el identificador = `3` , el qubit con el índice `1` tiene el identificador = `2` .

#### <a name="command-line--visual-studio-code"></a>[Línea de comandos/Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > Puede buscar un identificador de qubit mediante la <xref:microsoft.quantum.intrinsic.message> función y pasar la variable qubit en el mensaje, por ejemplo:
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > Esto podría generar esta salida:
  >```
  > 0=q:3; 1=q:2
  >```
  > lo que significa que el qubit con el índice `0` de `register2` tiene `3` el identificador =, el qubit con el índice `1` tiene el identificador = `2` .


***

Dado que <xref:microsoft.quantum.diagnostics.dumpmachine> forma parte del  <xref:microsoft.quantum.diagnostics> espacio de nombres, debe agregar una `open` instrucción para tener acceso a ella:

```qsharp
namespace Samples {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {
        using (qubits = Qubit[2]) {
            H(qubits[1]);
            DumpMachine("dump.txt");
        }
    }
}
```


### <a name="dumpregister"></a>DumpRegister

<xref:microsoft.quantum.diagnostics.dumpregister> funciona como <xref:microsoft.quantum.diagnostics.dumpmachine> , salvo que también toma una matriz de qubits para limitar la cantidad de información a solo el correspondiente qubits.

Como con <xref:microsoft.quantum.diagnostics.dumpmachine> , la información generada por <xref:microsoft.quantum.diagnostics.dumpregister> depende del equipo de destino. Para el simulador de Quantum de estado completo, escribe en el archivo la función Wave hasta una fase global del subsistema Quantum generada por el qubits proporcionado en el mismo formato que <xref:microsoft.quantum.diagnostics.dumpmachine> .  Por ejemplo, vuelva a realizar una máquina con solo dos qubits asignados y en el estado Quantum $ $ \begin{align} \ket{\psi} = \frac {1} {\sqrt {2} } \ket {00} -\frac{(1 + i)} {2} \ket {10} =-e ^ {-i \ PI/4} ((\frac {1} {\sqrt {2} } \ket {0} -\frac{(1 + i)} {2} \ket {1} ) \otimes \frac{-(1 + i)} {\sqrt {2} } \ket {0} ) la llamada de \end{align} $ $ que llama <xref:microsoft.quantum.diagnostics.dumpregister> a `qubit[0]` genera este resultado:

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

y al llamar a <xref:microsoft.quantum.diagnostics.dumpregister> para `qubit[1]` se genera este resultado:

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

En general, el estado de un registro que está inenredado con otro registro es un estado mixto en lugar de un estado puro. En este caso, <xref:microsoft.quantum.diagnostics.dumpregister> genera el siguiente mensaje:

```
Qubits provided (0;) are entangled with some other qubit.
```

En el ejemplo siguiente se muestra cómo puede usar <xref:microsoft.quantum.diagnostics.dumpregister> y <xref:microsoft.quantum.diagnostics.dumpmachine> en el Q# código:

```qsharp
namespace app
{
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {

        using (qubits = Qubit[2]) {
            X(qubits[1]);
            H(qubits[1]);
            R1Frac(1, 2, qubits[1]);
            
            DumpMachine("dump.txt");
            DumpRegister("q0.txt", qubits[0..0]);
            DumpRegister("q1.txt", qubits[1..1]);

            ResetAll(qubits);
        }
    }
}
```

## <a name="debugging"></a>Depuración

Sobre `Assert` `Dump` las funciones y y las operaciones, Q# admite un subconjunto de capacidades de depuración estándar de Visual Studio: [establecer puntos de interrupción de línea](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [recorrer paso a paso el código mediante F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)y [inspeccionar los valores de las variables clásicas](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) es posible al ejecutar el código en el simulador.

La depuración en Visual Studio Code aprovecha las capacidades de depuración proporcionadas por C# para la extensión de Visual Studio Code con tecnología de OmniSharp y requiere la instalación de la [versión más reciente](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp). 
