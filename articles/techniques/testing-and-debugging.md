---
title: Pruebas y depuración de programas QTM
description: Aprenda a utilizar pruebas unitarias, hechos y aserciones, y funciones de volcado para probar y depurar programas cuánticos.
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: caf15b7273b7efed1da87a2edd62c06cd4357593
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030589"
---
# <a name="testing-and-debugging"></a>Pruebas y depuración

Al igual que con la programación clásica, es esencial poder comprobar que los programas cuánticos actúan según lo previsto, y poder diagnosticar un programa cuántico que es incorrecto.
En esta sección, cubrimos las herramientas que ofrece Q para probar y depurar programas cuánticos.

## <a name="unit-tests"></a>Pruebas unitarias

Un enfoque común para probar programas clásicos es escribir pequeños programas llamados *pruebas unitarias* que ejecutan código en una biblioteca y comparan su salida con algunos resultados esperados.
Por ejemplo, es posible `Square(2)` que `4`deseemos asegurarnos de que devuelve, ya que sabemos a *priori* que $2 x 2 x 4 $.

Q admite la creación de pruebas unitarias para programas cuánticos y que se pueden ejecutar como pruebas dentro del marco de pruebas [unitarias xUnit.](https://xunit.github.io/)

### <a name="creating-a-test-project"></a>Creación de un proyecto de prueba

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Abra Visual Studio 2019. Vaya al `File` menú `New`  >  `Project...`y seleccione .
En la esquina superior `Q#`derecha, busque `Q# Test Project` , y seleccione la plantilla.

#### <a name="command-line--visual-studio-code"></a>[Línea de comandos/Visual Studio Code](#tab/tabid-vscode)

Desde su línea de comandos favorita, ejecute el siguiente comando:
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

Su nuevo proyecto tendrá `Tests.qs`un único archivo, que proporciona un lugar conveniente para definir nuevas pruebas unitarias de Q.
Inicialmente, este archivo contiene `AllocateQubit` una prueba unitaria de ejemplo que comprueba{0}que un qubit recién asignado se encuentra en el estado $-ket $ e imprime un mensaje:

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

:new: cualquier operación o función Q `Unit` que `Unit` tome un argumento de `@Test("...")` tipo y devuelve se puede marcar como una prueba unitaria a través del atributo. El argumento de `"QuantumSimulator"` ese atributo, anteriormente, especifica el destino en el que se ejecuta la prueba. Se puede ejecutar una sola prueba en varios destinos. Por ejemplo, agregue `@Test("ResourcesEstimator")` `AllocateQubit`un atributo anterior . 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
Guarde el archivo y ejecute todas las pruebas. Ahora debería haber dos pruebas unitarias, una en la que AllocateQubit se ejecute en QuantumSimulator y otra donde se ejecute en ResourceEstimator. 

El compilador q reconoce los destinos integrados "QuantumSimulator", "ToffoliSimulator" y "ResourcesEstimator" como destinos de ejecución válidos para las pruebas unitarias. También es posible especificar cualquier nombre completo para definir un destino de ejecución personalizado. 

### <a name="running-q-unit-tests"></a>Ejecución de pruebas unitarias de Q

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Como una configuración `Test` única por solución, vaya `Test Settings`  >  `Default Processor Architecture`  >  `X64`al menú y seleccione .

> [!TIP]
> La configuración de arquitectura de procesador predeterminada para`.suo`Visual Studio se almacena en el archivo de opciones de solución ( ) para cada solución.
> Si elimina este archivo, tendrá que `X64` seleccionar como arquitectura de procesador de nuevo.

Compile el proyecto, `Test` vaya al `Windows`  >  `Test Explorer`menú y seleccione . `AllocateQubit`aparecerá en la lista de `Not Run Tests` pruebas del grupo. Seleccione `Run All` o ejecute esta prueba individual, y debe pasar!

#### <a name="command-line--visual-studio-code"></a>[Línea de comandos/Visual Studio Code](#tab/tabid-vscode)

Para ejecutar pruebas, vaya a la carpeta `Tests.csproj`del proyecto (la carpeta que contiene ) y ejecute el comando:

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

Las pruebas unitarias se pueden filtrar según su nombre y/o el destino de ejecución:

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

La función <xref:microsoft.quantum.intrinsic.message> `(String -> Unit)` intrínseca tiene tipo y permite la creación de mensajes de diagnóstico.

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Después de ejecutar una prueba en el Explorador de pruebas y hacer clic en la prueba, aparecerá un panel con información sobre la ejecución de la prueba: Estado aprobado/fallido, tiempo transcurrido y un vínculo "Salida". Si hace clic en el vínculo "Salida", la salida de prueba se abrirá en una nueva ventana.

![salida de prueba](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[Línea de comandos/Visual Studio Code](#tab/tabid-vscode)

El estado de aprobación/fallo de cada `dotnet test`prueba se imprime en la consola mediante .
Para las pruebas con errores, las salidas también se imprimen en la consola para ayudar a diagnosticar el error.

***

## <a name="facts-and-assertions"></a>Hechos y Aserciones

Debido a que las funciones en Q no tienen efectos secundarios _lógicos,_ cualquier `()` otro _tipo_ de efectos de ejecutar una función cuyo tipo de salida es la tupla vacía nunca se puede observar desde dentro de un programa Q.
Es decir, una máquina de destino puede `()` optar por no ejecutar ninguna función que devuelva con la garantía de que esta omisión no modificará el comportamiento de cualquier código Q.
Esto hace que `()` las funciones `Unit`que devuelven (es decir) sean una herramienta útil para incrustar aserciones y depurar lógica en programas Q. 

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

Aquí, la `fail` palabra clave indica que el cálculo no debe continuar, generando una excepción en el equipo de destino que ejecuta el programa Q.
Por definición, no se puede observar un error de este tipo desde dentro `fail` de Q, ya que no se ejecuta ningún otro código Q- después de que se alcanza una instrucción.
Por lo tanto, si `PositivityFact`procedemos más allá de una llamada a , podemos estar seguros por que su entrada fue positiva.

Tenga en cuenta que podemos `PositivityFact` implementar [`Fact`](xref:microsoft.quantum.diagnostics.fact) el <xref:microsoft.quantum.diagnostics> mismo comportamiento que el uso de la función desde el espacio de nombres:

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

*Las aserciones*, por otro lado, se utilizan de forma similar a los hechos, pero pueden depender del estado de la máquina de destino. En consecuencia, se definen como operaciones, mientras que los hechos se definen como funciones (como se ha mencionado anteriormente).
Para entender la distinción, considere el siguiente uso de un hecho dentro de una afirmación:

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

Aquí, estamos utilizando <xref:microsoft.quantum.environment.getqubitsavailabletouse> la operación para devolver el número de qubits disponibles para usar.
Como esto depende claramente del estado global del programa `AssertQubitsAreAvailable` y de su entorno de ejecución, nuestra definición de debe ser también una operación.
Sin embargo, podemos usar ese `Bool` estado global para `Fact` producir un valor simple como entrada para la función.

Basándose en estas ideas, [el preludio](xref:microsoft.quantum.libraries.standard.prelude) <xref:microsoft.quantum.intrinsic.assert> ofrece <xref:microsoft.quantum.intrinsic.assertprob> dos afirmaciones especialmente `()`útiles, y ambas modeladas como operaciones en . Cada una de estas aserciones toma un operador Pauli que describe una medida particular de interés, un registro cuántico en el que se va a realizar una medición y un resultado hipotético.
En las máquinas de destino que funcionan mediante simulación, no estamos vinculados por [el teorema de no clonación,](https://en.wikipedia.org/wiki/No-cloning_theorem)y podemos realizar tales mediciones sin perturbar el registro pasado a tales aserciones.
Un simulador puede entonces, similar a la `PositivityFact` función anterior, abortar el cálculo si el resultado hipotético no se observa en la práctica:

```qsharp
using (register = Qubit()) 
{
    H(register);
    Assert([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

En el hardware cuántico físico, donde el teorema sin `Assert` `AssertProb` clonación `()` impide el examen del estado cuántico, las operaciones simplemente regresan sin ningún otro efecto.

El <xref:microsoft.quantum.diagnostics> espacio de nombres `Assert` proporciona varias funciones más de la familia que nos permiten comprobar condiciones más avanzadas. 

## <a name="dump-functions"></a>Funciones de volcado

Para ayudar a solucionar <xref:microsoft.quantum.diagnostics> problemas de programas cuánticos, el espacio de nombres <xref:microsoft.quantum.diagnostics.dumpmachine> <xref:microsoft.quantum.diagnostics.dumpregister>ofrece dos funciones que pueden volcar en un archivo el estado actual de la máquina de destino: y . La salida generada de cada uno depende de la máquina de destino.

### <a name="dumpmachine"></a>DumpMachine

El simulador cuántico de estado completo distribuido como parte del Kit de Desarrollo Cuántico escribe en el archivo la [función](https://en.wikipedia.org/wiki/Wave_function) de onda de todo el sistema cuántico, como una matriz unidimensional de números complejos, en la que cada elemento representa la amplitud de la probabilidad de medir el estado de base computacional $ b_ . b_1b_0$ por bits\{\}$ b_i $. Por ejemplo, en una máquina con sólo dos qubits asignados y en el estado cuántico{1}$$ .{2}{00} {2} {10} <xref:microsoft.quantum.diagnostics.dumpmachine>

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

La primera fila proporciona un comentario con los documentos de identificación de los qubits correspondientes en su orden significativo.
El resto de las filas describen la amplitud de probabilidad de medir el vector de estado base $-ket-n$en formatos cartesianos y polares. En detalle para la primera fila:

* **`∣0❭:`** esta fila corresponde `0` al estado de base computacional
* **`0.707107 +  0.000000 i`**: la amplitud de probabilidad en formato cartesiano.
* **` == `**: `equal` el signo separa ambas representaciones equivalentes.
* **`**********  `**: Una representación gráfica de `*` la magnitud, el número de es proporcional a la probabilidad de medir este vector de estado.
* **`[ 0.500000 ]`**: el valor numérico de la magnitud
* **`    ---`**: Representación gráfica de la fase de la amplitud (ver más abajo).
* **`[ 0.0000 rad ]`**: el valor numérico de la fase (en radianes).

Tanto la magnitud como la fase se muestran con una representación gráfica. La representación de magnitud es recta: `*`muestra una barra de , cuanto mayor sea la probabilidad de que mayor sea la barra. Para la fase, mostramos los siguientes símbolos para representar el ángulo basado en rangos:

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

Los siguientes ejemplos muestran `DumpMachine` algunos estados comunes:

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
  > El identificador de un qubit se asigna en tiempo de ejecución y no está necesariamente alineado con el orden en el que se asignó el qubit o su posición dentro de un registro qubit.


#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > Puede averiguar un identificador de qubit en Visual Studio colocando un punto de interrupción en el código e inspeccionando el valor de una variable qubit, por ejemplo:
  > 
  > ![mostrar qubit id en Visual Studio](~/media/qubit_id.png)
  >
  > el qubit `0` con `register2` index`3`on tiene id `1` , el`2`qubit con index tiene id .

#### <a name="command-line--visual-studio-code"></a>[Línea de comandos/Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > Puede averiguar un qubit id <xref:microsoft.quantum.intrinsic.message> utilizando la función y pasando la variable qubit en el mensaje, por ejemplo:
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > que podría generar esta salida:
  >```
  > 0=q:3; 1=q:2
  >```
  > lo que significa que `0` el `register2` qubit`3`con index on `1` tiene`2`id , el qubit con index tiene id.


***

<xref:microsoft.quantum.diagnostics.dumpmachine>es parte <xref:microsoft.quantum.diagnostics> del espacio de nombres, por lo `open` que para usarlo debe agregar una instrucción:

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

<xref:microsoft.quantum.diagnostics.dumpregister>funciona <xref:microsoft.quantum.diagnostics.dumpmachine>como , excepto que también se necesita una matriz de qubits para limitar la cantidad de información a sólo la relevante para los qubits correspondientes.

Al <xref:microsoft.quantum.diagnostics.dumpmachine>igual que con <xref:microsoft.quantum.diagnostics.dumpregister> , la información generada por depende de la máquina de destino. Para el simulador cuántico de estado completo escribe en el archivo la función de onda hasta una fase global <xref:microsoft.quantum.diagnostics.dumpmachine>del subsistema cuántico generado por los qubits proporcionados en el mismo formato que .  Por ejemplo, tomar de nuevo una máquina con sólo dos qubits asignados y en el estado{1}cuántico $$ -{00} begin -align-ket-psi-{2} á{10} 'frac'sqrt{2}' ''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''( (frac,{1}{2}frac, "frac" y{0} "ket" (1 + i) "{2} "ket"{1} y "otimes" (1 + i) , "sqrt"{2}y "ket"{0} , "end" (alineación) de $$, que llama <xref:microsoft.quantum.diagnostics.dumpregister> para `qubit[0]` generar esta salida:

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

y <xref:microsoft.quantum.diagnostics.dumpregister> la `qubit[1]` llamada genera esta salida:

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

En general, el estado de un registro que está enredado con otro registro es un estado mixto en lugar de un estado puro. En este <xref:microsoft.quantum.diagnostics.dumpregister> caso, genera el siguiente mensaje:

```
Qubits provided (0;) are entangled with some other qubit.
```

En el ejemplo siguiente se <xref:microsoft.quantum.diagnostics.dumpregister> muestra <xref:microsoft.quantum.diagnostics.dumpmachine> cómo puede utilizar ambos y en el código q:

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

Además `Assert` `Dump` de las funciones y operaciones, Q- admite un subconjunto de capacidades de depuración estándar de Visual Studio: [establecer puntos](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints)de interrupción de línea, recorrer el [código mediante F10](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) e [inspeccionar los valores de las variables clásicas](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) son posibles durante la ejecución de código en el simulador.

La depuración en Visual Studio Code aprovecha las capacidades de depuración proporcionadas por la extensión de código de Visual Studio con tecnología OmniSharp y requiere la instalación de la [versión más reciente.](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) 
