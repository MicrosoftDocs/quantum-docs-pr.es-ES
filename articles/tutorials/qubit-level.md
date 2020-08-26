---
title: Escribir y simular programas de nivel de qubit en Q#
description: Tutorial paso a paso sobre cómo escribir y simular un programa Quantum que opere en el nivel de qubit individual
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 10/06/2019
uid: microsoft.quantum.circuit-tutorial
ms.topic: tutorial
no-loc:
- Q#
- $$v
ms.openlocfilehash: 39b2d762c0efbfa4bb3a60a1dcee6bcbe2bd91a9
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863332"
---
# <a name="tutorial-write-and-simulate-qubit-level-programs-in-q"></a>Tutorial: escribir y simular programas de nivel de qubit en Q\#

Este es el tutorial del kit de desarrollo de Quantum sobre cómo escribir y simular un programa Quantum básico que opere en qubits individuales. 

Aunque Q# se creó principalmente como un lenguaje de programación de alto nivel para los programas Quantum de gran escala, se puede usar de la misma manera que para explorar el nivel inferior de los programas Quantum: dirigirse directamente a qubits específicos.
La flexibilidad de Q# permite a los usuarios enfocar los sistemas Quantum desde cualquier nivel de abstracción y en este tutorial se profundiza en los qubits.
En concreto, echamos un vistazo a la transformación de [Fourier de Quantum](https://en.wikipedia.org/wiki/Quantum_Fourier_transform), una subrutina que es integral de muchos algoritmos Quantum más grandes.

Tenga en cuenta que esta vista de bajo nivel del procesamiento de la información Quantum se describe a menudo en términos de "[circuitos Quantum](xref:microsoft.quantum.concepts.circuits)", que representan la aplicación secuencial de las puertas de qubits específicas de un sistema.

Por lo tanto, las operaciones de una y varias qubit que se aplican secuencialmente se pueden representar fácilmente en un "diagrama de circuitos".
En nuestro caso, vamos a definir una Q# operación para realizar la transformación completa de qubit de Quantum de tres-, que tiene la siguiente representación como un circuito:

<br/>
<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

## <a name="prerequisites"></a>Requisitos previos

* [Instale](xref:microsoft.quantum.install) el kit de desarrollo de Quantum usando su entorno de desarrollo y lenguaje preferido.
* Si ya tiene instalado el QDK, asegúrese de que tiene [actualizada](xref:microsoft.quantum.update) la última versión


## <a name="in-this-tutorial-youll-learn-how-to"></a>En este tutorial, aprenderá a:

> [!div class="checklist"]
> * Definir operaciones Quantum en Q#
> * Llamar a Q# operaciones directamente desde el símbolo del sistema o mediante un programa host clásico
> * Simular una operación Quantum desde la asignación qubit a la salida de medición
> * Observe cómo evoluciona el WaveFunction simulado del sistema Quantum durante la operación

La ejecución de un programa Quantum con el kit de desarrollo de Quantum de Microsoft normalmente consta de dos partes:
1. El propio programa, que se implementa mediante el Q# lenguaje de programación Quantum, y, a continuación, se invoca para ejecutarse en un equipo Quantum o en un simulador Quantum. Se componen de 
    - Q# operaciones: subrutinas que actúan sobre registros Quantum y 
    - Q# funciones: subrutinas clásicas que se usan en el algoritmo Quantum.
2. El punto de entrada que se usa para llamar al programa Quantum y especificar el equipo de destino en el que se debe ejecutar.
    Esto puede realizarse directamente desde el símbolo del sistema o a través de un programa de host escrito en un lenguaje de programación clásico como Python o C#.
    En este tutorial se incluyen instrucciones para cualquier método que prefiera.

## <a name="allocate-qubits-and-define-quantum-operations"></a>Asignación de qubits y definición de operaciones Quantum

La primera parte de este tutorial consiste en definir la Q# operación `Perform3qubitQFT` , que realiza la transformación de Fourier de Quantum en tres qubits. 

Además, usaremos la [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) función para observar cómo evoluciona el WaveFunction simulado de nuestro sistema qubit en la operación.

El primer paso es crear el Q# proyecto y el archivo.
Los pasos para ello dependen del entorno que se utilizará para llamar al programa, y puede encontrar los detalles en las guías de [instalación](xref:microsoft.quantum.install)correspondientes.

Le guiaremos a través de los componentes del archivo paso a paso, pero el código también está disponible como un bloque completo a continuación.

### <a name="namespaces-to-access-other-no-locq-operations"></a>Espacios de nombres para tener acceso a otras Q# operaciones
Dentro del archivo, primero definimos el espacio de nombres al `NamespaceQFT` que tendrá acceso el compilador.
Para que nuestra operación haga uso de Q# las operaciones existentes, abrimos los `Microsoft.Quantum.<>` espacios de nombres pertinentes.

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    // operations go here
}
```

### <a name="define-operations-with-arguments-and-returns"></a>Definir operaciones con argumentos y devoluciones
A continuación, definimos la `Perform3qubitQFT` operación:

```qsharp
    operation Perform3qubitQFT() : Unit {
        // do stuff
    }
```

Por ahora, la operación no toma ningún argumento y no devuelve nada---en este caso escribimos que devuelve un `Unit` objeto, que es similar a `void` en C# o una tupla vacía, `Tuple[()]` , en Python.
Más adelante, se modificará para que devuelva una matriz de resultados de medición, en cuyo punto se `Unit` reemplazará por `Result[]` . 

### <a name="allocate-qubits-with-using"></a>Asignar qubits con `using`
Dentro de nuestra Q# operación, asignamos primero un registro de tres qubits con la `using` instrucción:

```qsharp
        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

        }
```

Con `using` , los qubits se asignan automáticamente en el estado $ \ket {0} $. Podemos comprobarlo mediante [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) y [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) , que imprimen una cadena y el estado actual del sistema en la consola.

> [!NOTE]
> Las `Message(<string>)` `DumpMachine()` funciones y (desde [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) y [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics) , respectivamente) se imprimen directamente en la consola. Al igual que un cálculo de Quantum real, Q# no nos permite acceder directamente a los Estados de qubit.
> Sin embargo, como `DumpMachine` imprime el estado actual del equipo de destino, puede proporcionar información valiosa para la depuración y el aprendizaje cuando se usa junto con el simulador de estado completo.


### <a name="applying-single-qubit-and-controlled-gates"></a>Aplicación de una sola qubit y de las puertas controladas

A continuación, se aplican las puertas que componen la propia operación.
Q# ya contiene muchas de las puertas de Quantum básicas como operaciones en el [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) espacio de nombres y no son excepciones. 

Dentro de una Q# operación, las instrucciones que invocan llamadas se ejecutarán en orden secuencial.
Por lo tanto, la primera puerta que se va a aplicar es [`H`](xref:microsoft.quantum.intrinsic.h) (Hadamard) al primer qubit:

<br/>
<img src="../media/qft_firstH.PNG" alt="Circuit diagram for three qubit QFT through first Hadamard" width="120">

Para aplicar una operación a un qubit específico desde un registro (es decir, un único `Qubit` de una matriz `Qubit[]` ) usamos la notación de índice estándar.
Por lo tanto, aplicar el [`H`](xref:microsoft.quantum.intrinsic.h) al primer qubit de nuestro registro `qs` tiene el siguiente formato:

```qsharp
            H(qs[0]);
```

Además de aplicar la `H` puerta (Hadamard) a qubits individuales, el circuito QFT se compone principalmente de [`R1`](xref:microsoft.quantum.intrinsic.r1) rotaciones controladas.
Una `R1(θ, <qubit>)` operación en general deja el componente $ \ket {0} $ de la qubit sin modificar, mientras se aplica un giro de $e ^ {i\theta} $ al componente $ \ket {1} $.

#### <a name="controlled-operations"></a>Operaciones controladas

Q# facilita en gran medida la ejecución de una operación en uno o varios qubits de control.
En general, simplemente se antepone la llamada a `Controlled` y los argumentos de la operación cambian como:

 `Op(<normal args>)` $ \to $ `Controlled Op([<control qubits>], (<normal args>))` .

Tenga en cuenta que el control qubits debe proporcionarse como una matriz, incluso si es un qubit único.

Después de `H` , vemos que las siguientes puertas son las `R1` puertas que actúan en la primera qubit (y que están controladas por el segundo/tercer):

<br/>
<img src="../media/qft_firstqubit.PNG" alt="Circuit diagram for three qubit QFT through first qubit" width="310">

Lo llamamos con

```qsharp
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));
```

Tenga en cuenta que usamos la [`PI()`](xref:microsoft.quantum.math.pi) función del [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) espacio de nombres para definir los giros en términos de PI radianes.
Además, se divide por un `Double` (por ejemplo, `2.0` ) porque la división por un entero `2` produciría un error de tipo. 

> [!TIP]
> `R1(π/2)` y `R1(π/4)` son equivalentes a `S` las `T` operaciones y (también en `Microsoft.Quantum.Intrinsic` ).


Después de aplicar las `H` operaciones pertinentes y las rotaciones controladas al segundo y tercer qubits:

```qsharp
            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);
```

solo necesitamos aplicar una [`SWAP`](xref:microsoft.quantum.intrinsic.swap) puerta para completar el circuito:

```qsharp
            SWAP(qs[2], qs[0]);
```

Esto es necesario porque la naturaleza de la transformación de Fourier de Quantum genera el qubits en orden inverso, por lo que los intercambios permiten una integración perfecta de la subrutina en algoritmos más grandes.

Por lo tanto, hemos terminado de escribir las operaciones de nivel de qubit de la transformación Fourier de Quantum en nuestra Q# operación:

<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

Sin embargo, no podemos llamarlo un día todavía.
Nuestro qubits estaba en el estado $ \ket {0} $ cuando lo hemos asignado y, en gran parte, en nuestra vida, deberíamos Q# dejar cosas de la misma manera en que las encontramos (o mejor).

### <a name="deallocate-qubits"></a>Desasignar qubits

Se llama de [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) nuevo para ver el estado posterior a la operación y, por último, se aplica [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) al registro qubit para restablecer el qubits en $ \ket {0} $ antes de completar la operación:

```qsharp
            Message("After:");
            DumpMachine();

            ResetAll(qs);
```

Requerir que todos los qubits desasignados se establezcan explícitamente en $ \ket {0} $ es una característica básica de Q# , ya que permite que otras operaciones sepan que su estado es precisamente cuando empiezan a usar esos mismos qubits (un recurso escaso).
Además, esto garantiza que no se inenreden con ningún otro qubits del sistema.
Si el restablecimiento no se realiza al final de un `using` bloque de asignación, se producirá un error en tiempo de ejecución.

El Q# archivo completo debe tener el siguiente aspecto:

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    operation Perform3qubitQFT() : Unit {

        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("After:");
            DumpMachine();

            ResetAll(qs);
        }
    }
}
```


Una Q# vez completado el archivo y la operación, el programa Quantum está listo para ser llamado y simulado.

## <a name="execute-the-program"></a>Ejecución del programa

Una vez definida Q# la operación en un `.qs` archivo, ahora es necesario llamar a esa operación y observar cualquier dato clásico devuelto.
Por ahora, no se devuelve nada (Recuerde que la operación definida anteriormente devuelve `Unit` ), pero, cuando se modifica posteriormente la Q# operación para devolver una matriz de resultados de la medición ( `Result[]` ), se solucionará este error.

Aunque el Q# programa está omnipresente en todos los entornos que se usan para llamarlo, la manera de hacerlo será diferente. Como tal, simplemente siga las instrucciones de la pestaña correspondiente a su configuración: trabajar desde la Q# aplicación o mediante un programa host en Python o C#.

#### <a name="command-prompt"></a>[Símbolo del sistema](#tab/tabid-cmdline)

Ejecutar el Q# programa desde el símbolo del sistema solo requiere un pequeño cambio en el Q# archivo.

Simplemente agregue `@EntryPoint()` a una línea que preceda a la definición de la operación:

```qsharp
    @EntryPoint()
    operation Perform3qubitQFT() : Unit {
        // ...
```

Para ejecutar el programa, abra el terminal en la carpeta del proyecto y escriba

```dotnetcli
dotnet run
```

Tras la ejecución, debería ver los `Message` `DumpMachine` resultados y siguientes impresos en la consola.


#### <a name="python"></a>[Python](#tab/tabid-python)

Cree un archivo de host de Python: `host.py` .

El archivo de host se construye de la siguiente manera: 
1. En primer lugar, se importa el `qsharp` módulo, que registra el cargador de módulos para la Q# interoperabilidad. 
    Esto permite Q# que los espacios de nombres (por ejemplo, el que `NamespaceQFT` hemos definido en nuestro Q# archivo) aparezcan como módulos de Python, desde los que se pueden importar Q# operaciones.
2. A continuación, importe las Q# operaciones que llamaremos directamente---en este caso, `Perform3qubitQFT` .
    Solo es necesario importar el punto de entrada en un Q# programa (es decir, _no_ operaciones como `H` y `R1` , que son llamadas por otras Q# operaciones, pero nunca por el host clásico).
3. En simulación de Q# operaciones o funciones, use el formulario `<Q#callable>.simulate(<args>)` para ejecutarlas en el `QuantumSimulator()` equipo de destino. 

> [!NOTE]
> Si deseamos llamar a la operación en otro equipo, por ejemplo `ResourceEstimator()` , simplemente usaremos `<Q#callable>.estimate_resources(<args>)` .
> En general, Q# las operaciones son independientes de las máquinas en las que se ejecutan, pero algunas características como `DumpMachine` pueden comportarse de forma diferente.

4. Tras realizar la simulación, la llamada a la operación devolverá valores tal como se define en el Q# archivo.
    Por ahora, no se devuelve nada, pero más adelante veremos un ejemplo de la asignación y el procesamiento de estos valores.
    Con los datos resultantes en nuestras manos y en todo el clásico, podemos hacer todo lo que nos gustaría.

El `host.py` archivo completo debe ser el siguiente:

```python
import qsharp
from NamespaceQFT import Perform3qubitQFT

Perform3qubitQFT.simulate()
```

Ejecute el archivo Python e impreso en la consola. debería ver los `Message` resultados y `DumpMachine` siguientes. 


#### <a name="c"></a>[C#](#tab/tabid-csharp)

Siguiendo las mismas instrucciones que en la [Guía de instalación](xref:microsoft.quantum.install.cs), cree un archivo de host de C# y cambie su nombre a `host.cs` .

El host de C# tiene cuatro partes:
1. Construya un simulador cuántico.
    En el código siguiente, esta es la variable `qsim` .
2. Calcule los argumentos necesarios para el algoritmo cuántico.
    En este ejemplo no hay ninguno.
3. Ejecute el algoritmo cuántico. 
    Cada Q# operación genera una clase de C# con el mismo nombre. 
    Esta clase tiene un método `Run` que ejecuta la operación **de forma asincrónica**.
    La ejecución es asincrónica debido a que la ejecución en el hardware real será asincrónica. 
    Dado que el `Run` método es asincrónico, llamamos al `Wait()` método; Esto bloquea la ejecución hasta que la tarea se completa y devuelve el resultado sincrónicamente. 
4. Procesa el resultado devuelto de la operación.
    Por ahora, la operación no devuelve nada.


```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                Perform3QubitQFT.Run(qsim).Wait();
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}

```
Ejecute la aplicación y la salida debe coincidir con la que aparece a continuación.
El programa se cerrará después de presionar una tecla.
***

```Output
Initial state |000>:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
After:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
```

Cuando se llama en el simulador de estado completo, `DumpMachine()` proporciona estas representaciones múltiples del WaveFunction del estado de Quantum. Los Estados posibles de una $n sistema $-qubit pueden estar representados por los Estados de base de $2 ^ n $ computacional, cada uno con un coeficiente complejo correspondiente (simplemente una amplitud y una fase).
Los Estados de base de cálculo corresponden a todas las posibles cadenas binarias de longitud $n $---, es decir, todas las combinaciones posibles de los Estados qubit $ \ket {0} $ y $ \ket {1} $, donde cada dígito binario corresponde a una qubit individual.

La primera fila proporciona un comentario con los identificadores del qubits correspondiente en su orden significativo.
Qubit `2` es el "más importante" simplemente significa que en la representación binaria del vector de estado de base $ \ket{i} $, el estado de qubit `2` corresponde al dígito situado más a la izquierda. Por ejemplo, $ \ket {6} = \ket {110} $ incluye qubits `2` y `1` ambos en $ \ket {1} $ y qubit `0` en $ \ket {0} $.


El resto de las filas describen la amplitud de probabilidad de medir el vector de estado de base $ \ket{i} $ en formatos cartesianos y polares.
En detalle para la primera fila de nuestro estado de entrada $ \ket {000} $:
* **`|0>:`** esta fila corresponde al `0` Estado de base de cálculo (dado que la asignación posterior de estado inicial era $ \ket {000} $, esperamos que este sea el único estado con amplitud de probabilidad en este momento).
* **`1.000000 +  0.000000 i`**: la amplitud de probabilidad en formato cartesiano.
* **` == `**: el `equal` signo separa ambas representaciones equivalentes.
* **`********************`**: Una representación gráfica de la magnitud, el número de `*` es proporcional a la probabilidad de medir este vector de estado. 
* **`[ 1.000000 ]`**: el valor numérico de la magnitud
* **`    ---`**: Representación gráfica de la fase de amplitud.
* **`[ 0.0000 rad ]`**: valor numérico de la fase (en radianes).

Tanto la magnitud como la fase se muestran con una representación gráfica. La representación de la magnitud es sencilla: muestra una barra de `*` y cuanto mayor sea la probabilidad, mayor será la barra. Para la fase, consulte [pruebas y depuración: funciones de volcado](xref:microsoft.quantum.guide.testingdebugging#dump-functions) de memoria para las posibles representaciones de símbolos basadas en intervalos de ángulo.


Por lo tanto, la salida impresa ilustra que nuestras puertas programadas transformaron nuestro estado desde

$ $ \ket{\psi} \_ {Initial} = \ket {000} $ $

to 

$ $ \begin{align} \ket{\psi} \_ {final} &= \frac {1} {\sqrt {8} } \left (\ket {000} + \ket {001} + \ket {010} + \ket {011} + \ket {100} + \ket {101} + \ket {110} + \ket {111} \right) \\ \\ &= \frac {1} {\sqrt{2 ^ n}} \sum \_ {j = 0} ^ {2 ^ n-1} \ket{j}, \end{align} $ $

que es precisamente el comportamiento de la transformación de Fourier 3-qubit. 

Si tiene curiosidad sobre cómo se ven afectados otros Estados de entrada, le recomendamos que experimente con la aplicación de las operaciones de qubit antes de la transformación.

## <a name="adding-measurements"></a>Agregar medidas

Desafortunadamente, una piedra angular de la mecánica de Quantum nos indica que un sistema Quantum real no puede tener una función de este tipo `DumpMachine` . En su lugar, nos obligamos a extraer información a través de medidas, que en general no solo proporcionan el estado completo del Quantum, sino que también pueden modificar drásticamente el propio sistema.
Hay muchos tipos de mediciones Quantum, pero nos centraremos en las mediciones más básicas: las medidas proyectadas en un único qubits.
A medida que se mide de forma determinada (por ejemplo, la base de cálculo $ \{ \ket {0} , \ket {1} \} $), el estado de qubit se proyecta en el estado de base medido---, por lo tanto, se destruye cualquier superposición entre los dos.

Para implementar las medidas dentro de un Q# programa, usamos la `M` operación (from `Microsoft.Quantum.Intrinsic` ), que devuelve un `Result` tipo.

En primer lugar, se modifica la `Perform3QubitQFT` operación para devolver una matriz de resultados de medida, `Result[]` , en lugar de `Unit` .

```qsharp
    operation Perform3QubitQFT() : Result[] {
```

#### <a name="define-and-initialize-result-array"></a>Definición e inicialización de una `Result[]` matriz

Antes de asignar qubits (es decir, antes de la `using` instrucción), se declara y se enlaza esta matriz de longitud 3 (una `Result` para cada qubit): 

```qsharp
        mutable resultArray = new Result[3];
```

La `mutable` palabra clave preorientada `resultArray` permite reenlazar la variable más adelante en el código---por ejemplo, al agregar los resultados de la medida.

#### <a name="perform-measurements-in-a-for-loop-and-add-results-to-array"></a>Realizar mediciones en un `for` bucle y agregar resultados a la matriz

Después de las operaciones de transformación de Fourier dentro del `using` bloque, inserte el código siguiente:

```qsharp
            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }
```
La [`IndexRange`](xref:microsoft.quantum.arrays.indexrange) función a la que se llama en una matriz (por ejemplo, nuestra matriz de qubits `qs` ) devuelve un intervalo sobre los índices de la matriz. Aquí se usa en nuestro `for` bucle para medir secuencialmente cada qubit mediante la `M(qs[i])` instrucción.
Cada `Result` tipo medido ( `Zero` o `One` ) se agrega a continuación a la posición de índice correspondiente en `resultArray` con una instrucción Update-and-resign.

> [!NOTE]
> La sintaxis de esta instrucción es única para Q# , pero corresponde a la reasignación de variables similar que se ha `resultArray[i] <- M(qs[i])` detectado en otros lenguajes, como F # y R.

La palabra clave `set` siempre se usa para reasignar variables enlazadas mediante `mutable` .

#### <a name="return-resultarray"></a>Devolver `resultArray`

Con los tres qubits medidos y los resultados agregados a `resultArray` , es seguro restablecer y desasignar el qubits como antes.
Después del `using` cierre del bloque, inserte

```qsharp
        return resultArray;
```
para devolver el resultado de la operación en última instancia. 

### <a name="understanding-the-effects-of-measurement"></a>Descripción de los efectos de la medición

Vamos a cambiar la ubicación de las `DumpMachine` funciones para generar el estado antes y después de las mediciones.
El código de operación final debería ser similar al siguiente: 

```qsharp
    operation Perform3QubitQFT() : Result[] {

        mutable resultArray = new Result[3];

        using (qs = Qubit[3]) {

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("Before measurement: ");
            DumpMachine();

            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }

            Message("After measurement: ");
            DumpMachine();

            ResetAll(qs);
        }
        return resultArray;
    }
}
```

Si está trabajando desde el símbolo del sistema, la matriz devuelta se imprimirá directamente en la consola al final de la ejecución.
De lo contrario, actualice el programa host para procesar la matriz devuelta.

#### <a name="command-prompt"></a>[Símbolo del sistema](#tab/tabid-cmdline)

Para comprender mejor la matriz devuelta que se va a imprimir en la consola de, podemos agregar otra `Message` en el Q# archivo justo antes de la `return` instrucción:

```qsharp
        Message("Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
        return resultArray;
```

Ejecute el proyecto y el resultado debe ser similar al siguiente:

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]
```

#### <a name="python"></a>[Python](#tab/tabid-python)

Actualice el programa de Python a lo siguiente:

```python
import qsharp
from NamespaceQFT import Perform3QubitQFT

measurementResult = Perform3QubitQFT.simulate()
print("\n")
print("Measured post-QFT state: [qubit0, qubit1, qubit2]")
print(measurementResult)

# reversing order to show corresponding basis state in binary form
binaryCompBasisState = ""
for i in measurementResult:
    binaryCompBasisState = str(i) + binaryCompBasisState
print("Corresponding basis state in binary:")
print("|" + binaryCompBasisState + ">")
```

Ejecute el archivo y el resultado debe ser similar al siguiente:

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[1, 1, 0]

Corresponding basis state in binary:
|011>
```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

Ahora que la operación devuelve un resultado, reemplace la llamada al método `Wait()` con la captura de la `Result` propiedad. Esto sigue logrando la misma Synchronicity descrita anteriormente y podemos enlazar directamente este valor a la variable `measurementResult` .

```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                var measurementResult = Perform3QubitQFT.Run(qsim).Result;
                System.Console.WriteLine(
                    $"Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
                System.Console.WriteLine(
                    measurementResult);

                // reversing order to show corresponding basis state in binary form
                string binaryCompBasisState = String.Empty;

                foreach (Result i in measurementResult)
                {
                    string iString = i.ToString();
                    binaryCompBasisState = iString + binaryCompBasisState;
                }
                binaryCompBasisState = "|" + binaryCompBasisState + ">";
                System.Console.WriteLine(
                    $"Corresponding basis state in binary:");
                System.Console.WriteLine(
                    binaryCompBasisState);
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}
```

Ejecute el proyecto y el resultado debe ser similar al siguiente:

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]

Corresponding basis state in binary:
|ZeroOneOne>

Press any key to continue...
```
***

Esta salida muestra algunos aspectos diferentes:
1. Al comparar el resultado devuelto con la medición previa `DumpMachine` , _no_ se ilustra claramente la superposición post-QFT en función de los Estados de base.
    Una medida solo devuelve un estado de base único, con una probabilidad determinada por la amplitud de ese estado en el WaveFunction del sistema.
2. A partir de la medición posterior `DumpMachine` , vemos que la medida _cambia_ el estado en sí, lo que lo proyecta desde la superposición inicial sobre los Estados de base hasta el estado de base única que corresponde al valor medido.

Si fuera a repetir esta operación muchas veces, veremos que las estadísticas de resultados comenzarán a ilustrar la superposición igualmente ponderada del estado posterior a la QFT que da lugar a un resultado aleatorio en cada captura.
_Sin embargo_, además de ser ineficaces y seguir siendo imperfectos, esto solo reproduciría las amplitudes relativas de los Estados de base, no las fases relativas entre ellas.
Esto último no es un problema en este ejemplo, pero veremos que las fases relativas aparecen si se proporciona una entrada más compleja a QFT de $ \ket {000} $.

#### <a name="partial-measurements"></a>Medidas parciales 
Para explorar cómo la medición de solo algunos qubits del registro puede afectar al estado del sistema, intente agregar lo siguiente dentro del `for` bucle, después de la línea de medida:
```qsharp
                let iString = IntAsString(i);
                Message("After measurement of qubit " + iString + ":");
                DumpMachine();
```

Tenga en cuenta que para tener acceso a la `IntAsString` función tendrá que agregar 
```qsharp
    open Microsoft.Quantum.Convert;
```
con el resto de las instrucciones de espacio de nombres `open` .

En la salida resultante, verá la proyección gradual en subespacios a medida que se mide cada qubit.


## <a name="use-the-no-locq-libraries"></a>Uso de las Q# bibliotecas
Tal y como se mencionó en la introducción, gran parte de la Q# capacidad de los demás tiene en cuenta que le permite abstraer las preocupaciones de trabajar con qubits individuales.
En realidad, si desea desarrollar programas Quantum de gran tamaño aplicables, preocuparse de si una `H` operación va antes o después de que una rotación determinada solo le ralentice. 

Las Q# bibliotecas contienen la operación [QFT](xref:microsoft.quantum.canon.qft) , que se puede realizar simplemente y aplicar para cualquier número de qubits.
Para probarlo, defina una nueva operación en el Q# archivo que tenga el mismo contenido de `Perform3QubitQFT` , pero con todo lo que haya entre el primero `H` y el `SWAP` reemplazado por dos líneas sencillas:
```qsharp
            let register = BigEndian(qs);    //from Microsoft.Quantum.Arithmetic
            QFT(register);                   //from Microsoft.Quantum.Canon
```
La primera línea simplemente crea una [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) expresión de la matriz asignada de qubits, `qs` , que es lo que la operación [QFT](xref:microsoft.quantum.canon.qft) toma como argumento.
Esto corresponde al orden de índice de qubits en el registro.

Para tener acceso a estas operaciones, agregue `open` instrucciones para sus respectivos espacios de nombres al principio del Q# archivo:
```qsharp
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Arithmetic;
```

Ahora, ajuste el programa host para que llame al nombre de la nueva operación (por ejemplo `PerformIntrinsicQFT` ,) y asígnele un giro.

Para ver las ventajas reales del uso de las Q# operaciones de biblioteca, cambie el número de qubits a algo distinto de `3` :
```qsharp
        mutable resultArray = new Result[4]; 

        using (qs = Qubit[4]) {
            //...
        }
```
Por tanto, puede aplicar el QFT adecuado para cualquier número determinado de qubits, sin tener que preocuparse por el desorden de nuevas `H` operaciones y giros en cada qubit.

Tenga en cuenta que el simulador de Quantum tarda más tiempo en ejecutarse a medida que aumenta el número de qubits---exactamente por qué le parecemos el hardware Quantum real.













