---
title: Explore el incumplimiento con Q#
description: Aprenda a escribir un programa Quantum en Q# . Desarrolle una aplicación de estado Bell mediante el kit de desarrollo de Microsoft Quantum (QDK)
author: geduardo
ms.author: v-edsanc
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6fd7494d341a83a1354d23a283d21a7ae535e49f
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834030"
---
# <a name="tutorial-explore-entanglement-with-q"></a>Tutorial: Exploración del entrelazamiento con Q\#

En este tutorial, se muestra cómo escribir un Q# programa que manipula y mide qubits y muestra los efectos de la superposición y el inenredo.

Escribirá una aplicación llamada Bell para demostrar el entrelazamiento cuántico.
El nombre Bell hace referencia a los estados de Bell, que son estados cuánticos específicos de dos cúbits que se usan para representar los ejemplos más sencillos de la superposición y el entrelazamiento cuántico.

## <a name="pre-requisites"></a>Requisitos previos

Si está listo para empezar a codificar, siga estos pasos antes de continuar: 

* [Instale](xref:microsoft.quantum.install) el kit de desarrollo de Quantum usando su entorno de desarrollo y lenguaje preferido.
* Si ya tiene instalado el QDK, asegúrese de que tiene [actualizada](xref:microsoft.quantum.update) la última versión

También puede seguir con la narrativa sin instalar QDK, revisando la información general del Q# lenguaje de programación y los primeros conceptos de la informática Quantum.

## <a name="in-this-tutorial-youll-learn-how-to"></a>En este tutorial, aprenderá a:

> [!div class="checklist"]
> * Operaciones de creación y combinación en Q\#
> * Crear operaciones para colocar qubits en la superposición, entangle y medirlos.
> * Muestre el incumplimiento de Quantum con un programa que se Q# ejecuta en un simulador. 

## <a name="demonstrating-qubit-behavior-with-the-qdk"></a>Demostrar el comportamiento de qubit con QDK

Mientras que los bits clásicos contienen un único valor binario, como 0 o 1, el estado de un [cúbit](xref:microsoft.quantum.glossary#qubit) puede ser una **superposición** de 0 y 1.  Conceptualmente, el estado de un qubit se puede considerar como una dirección en un espacio abstracto (también conocido como vector).  Un estado de qubit puede estar en cualquiera de las direcciones posibles. Los dos **estados clásicos** son las dos direcciones, que representan el 100 % de probabilidad de medir 0 y el 100 % de probabilidad de medir 1.

La acción de medir genera un resultado binario y cambia el estado del cúbit.
La medida produce un valor binario, ya sea 0 o 1.  El cúbit pasa de estar en superposición (cualquier dirección) a estar en uno de los estados clásicos.  Después, si se repite la medida sin que intervenga ninguna operación, se produce el mismo resultado binario.  

Varios cúbits pueden estar [**entrelazados**](xref:microsoft.quantum.glossary#entanglement).  Cuando se toma una medida de un cúbit entrelazado, se actualizan también los conocimientos del estado de los otros.

Ahora, estamos listos para demostrar cómo Q# expresa este comportamiento.  Comience con el programa más sencillo posible y compílelo para demostrar la superposición cuántica y el entrelazamiento cuántico.

## <a name="creating-a-no-locq-project"></a>Crear un Q# proyecto

Lo primero que tenemos que hacer es crear un nuevo Q# proyecto. En este tutorial vamos a usar el entorno basado en [ Q# aplicaciones con vs Code](xref:microsoft.quantum.install.standalone).

Para crear un nuevo proyecto, en VS Code: 

1. Haga clic en **Ver** -> **Paleta de comandos** y seleccione **Q#: Crear nuevo proyecto**.
2. Haga clic en **Aplicación de consola independiente**.
3. Vaya a la ubicación para guardar el proyecto y haga clic en **Crear proyecto**.
4. Cuando el proyecto se haya creado correctamente, haga clic en **Abrir nuevo proyecto...** abajo a la derecha.

En este caso, se ha llamado al proyecto `Bell` . Esto genera dos archivos: `Bell.csproj` , el archivo de proyecto y `Program.qs` , una plantilla de una Q# aplicación que se va a usar para escribir la aplicación. El contenido de `Program.qs` debe ser:

```qsharp
   namespace Bell {

      open Microsoft.Quantum.Canon;
      open Microsoft.Quantum.Intrinsic;
    

      @EntryPoint()
      operation HelloQ() : Unit {
          Message("Hello quantum world!");
      }
   }
```

## <a name="write-the-q-application"></a>Escritura de la \# aplicación Q
 
Nuestro objetivo es preparar dos qubits en un estado de Quantum específico, mostrando cómo operar en qubits con Q# para cambiar su estado y demostrar los efectos de la superposición y el incumplimiento. Compilaremos esta pieza por parte para introducir los Estados, las operaciones y la medida de qubit.

### <a name="initialize-qubit-using-measurement"></a>Inicializar qubit mediante medición

En el primer código que aparece a continuación, le mostramos cómo trabajar con qubits en Q# .  Introduciremos dos operaciones [`M`](xref:microsoft.quantum.intrinsic.m) y [`X`](xref:microsoft.quantum.intrinsic.x) que transformarán el estado de un qubit. En este fragmento de código, se define una operación `SetQubitState` que toma como parámetro un cúbit y otro parámetro, `desired`, que representa el estado en el que queremos que esté el cúbit.  La operación `SetQubitState` toma una medida en el cúbit con la operación `M`.  En Q# , una medida qubit siempre devuelve `Zero` o `One` .  Si la medida devuelve un valor que no es igual al valor deseado, `SetQubitState` "voltea" el qubit; es decir, ejecuta una `X` operación, que cambia el estado de qubit a un nuevo estado en el que las probabilidades de una medida devuelven `Zero` y `One` se invierten. De este modo, `SetQubitState` siempre coloca el qubit de destino en el estado deseado.

Reemplace el contenido de `Program.qs` por el código siguiente:


```qsharp
   namespace Bell {
       open Microsoft.Quantum.Intrinsic;
       open Microsoft.Quantum.Canon;

       operation SetQubitState(desired : Result, q1 : Qubit) : Unit {
           if (desired != M(q1)) {
               X(q1);
           }
       }
   }
```

Ahora se puede llamar a esta operación para establecer un cúbit en un estado clásico, ya sea devolviendo `Zero` el 100 % del tiempo o devolviendo `One` el 100 % del tiempo.
`Zero` y `One` son constantes que representan los únicos dos resultados posibles de la medida de un cúbit.

La operación `SetQubitState` mide el cúbit. Si el qubit está en el estado deseado, lo `SetQubitState` deja por sí solo; de lo contrario, al ejecutar la `X` operación, cambiamos el estado de qubit al estado deseado.

#### <a name="about-no-locq-operations"></a>Acerca de Q# las operaciones

Una Q# operación es una subrutina Quantum. Es decir, es una rutina invocable que contiene llamadas a otras operaciones Quantum.

Los argumentos de una operación se especifican como una tupla, entre paréntesis.

El tipo de valor devuelto de la operación se especifica después de un signo de dos puntos. En este caso, la operación de `SetQubitState` no devuelve ningún valor, por lo que se marca como retorno `Unit`. Es el Q# equivalente de `unit` en F #, que es aproximadamente análogo a `void` en C#, y una tupla vacía en Python ( `()` , representada por la sugerencia de tipo `Tuple[()]` ).

Ha usado dos operaciones Quantum en la primera Q# operación:

* La [`M`](xref:microsoft.quantum.intrinsic.m) operación, que mide el estado de qubit
* La [`X`](xref:microsoft.quantum.intrinsic.x) operación, que voltea el estado de un qubit

Una operación cuántica transforma el estado de un cúbit. Algunos usuarios hablan de puertas cuánticas en lugar de operaciones, por analogía con las puertas lógicas clásicas. Esto tiene su origen en los primeros tiempos de la computación cuántica, cuando los algoritmos eran una simple construcción teórica y se visualizaban como diagramas, de forma similar a los diagramas de circuitos de la computación clásica.

### <a name="counting-measurement-outcomes"></a>Recuento de los resultados de la medición

Para mostrar el efecto de la operación `SetQubitState`, se agrega una operación `TestBellState`. Esta operación toma como entrada un `Zero` o `One`, llama a la operación `SetQubitState` un número determinado de veces con esa entrada y cuenta el número de veces que la medida del cúbit devolvió `Zero` y el número de veces que se devolvió `One`. Por supuesto, en esta primera simulación de la operación `TestBellState` esperamos que la salida muestre que todas las medidas de un cúbit establecidas con `Zero` como entrada del parámetro devolverán `Zero`, y todas las medidas de un cúbit establecidas con `One` como entrada del parámetro devolverán `One`. Más adelante, agregaremos código a `TestBellState` para mostrar la superposición y el inenredo.

Agregue la siguiente operación al archivo `Program.qs`, dentro del espacio de nombres, después del final de la operación de `SetQubitState`:

```qsharp
   operation TestBellState(count : Int, initial : Result) : (Int, Int) {

       mutable numOnes = 0;
       using (qubit = Qubit()) {

           for (test in 1..count) {
               SetQubitState(initial, qubit);
               let res = M(qubit);

               // Count the number of ones we saw:
               if (res == One) {
                   set numOnes += 1;
               }
           }
            
           SetQubitState(Zero, qubit);
       }

       // Return number of times we saw a |0> and number of times we saw a |1>
       Message("Test results (# of 0s, # of 1s): ");
       return (count - numOnes, numOnes);
   }
```
Tenga en cuenta que hemos agregado una línea antes de `return` que imprima un mensaje explicativo en la consola con la función ( `Message` ) [Microsoft. Quantum. Intrinsic. Message]

Esta operación (`TestBellState`) creará un bucle para `count` iteraciones, establecerá un valor de `initial` especificado en cúbits y, a continuación, medirá (`M`) el resultado. Recopilará estadísticas sobre cuántos ceros y unos se han medido y los devolverá al autor de la llamada. Realiza otra operación necesaria. Restablece el cúbit a un estado conocido (`Zero`) antes de devolverlo, lo que permite que otros usuarios asignen este cúbit en un estado conocido. Esto es necesario para la instrucción `using`.

#### <a name="about-variables-in-q"></a>Acerca de las variables en Q\#

De forma predeterminada, las variables de Q# son inmutables; su valor no se puede cambiar una vez enlazado. La palabra clave `let` se utiliza para indicar el enlace de una variable inmutable. Los argumentos de la operación son siempre inmutables.

Si necesita una variable cuyo valor puede cambiar, como `numOnes` en el ejemplo, puede declarar la variable con la palabra clave `mutable`. Se puede cambiar el valor de una variable mutable mediante una instrucción `setQubitState`.

En ambos casos, el compilador deduce el tipo de una variable. Q# no requiere ninguna anotación de tipo para las variables.

#### <a name="about-using-statements-in-q"></a>Acerca `using` de las instrucciones en Q\#

La `using` instrucción también es especial para Q# . Se usa para asignar cúbits para su uso en un bloque de código. En Q# , todos los qubits se asignan y liberan dinámicamente, en lugar de ser recursos fijos que están ahí para toda la duración de un algoritmo complejo. Una instrucción `using` asigna un conjunto de cúbits al principio y libera esos cúbits al final del bloque.

## <a name="run-the-code-from-the-command-prompt"></a>Ejecutar el código desde el símbolo del sistema

Para ejecutar el código, es necesario especificar el compilador al *que* se puede llamar para que se ejecute cuando se proporciona el `dotnet run` comando. Esto se hace con un simple cambio en el Q# archivo agregando una línea que `@EntryPoint()` preceda directamente a la operación invocable: `TestBellState` en este caso. El código completo debe ser:

```qsharp
namespace Bell {
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Intrinsic;

    operation SetQubitState(desired : Result, target : Qubit) : Unit {
        if (desired != M(target)) {
            X(target);
        }
    }

    @EntryPoint()
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                SetQubitState(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, qubit);
        }

    // Return number of times we saw a |0> and number of times we saw a |1>
    Message("Test results (# of 0s, # of 1s): ");
    return (count - numOnes, numOnes);
    }
}
```

Para ejecutar el programa, es necesario especificar `count` los `initial` argumentos y desde el símbolo del sistema. Vamos a elegir, por ejemplo `count = 1000` , y `initial = One` . Escriba el comando siguiente:

```dotnetcli
dotnet run --count 1000 --initial One
```

Y debe observar el siguiente resultado:

```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

Si lo intenta, `initial = Zero` debe observar lo siguiente:

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

## <a name="prepare-superposition"></a>Preparar la superposición

Ahora veamos cómo Q# expresa cómo expresar qubits en la superposición.  Recuerde que el estado de un cúbit puede ser una superposición de 0 y 1.  Usaremos la operación `Hadamard` para hacerlo. Si el cúbit está en cualquiera de los estados clásicos (al medir devuelve `Zero` siempre o `One` siempre), las operaciones `Hadamard` o `H` pondrán el cúbit en un estado tal que al medirlo, devolverá `Zero` el 50 % del tiempo y devolverá `One` el otro 50 % del tiempo.  Conceptualmente, el cúbit se puede considerar a medio camino entre `Zero` y `One`.  Ahora, cuando simulemos la operación `TestBellState`, veremos que los resultados devolverán aproximadamente un número igual de `Zero` y `One` después de medir.  

### <a name="x-flips-qubit-state"></a>`X` Voltea el estado de qubit

En primer lugar, intentaremos invertir el cúbit (si el cúbit está en estado `Zero` se invertirá a `One` y viceversa). Esto se logra con una operación `X` antes de medirlo en `TestBellState`:

```qsharp
X(qubit);
let res = M(qubit);
```

Ahora se invierten los resultados:

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

Ahora vamos a explorar las propiedades Quantum de qubits.

### <a name="h-prepares-superposition"></a>`H` prepara la superposición

Lo único que tenemos que hacer es reemplazar la operación `X` de la ejecución anterior por una operación `H` o Hadamard. En lugar de voltear totalmente el cúbit de 0 a 1, solo lo voltearemos a la mitad. Las líneas reemplazadas en `TestBellState` ahora tienen el siguiente aspecto:

```qsharp
H(qubit);
let res = M(qubit);
```

Ahora tenemos resultados más interesantes:

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(496, 504)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```

```output
Test results (# of 0s, # of 1s):
(506, 494)
```

Cada vez que medimos, solicitamos un valor clásico, pero el cúbit se encuentra a medio camino entre 0 y 1, por lo que obtenemos (estadísticamente) 0 la mitad del tiempo y 1 la otra mitad del tiempo.
Esto se conoce como **superposición** y nos proporciona nuestra primera vista real en un estado cuántico.

## <a name="prepare-entanglement"></a>Preparación del entrelazamiento

Ahora veremos cómo expresa las Q# maneras de entangle qubits.
En primer lugar, establecemos el primer cúbit en el estado inicial y después usamos la operación `H` para ponerlo en superposición.  A continuación, antes de que se mida el primer qubit, usamos una nueva operación ( `CNOT` ), que significa *controlada*por.  El resultado de la ejecución de esta operación en dos qubits es voltear el segundo qubit si el primer qubit es `One` .  Ahora, los dos cúbits están entrelazados.  Nuestras estadísticas del primer cúbit no han cambiado (50-50 de probabilidades de `Zero` o `One` después de medir) pero ahora, cuando medimos el segundo cúbit, es __siempre__ igual que lo que se midió para el primer cúbit. Nuestro `CNOT` ha hecho el entrelazamiento de los dos cúbits, de modo que lo que le suceda a uno, le sucede al otro. Si invirtió las medidas (hizo la del segundo cúbit antes del primero), sucedería lo mismo. La primera medida sería aleatoria y la segunda sería en el paso de bloqueo con lo que se haya descubierto en primer lugar.

Lo primero que debemos hacer es asignar dos qubits en lugar de uno en `TestBellState` :

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

Esto nos permitirá agregar una nueva operación (`CNOT`) antes de medir (`M`) en `TestBellState`:

```qsharp
SetQubitState(initial, q0);
SetQubitState(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

Hemos agregado otra operación `SetQubitState` para inicializar el primer cúbit para asegurarnos de que siempre está en `Zero` cuando se inicia.

También necesitamos restablecer el segundo cúbit antes de liberarlo.

```qsharp
SetQubitState(Zero, q0);
SetQubitState(Zero, q1);
```

La rutina completa se ve ahora así:

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
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
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

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
            
            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return times we saw |0>, times we saw |1>, and times measurements agreed
        Message("Test results (# of 0s, # of 1s, # of agreements)");
        return (count-numOnes, numOnes, agree);
    }
```

El nuevo valor devuelto (`agree`) realiza un seguimiento de cada vez que la medida del primer cúbit coincide con la medida del segundo.

Ejecutar el código que obtenemos:

```dotnetcli
dotnet run --count 1000 --initial One
```
```output
(505, 495, 1000)
```
```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s, # of agreements)
(507, 493, 1000)
```

Tal y como se indicó en la introducción, nuestras estadísticas del primer cúbit no han cambiado (50-50 de probabilidades de 0 o 1 después de medir) pero ahora, cuando medimos el segundo cúbit, es __siempre__ igual que lo que se midió para el primer cúbit, porque están entrelazados.

## <a name="next-steps"></a>Pasos siguientes

En el tutorial [de la búsqueda de Grover](xref:microsoft.quantum.quickstarts.search) se muestra cómo compilar y ejecutar la búsqueda de Grover, uno de los algoritmos de procesamiento de Quantum más populares y ofrece un buen ejemplo de un Q# programa que se puede usar para solucionar problemas reales con la informática Quantum.  

Introducción al [Kit de desarrollo de Quantum](xref:microsoft.quantum.welcome) recomienda más formas de aprender Q# y la programación de Quantum.
