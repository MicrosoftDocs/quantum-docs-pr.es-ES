---
title: Exploración del entrelazamiento con Q#
description: Obtenga información sobre cómo escribir un programa cuántico en Q#. Desarrolle una aplicación de estado Bell mediante el kit de desarrollo de Microsoft Quantum (QDK)
author: natke
ms.author: nakersha
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 989080e7d9979bb87d14b2580d28732bb1092eb1
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327380"
---
# <a name="tutorial-explore-entanglement-with-q"></a>Tutorial: Exploración del entrelazamiento con Q\#

En este tutorial, se muestra cómo escribir un programa de Q# que manipula y mide cúbits, y muestra los efectos de la superposición y el entrelazamiento.
Incluye instrucciones para instalar QDK, compilar el programa y ejecutarlo en un simulador cuántico.  

Escribirá una aplicación llamada Bell para demostrar el entrelazamiento cuántico.
El nombre Bell hace referencia a los estados de Bell, que son estados cuánticos específicos de dos cúbits que se usan para representar los ejemplos más sencillos de la superposición y el entrelazamiento cuántico.

## <a name="pre-requisites"></a>Requisitos previos

Si está listo para empezar a codificar, siga estos pasos antes de continuar: 

* Instale el kit de desarrollo de Microsoft Quantum para [Python](xref:microsoft.quantum.install.python) o [.NET](xref:microsoft.quantum.install.cs).
* Si ya tiene instalado el QDK, asegúrese de que tiene [actualizada](xref:microsoft.quantum.update) la última versión

También puede seguir sin instalar QDK y revisar las introducciones al lenguaje de programación Q# y los primeros conceptos de la computación cuántica.

## <a name="demonstrating-qubit-behavior-with-q"></a>Demostración del comportamiento de los cúbits con Q#

Recuerde nuestra [definición sencilla de cúbit](xref:microsoft.quantum.overview.understanding).  Mientras que los bits clásicos contienen un único valor binario, como 0 o 1, el estado de un [cúbit](xref:microsoft.quantum.glossary#qubit) puede ser una **superposición** de 0 y 1.  Conceptualmente, un cúbit se podría considerar como una dirección en el espacio (también conocida como vector).  Un cúbit puede estar en cualquiera de las direcciones posibles. Los dos **estados clásicos** son las dos direcciones, que representan el 100 % de probabilidad de medir 0 y el 100 % de probabilidad de medir 1.  Esta representación se visualiza también más formalmente con la [esfera de Bloch](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).

La acción de medir genera un resultado binario y cambia el estado del cúbit. La medida produce un valor binario, ya sea 0 o 1.  El cúbit pasa de estar en superposición (cualquier dirección) a estar en uno de los estados clásicos.  Después, si se repite la medida sin que intervenga ninguna operación, se produce el mismo resultado binario.  

Varios cúbits pueden estar [**entrelazados**](xref:microsoft.quantum.glossary#entanglement). Cuando se toma una medida de un cúbit entrelazado, se actualizan también los conocimientos del estado de los otros.

Ahora, estamos listos para demostrar cómo expresa Q# este comportamiento.  Comience con el programa más sencillo posible y compílelo para demostrar la superposición cuántica y el entrelazamiento cuántico.

## <a name="setup"></a>Configurar

En este tutorial, se usan programas host y se compone de dos partes:

1. Una serie de algoritmos cuánticos, implementados mediante el lenguaje de programación cuántica Q#.
1. Un programa host, implementado en Python o C#, que actúa como el punto de entrada principal e invoca operaciones de Q# para ejecutar algoritmos cuánticos.

#### <a name="python"></a>[Python](#tab/tabid-python)

1. Elija una ubicación para su aplicación

1. Cree un archivo llamado `Bell.qs`. Este archivo contendrá el código Q#.

1. Cree un archivo llamado `host.py`. Este archivo contendrá el código host Python.

#### <a name="c-command-line"></a>[Línea de comandos para C#](#tab/tabid-csharp)

1. Cree un nuevo proyecto de Q#

    ```bash
    dotnet new console -lang Q# --output Bell
    cd Bell
    ```

    Debería ver un archivo `.csproj`, un archivo Q# denominado `Operations.qs` y un archivo de programa host llamado `Driver.cs`

1. Cambie el nombre del archivo Q#

    ```bash
    mv Operation.qs Bell.qs
    ```

#### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs2019)

1. Creación de un nuevo proyecto

   * Abra Visual Studio.
   * En el menú **Archivo**, seleccione **Nuevo** -> **Proyecto...**
   * En el explorador de plantillas de proyecto, escriba `Q#` en el campo de búsqueda y seleccione la plantilla `Q# Application`.
   * Asígnele el nombre `Bell` a su proyecto

1. Cambie el nombre del archivo Q#

   * Vaya hasta **Explorador de soluciones**
   * Haga clic con el botón derecho en el archivo `Operations.qs`
   * Cambie su nombre por `Bell.qs`

* * *

## <a name="write-a-q-operation"></a>Escriba una operación de Q#

Nuestros objetivos son: preparar dos cúbits en un estado cuántico específico; demostrar cómo operar en los cúbits con Q# para cambiar su estado; y demostrar los efectos de la superposición y el entrelazamiento. Crearemos esto paso a paso para mostrar los estados del cúbit, las operaciones y la medida.

**Información general:**  En el primer código que aparece a continuación, mostramos cómo trabajar con cúbits en Q#.  Introduciremos dos operaciones, `M` y `X`, que transforman el estado de un cúbit. 

En este fragmento de código, se define una operación `Set` que toma como parámetro un cúbit y otro parámetro, `desired`, que representa el estado en el que queremos que esté el cúbit.  La operación `Set` toma una medida en el cúbit con la operación `M`.  En Q#, la medida de un cúbit siempre devuelve `Zero` o `One`.  Si la medida devuelve un valor distinto del deseado, Set "invierte" el cúbit; es decir, ejecuta una operación `X` que cambia el estado del cúbit a un nuevo estado en el que las probabilidades de que una medida devuelva `Zero` y `One` se invierten.  Para mostrar el efecto de la operación `Set`, se agrega una operación `TestBellState`.  Esta operación toma como entrada un `Zero` o `One`, llama a la operación `Set` un número determinado de veces con esa entrada y cuenta el número de veces que la medida del cúbit devolvió `Zero` y el número de veces que se devolvió `One`. Por supuesto, en esta primera simulación de la operación `TestBellState` esperamos que la salida muestre que todas las medidas de un cúbit establecidas con `Zero` como entrada del parámetro devolverán `Zero`, y todas las medidas de un cúbit establecidas con `One` como entrada del parámetro devolverán `One`.  Más adelante, agregaremos código a `TestBellState` para demostrar la superposición y el entrelazamiento.


### <a name="q-operation-code"></a>Código de operación de Q#

1. Reemplace el contenido del archivo Bell.qs con el siguiente código:

    ```qsharp
    namespace Quantum.Bell {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation Set(desired : Result, q1 : Qubit) : Unit {
            if (desired != M(q1)) {
                X(q1);
            }
        }
    }
    ```

    Ahora se puede llamar a esta operación para establecer un cúbit en un estado clásico, ya sea devolviendo `Zero` el 100 % del tiempo o devolviendo `One` el 100 % del tiempo.  `Zero` y `One` son constantes que representan los únicos dos resultados posibles de la medida de un cúbit.

    La operación `Set` mide el cúbit.
    Si el cúbit está en el estado que queremos, `Set` lo deja así; de lo contrario, al ejecutar la operación `X`, cambiamos el estado del cúbit al estado deseado.

### <a name="about-q-operations"></a>Acerca de las operaciones de Q#

Una operación Q# es una subrutina cuántica. Es decir, es una rutina invocable que contiene operaciones cuánticas.

Los argumentos de una operación se especifican como una tupla, entre paréntesis.

El tipo de valor devuelto de la operación se especifica después de un signo de dos puntos. En este caso, la operación de `Set` no devuelve ningún valor, por lo que se marca como retorno `Unit`. Este es el equivalente de Q# de `unit` en F#, que es aproximadamente análogo a `void` en C#, y una tupla vacía (`Tuple[()]`) en Python.

Ha usado dos operaciones cuánticas en la primera operación de Q#:

* La operación [M](xref:microsoft.quantum.intrinsic.m), que mide el estado del cúbit.
* La operación [x](xref:microsoft.quantum.intrinsic.x), que invierte el estado de un cúbit.

Una operación cuántica transforma el estado de un cúbit. Algunos usuarios hablan de puertas cuánticas en lugar de operaciones, por analogía con las puertas lógicas clásicas. Esto tiene su origen en los primeros tiempos de la computación cuántica, cuando los algoritmos eran una simple construcción teórica y se visualizaban como diagramas, de forma similar a los diagramas de circuitos de la computación clásica.

### <a name="add-q-test-code"></a>Agregar código de prueba de Q#

1. Agregue la siguiente operación al archivo `Bell.qs`, dentro del espacio de nombres, después del final de la operación de `Set`:

    ```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                Set(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            Set(Zero, qubit);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
    ```

    Esta operación (`TestBellState`) creará un bucle para `count` iteraciones, establecerá un valor de `initial` especificado en cúbits y, a continuación, medirá (`M`) el resultado. Recopilará estadísticas sobre cuántos ceros y unos se han medido y los devolverá al autor de la llamada. Realiza otra operación necesaria. Restablece el cúbit a un estado conocido (`Zero`) antes de devolverlo, lo que permite que otros usuarios asignen este cúbit en un estado conocido. Esto es necesario para la instrucción `using`.

### <a name="about-variables-in-q"></a>Acerca de las variables en Q#

De forma predeterminada, las variables en Q# son inmutables; su valor no se puede cambiar una vez que se enlazaron. La palabra clave `let` se utiliza para indicar el enlace de una variable inmutable. Los argumentos de la operación son siempre inmutables.

Si necesita una variable cuyo valor puede cambiar, como `numOnes` en el ejemplo, puede declarar la variable con la palabra clave `mutable`. Se puede cambiar el valor de una variable mutable mediante una instrucción `set`.

En ambos casos, el compilador deduce el tipo de una variable. Para las variables, Q# no requiere ninguna anotación de tipo.

### <a name="about-using-statements-in-q"></a>Acerca de las instrucciones `using` en Q#

La instrucción `using` también es especial para Q#. Se usa para asignar cúbits para su uso en un bloque de código. En Q#, todos los cúbits se asignan y liberan dinámicamente, en lugar de ser recursos fijos que están disponibles para toda la duración de un algoritmo complejo. Una instrucción `using` asigna un conjunto de cúbits al principio y libera esos cúbits al final del bloque.

## <a name="create-the-host-application-code"></a>Cree el código de aplicación host

#### <a name="python"></a>[Python](#tab/tabid-python)

1. Abra el archivo `host.py` y agregue el código siguiente:

    ```python
    import qsharp

    from qsharp import Result
    from Quantum.Bell import TestBellState

    initials = (Result.Zero, Result.One)

    for i in initials:
      res = TestBellState.simulate(count=1000, initial=i)
      (num_zeros, num_ones) = res
      print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4}')
    ```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

1. Reemplace el contenido del archivo `Driver.cs` por el código siguiente:

    ```csharp
    using System;

    using Microsoft.Quantum.Simulation.Core;
    using Microsoft.Quantum.Simulation.Simulators;

    namespace Quantum.Bell
    {
        class Driver
        {
            static void Main(string[] args)
            {
                using (var qsim = new QuantumSimulator())
                {
                    // Try initial values
                    Result[] initials = new Result[] { Result.Zero, Result.One };
                    foreach (Result initial in initials)
                    {
                        var res = TestBellState.Run(qsim, 1000, initial).Result;
                        var (numZeros, numOnes) = res;
                        System.Console.WriteLine(
                            $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4}");
                    }
                }

                System.Console.WriteLine("Press any key to continue...");
                Console.ReadKey();
            }
        }
    }
    ```

#### [](#tab/tabid-vs2019)

* * *

### <a name="about-the-host-application-code"></a>Sobre el código de aplicación host

#### <a name="python"></a>[Python](#tab/tabid-python)

La aplicación host de Python consta de tres partes:

* Calcule los argumentos necesarios para el algoritmo cuántico. En el ejemplo, `count` se fija en 1000 y `initial` es el valor inicial del cúbit.
* Ejecute el algoritmo cuántico llamando al método `simulate()` de la operación Q# importada.
* Procesamiento del resultado de la operación. En el ejemplo, `res` recibe el resultado de la operación. Aquí, el resultado es una tupla del número de ceros (`num_zeros`) y el número de unos (`num_ones`) que el simulador mide. Deconstruimos la tupla para obtener los dos campos e imprimir los resultados.

#### <a name="c"></a>[C#](#tab/tabid-csharp)

La aplicación host de C# tiene cuatro partes:

* Construya un simulador cuántico. En el ejemplo, `qsim` es el simulador.
* Calcule los argumentos necesarios para el algoritmo cuántico. En el ejemplo, `count` se fija en 1000 y `initial` es el valor inicial del cúbit.
* Ejecute el algoritmo cuántico. Cada operación de Q# genera una clase C# con el mismo nombre. Esta clase tiene un método `Run` que ejecuta la operación **de forma asincrónica**. La ejecución es asincrónica debido a que la ejecución en el hardware real será asincrónica. Dado que el método `Run` es asincrónico, se captura la propiedad `Result`. Esto bloquea la ejecución hasta que la tarea se completa y devuelve el resultado de forma sincrónicamente.
* Procesamiento del resultado de la operación. En el ejemplo, `res` recibe el resultado de la operación. Aquí, el resultado es una tupla del número de ceros (`numZeros`) y el número de unos (`numOnes`) que el simulador mide. Esto se devuelve como ValueTuple en C#. Deconstruimos la tupla para obtener los dos campos, imprimir los resultados y esperar una keypress.

#### [](#tab/tabid-vs2019)

* * *

## <a name="build-and-run"></a>Compilación y ejecución

#### <a name="python"></a>[Python](#tab/tabid-python)

1. Ejecute el siguiente comando en su terminal:

    ```
    python host.py
    ```

    Este comando ejecuta la aplicación host, que simula la operación Q#.

Los resultados deben ser:

```Output
Init:0    0s=1000 1s=0   
Init:1    0s=0    1s=1000
```

#### <a name="command-line--visual-studio-code"></a>[Línea de comandos/Visual Studio Code](#tab/tabid-csharp)

1. Ejecute lo siguiente en su terminal:

    ```bash
    dotnet run
    ```

    Este comando descargará automáticamente todos los paquetes necesarios, compilará la aplicación y, después, la ejecutará en la línea de comandos.

1. De forma alternativa, presione **F1** para abrir la paleta de comandos y seleccione **Depuración: Iniciar sin depurar.**
Es posible que se le pida que cree un nuevo archivo ``launch.json`` que describa cómo iniciar el programa.
El ``launch.json`` predeterminado debe funcionar bien en la mayoría de las aplicaciones.

Los resultados deben ser:

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

#### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs2019)

1. Solo presione `F5` y el programa debe compilarse y ejecutarse.

Los resultados deben ser:

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

El programa se cerrará después de presionar una tecla.

* * *

## <a name="prepare-superposition"></a>Preparar la superposición

**Introducción** Ahora veremos cómo expresa Q# las maneras de colocar los cúbits en superposición.  Recuerde que el estado de un cúbit puede ser una superposición de 0 y 1.  Usaremos la operación `Hadamard` para hacerlo. Si el cúbit está en cualquiera de los estados clásicos (al medir devuelve `Zero` siempre o `One` siempre), las operaciones `Hadamard` o `H` pondrán el cúbit en un estado tal que al medirlo, devolverá `Zero` el 50 % del tiempo y devolverá `One` el otro 50 % del tiempo.  Conceptualmente, el cúbit se puede considerar a medio camino entre `Zero` y `One`.  Ahora, cuando simulemos la operación `TestBellState`, veremos que los resultados devolverán aproximadamente un número igual de `Zero` y `One` después de medir.  

En primer lugar, intentaremos invertir el cúbit (si el cúbit está en estado `Zero` se invertirá a `One` y viceversa). Esto se logra con una operación `X` antes de medirlo en `TestBellState`:

```qsharp
X(qubit);
let res = M(qubit);
```

Ahora se invierten los resultados (después de presionar `F5`):

```Output
Init:Zero 0s=0    1s=1000
Init:One  0s=1000 1s=0
```

Sin embargo, todo lo que hemos visto hasta ahora es clásico. Ahora obtengamos un resultado cuántico. Lo único que tenemos que hacer es reemplazar la operación `X` de la ejecución anterior por una operación `H` o Hadamard. En lugar de voltear totalmente el cúbit de 0 a 1, solo lo voltearemos a la mitad. Las líneas reemplazadas en `TestBellState` ahora tienen el siguiente aspecto:

```qsharp
H(qubit);
let res = M(qubit);
```

Ahora tenemos resultados más interesantes:

```Output
Init:Zero 0s=484  1s=516
Init:One  0s=522  1s=478
```

Cada vez que medimos, solicitamos un valor clásico, pero el cúbit se encuentra a medio camino entre 0 y 1, por lo que obtenemos (estadísticamente) 0 la mitad del tiempo y 1 la otra mitad del tiempo. Esto se conoce como __superposición__ y nos proporciona nuestra primera vista real en un estado cuántico.

## <a name="prepare-entanglement"></a>Preparación del entrelazamiento

**Información general:**  Ahora veamos cómo expresa Q# las maneras de entrelazar los cúbits.  En primer lugar, establecemos el primer cúbit en el estado inicial y después usamos la operación `H` para ponerlo en superposición.  Luego, antes de medir el primer cúbit, usamos una nueva operación (`CNOT`), que significa Controlled-Not.  El resultado de ejecutar esta operación en dos cúbits es la inversión del segundo cúbit si el primero es `One`.  Ahora, los dos cúbits están entrelazados.  Nuestras estadísticas del primer cúbit no han cambiado (50-50 de probabilidades de `Zero` o `One` después de medir) pero ahora, cuando medimos el segundo cúbit, es __siempre__ igual que lo que se midió para el primer cúbit. Nuestro `CNOT` ha hecho el entrelazamiento de los dos cúbits, de modo que lo que le suceda a uno, le sucede al otro. Si invirtió las medidas (hizo la del segundo cúbit antes del primero), sucedería lo mismo. La primera medida sería aleatoria y la segunda sería en el paso de bloqueo con lo que se haya descubierto en primer lugar.

Lo primero que debemos hacer es asignar 2 cúbits en lugar de uno en `TestBellState`:

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

Esto nos permitirá agregar una nueva operación (`CNOT`) antes de medir (`M`) en `TestBellState`:

```qsharp
Set(initial, q0);
Set(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

Hemos agregado otra operación `Set` para inicializar el primer cúbit para asegurarnos de que siempre está en `Zero` cuando se inicia.

También necesitamos restablecer el segundo cúbit antes de liberarlo.

```qsharp
Set(Zero, q0);
Set(Zero, q1);
```

La rutina completa se ve ahora así:

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set (initial, q0);
                Set (Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

Si la ejecutamos, obtendremos exactamente el mismo resultado 50-50 que obtuvimos antes. Sin embargo, ahora nos interesa cómo reacciona el segundo cúbit al primero que se mide. Agregaremos esta estadística con una nueva versión de la operación `TestBellState`:

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set(initial, q0);
                Set(Zero, q1);

                H(q0);
                CNOT(q0, q1);
                let res = M(q0);

                if (M(q1) == res) {
                    set agree += 1;
                }

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes, agree);
    }
```

El nuevo valor devuelto (`agree`) realiza un seguimiento de cada vez que la medida del primer cúbit coincide con la medida del segundo. También tenemos que actualizar la aplicación host, según corresponda:

#### <a name="python"></a>[Python](#tab/tabid-python)

```python
import qsharp

from qsharp import Result
from Quantum.Bell import TestBellState

initials = {Result.Zero, Result.One} 

for i in initials:
    res = TestBellState.simulate(count=1000, initial=i)
    (num_zeros, num_ones, agree) = res
    print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4} agree={agree: <4}')
```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

```csharp
            using (var qsim = new QuantumSimulator())
            {
                // Try initial values
                Result[] initials = new Result[] { Result.Zero, Result.One };
                foreach (Result initial in initials)
                {
                    var res = TestBellState.Run(qsim, 1000, initial).Result;
                    var (numZeros, numOnes, agree) = res;
                    System.Console.WriteLine(
                        $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4} agree={agree,-4}");
                }
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
```

#### [](#tab/tabid-vs2019)

* * *

Ahora, cuando hacemos la ejecución, obtenemos algo muy asombroso:

```Output
Init:Zero 0s=499  1s=501  agree=1000
Init:One  0s=490  1s=510  agree=1000
```

Tal y como se indicó en la introducción, nuestras estadísticas del primer cúbit no han cambiado (50-50 de probabilidades de 0 o 1 después de medir) pero ahora, cuando medimos el segundo cúbit, es __siempre__ igual que lo que se midió para el primer cúbit, porque están entrelazados.

Enhorabuena, ha escrito su primer programa cuántico.

## <a name="next-steps"></a>Pasos siguientes

El tutorial sobre la [búsqueda de Grover](xref:microsoft.quantum.quickstarts.search) muestra cómo compilar y ejecutar una búsqueda de Grover, uno de los algoritmos de computación cuántica más populares, y es un buen ejemplo de un programa de Q# que se puede usar para resolver problemas reales con la computación cuántica.  

En [Introducción al kit de desarrollo de Microsoft Quantum](xref:microsoft.quantum.welcome) se recomiendan más formas de aprender Q# y programación cuántica.
