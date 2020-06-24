---
title: 'Escribir y simular programas de nivel de qubit en p #'
description: Tutorial paso a paso sobre cómo escribir y simular un programa Quantum que opere en el nivel de qubit individual
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 10/06/2019
uid: microsoft.quantum.circuit-tutorial
ms.topic: tutorial
ms.openlocfilehash: e7ebdec4cd1aa201030d82759a3aa56473b26417
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275346"
---
# <a name="tutorial-write-and-simulate-qubit-level-programs-in-q"></a><span data-ttu-id="b7692-103">Tutorial: escribir y simular programas de nivel de qubit en Q\#</span><span class="sxs-lookup"><span data-stu-id="b7692-103">Tutorial: Write and simulate qubit-level programs in Q\#</span></span>

<span data-ttu-id="b7692-104">Este es el tutorial del kit de desarrollo de Quantum sobre cómo escribir y simular un programa Quantum básico que opere en qubits individuales.</span><span class="sxs-lookup"><span data-stu-id="b7692-104">Welcome to the Quantum Development Kit tutorial on writing and simulating a basic quantum program that operates on individual qubits.</span></span> 

<span data-ttu-id="b7692-105">Aunque Q # se creó principalmente como un lenguaje de programación de alto nivel para los programas Quantum de gran escala, se puede usar de la misma manera que para explorar el nivel inferior de los programas Quantum: dirigirse directamente a qubits específicos.</span><span class="sxs-lookup"><span data-stu-id="b7692-105">Although Q# was primarily created as a high-level programming language for large-scale quantum programs, it can just as easily be used to explore the lower level of quantum programs: directly addressing specific qubits.</span></span>
<span data-ttu-id="b7692-106">La flexibilidad de Q # permite a los usuarios enfocar los sistemas Quantum desde cualquier nivel de abstracción y en este tutorial se profundiza en los qubits.</span><span class="sxs-lookup"><span data-stu-id="b7692-106">The flexibility of Q# allows users to approach quantum systems from any such level of abstraction, and in this tutorial we dive into the qubits themselves.</span></span>
<span data-ttu-id="b7692-107">En concreto, echamos un vistazo a la transformación de [Fourier de Quantum](https://en.wikipedia.org/wiki/Quantum_Fourier_transform), una subrutina que es integral de muchos algoritmos Quantum más grandes.</span><span class="sxs-lookup"><span data-stu-id="b7692-107">Specifically, we take a look under the hood of the [quantum Fourier transform](https://en.wikipedia.org/wiki/Quantum_Fourier_transform), a subroutine that is integral to many larger quantum algorithms.</span></span>

<span data-ttu-id="b7692-108">Tenga en cuenta que esta vista de bajo nivel del procesamiento de la información Quantum se describe a menudo en términos de "[circuitos Quantum](xref:microsoft.quantum.concepts.circuits)", que representan la aplicación secuencial de las puertas de qubits específicas de un sistema.</span><span class="sxs-lookup"><span data-stu-id="b7692-108">Note that this low-level view of quantum information processing is often described in terms of "[quantum circuits](xref:microsoft.quantum.concepts.circuits)," which represent the sequential application of gates to specific qubits of a system.</span></span>

<span data-ttu-id="b7692-109">Por lo tanto, las operaciones de una y varias qubit que se aplican secuencialmente se pueden representar fácilmente en un "diagrama de circuitos".</span><span class="sxs-lookup"><span data-stu-id="b7692-109">Thus, the single- and multi-qubit operations we sequentially apply can be readily represented in a "circuit diagram."</span></span>
<span data-ttu-id="b7692-110">En nuestro caso, vamos a definir una operación de Q # para realizar la transformación completa de qubit de Quantum de tres-, que tiene la siguiente representación como circuito:</span><span class="sxs-lookup"><span data-stu-id="b7692-110">In our case, we will define a Q# operation to perform the full three-qubit quantum Fourier transform, which has the following representation as a circuit:</span></span>

<br/>
<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

## <a name="prerequisites"></a><span data-ttu-id="b7692-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b7692-111">Prerequisites</span></span>

* <span data-ttu-id="b7692-112">[Instale](xref:microsoft.quantum.install) el kit de desarrollo de Quantum usando su entorno de desarrollo y lenguaje preferido.</span><span class="sxs-lookup"><span data-stu-id="b7692-112">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your preferred language and development environment.</span></span>
* <span data-ttu-id="b7692-113">Si ya tiene instalado el QDK, asegúrese de que tiene [actualizada](xref:microsoft.quantum.update) la última versión</span><span class="sxs-lookup"><span data-stu-id="b7692-113">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>


## <a name="in-this-tutorial-youll-learn-how-to"></a><span data-ttu-id="b7692-114">En este tutorial, aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="b7692-114">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="b7692-115">Definición de operaciones Quantum en Q #</span><span class="sxs-lookup"><span data-stu-id="b7692-115">Define quantum operations in Q#</span></span>
> * <span data-ttu-id="b7692-116">Llamar a las operaciones de Q # directamente desde la línea de comandos o mediante un programa host clásico</span><span class="sxs-lookup"><span data-stu-id="b7692-116">Call Q# operations directly from the command line or using a classical host program</span></span>
> * <span data-ttu-id="b7692-117">Simular una operación Quantum desde la asignación qubit a la salida de medición</span><span class="sxs-lookup"><span data-stu-id="b7692-117">Simulate a quantum operation from qubit allocation to measurement output</span></span>
> * <span data-ttu-id="b7692-118">Observe cómo evoluciona el WaveFunction simulado del sistema Quantum durante la operación</span><span class="sxs-lookup"><span data-stu-id="b7692-118">Observe how the quantum system's simulated wavefunction evolves throughout the operation</span></span>

<span data-ttu-id="b7692-119">La ejecución de un programa Quantum con el kit de desarrollo de Quantum de Microsoft normalmente consta de dos partes:</span><span class="sxs-lookup"><span data-stu-id="b7692-119">Running a quantum program with Microsoft's Quantum Development Kit typically consists of two parts:</span></span>
1. <span data-ttu-id="b7692-120">El propio programa, que se implementa mediante el lenguaje de programación Q # Quantum, y, a continuación, se invoca para ejecutarse en un equipo Quantum o en un simulador Quantum.</span><span class="sxs-lookup"><span data-stu-id="b7692-120">The program itself, which is implemented using the Q# quantum programming language, and then invoked to run on a quantum computer or quantum simulator.</span></span> <span data-ttu-id="b7692-121">Se componen de</span><span class="sxs-lookup"><span data-stu-id="b7692-121">These consist of</span></span> 
    - <span data-ttu-id="b7692-122">Operaciones de Q #: subrutinas que actúan sobre registros Quantum y</span><span class="sxs-lookup"><span data-stu-id="b7692-122">Q# operations: subroutines acting on quantum registers, and</span></span> 
    - <span data-ttu-id="b7692-123">Funciones de Q #: subrutinas clásicas usadas en el algoritmo Quantum.</span><span class="sxs-lookup"><span data-stu-id="b7692-123">Q# functions: classical subroutines used within the quantum algorithm.</span></span>
2. <span data-ttu-id="b7692-124">El punto de entrada que se usa para llamar al programa Quantum y especificar el equipo de destino en el que se debe ejecutar.</span><span class="sxs-lookup"><span data-stu-id="b7692-124">The entry point used to call the quantum program and specify the target machine on which it should be run.</span></span>
    <span data-ttu-id="b7692-125">Esto se puede hacer directamente desde la línea de comandos o a través de un programa de host escrito en un lenguaje de programación clásico como Python o C#.</span><span class="sxs-lookup"><span data-stu-id="b7692-125">This can be done directly from the command line, or through a host program written in a classical programming language like Python or C#.</span></span>
    <span data-ttu-id="b7692-126">En este tutorial se incluyen instrucciones para cualquier método que prefiera.</span><span class="sxs-lookup"><span data-stu-id="b7692-126">This tutorial includes instructions for whichever method you prefer.</span></span>

## <a name="allocate-qubits-and-define-quantum-operations"></a><span data-ttu-id="b7692-127">Asignación de qubits y definición de operaciones Quantum</span><span class="sxs-lookup"><span data-stu-id="b7692-127">Allocate qubits and define quantum operations</span></span>

<span data-ttu-id="b7692-128">La primera parte de este tutorial consiste en definir la operación Q # `Perform3qubitQFT` , que realiza la transformación de Fourier de Quantum en tres qubits.</span><span class="sxs-lookup"><span data-stu-id="b7692-128">The first part of this tutorial consists of defining the Q# operation `Perform3qubitQFT`, which performs the quantum Fourier transform on three qubits.</span></span> 

<span data-ttu-id="b7692-129">Además, usaremos la [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) función para observar cómo evoluciona el WaveFunction simulado de nuestro sistema qubit en la operación.</span><span class="sxs-lookup"><span data-stu-id="b7692-129">In addition, we will use the [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) function to observe how the simulated wavefunction of our three qubit system evolves across the operation.</span></span>

<span data-ttu-id="b7692-130">El primer paso es crear el proyecto y el archivo de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="b7692-130">The first step is creating your Q# project and file.</span></span>
<span data-ttu-id="b7692-131">Los pasos para ello dependen del entorno que se utilizará para llamar al programa, y puede encontrar los detalles en las guías de [instalación](xref:microsoft.quantum.install)correspondientes.</span><span class="sxs-lookup"><span data-stu-id="b7692-131">The steps for this depend on the environment you will use to call the program, and you can find the details in the respective [installation guides](xref:microsoft.quantum.install).</span></span>

<span data-ttu-id="b7692-132">Le guiaremos a través de los componentes del archivo paso a paso, pero el código también está disponible como un bloque completo a continuación.</span><span class="sxs-lookup"><span data-stu-id="b7692-132">We will walk you through the components of the file step-by-step, but the code is also available as a full block below.</span></span>

### <a name="namespaces-to-access-other-q-operations"></a><span data-ttu-id="b7692-133">Espacios de nombres para tener acceso a otras operaciones de Q #</span><span class="sxs-lookup"><span data-stu-id="b7692-133">Namespaces to access other Q# operations</span></span>
<span data-ttu-id="b7692-134">Dentro del archivo, primero definimos el espacio de nombres al `NamespaceQFT` que tendrá acceso el compilador.</span><span class="sxs-lookup"><span data-stu-id="b7692-134">Inside the file, we first define the namespace `NamespaceQFT` which will be accessed by the compiler.</span></span>
<span data-ttu-id="b7692-135">Para que nuestra operación haga uso de las operaciones de Q # existentes, abrimos los `Microsoft.Quantum.<>` espacios de nombres pertinentes.</span><span class="sxs-lookup"><span data-stu-id="b7692-135">For our operation to make use of existing Q# operations, we open the relevant `Microsoft.Quantum.<>` namespaces.</span></span>

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    // operations go here
}
```

### <a name="define-operations-with-arguments-and-returns"></a><span data-ttu-id="b7692-136">Definir operaciones con argumentos y devoluciones</span><span class="sxs-lookup"><span data-stu-id="b7692-136">Define operations with arguments and returns</span></span>
<span data-ttu-id="b7692-137">A continuación, definimos la `Perform3qubitQFT` operación:</span><span class="sxs-lookup"><span data-stu-id="b7692-137">Next, we define the `Perform3qubitQFT` operation:</span></span>

```qsharp
    operation Perform3qubitQFT() : Unit {
        // do stuff
    }
```

<span data-ttu-id="b7692-138">Por ahora, la operación no toma ningún argumento y no devuelve nada---en este caso escribimos que devuelve un `Unit` objeto, que es similar a `void` en C# o una tupla vacía, `Tuple[()]` , en Python.</span><span class="sxs-lookup"><span data-stu-id="b7692-138">For now, the operation takes no arguments and does not return anything---in this case we write that it returns a `Unit` object, which is akin to `void` in C# or an empty tuple, `Tuple[()]`, in Python.</span></span>
<span data-ttu-id="b7692-139">Más adelante, se modificará para que devuelva una matriz de resultados de medición, en cuyo punto se `Unit` reemplazará por `Result[]` .</span><span class="sxs-lookup"><span data-stu-id="b7692-139">Later, we will modify it to return an array of measurement results, at which point `Unit` will be replaced by `Result[]`.</span></span> 

### <a name="allocate-qubits-with-using"></a><span data-ttu-id="b7692-140">Asignar qubits con`using`</span><span class="sxs-lookup"><span data-stu-id="b7692-140">Allocate qubits with `using`</span></span>
<span data-ttu-id="b7692-141">Dentro de nuestra operación de Q #, primero asignamos un registro de tres qubits con la `using` instrucción:</span><span class="sxs-lookup"><span data-stu-id="b7692-141">Within our Q# operation, we first allocate a register of three qubits with the `using` statement:</span></span>

```qsharp
        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

        }
```

<span data-ttu-id="b7692-142">Con `using` , los qubits se asignan automáticamente en el estado $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="b7692-142">With `using`, the qubits are automatically allocated in the $\ket{0}$ state.</span></span> <span data-ttu-id="b7692-143">Podemos comprobarlo mediante [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) y [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) , que imprimen una cadena y el estado actual del sistema en la consola.</span><span class="sxs-lookup"><span data-stu-id="b7692-143">We can verify this by using [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) and [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine), which print a string and the system's current state to the console.</span></span>

> [!NOTE]
> <span data-ttu-id="b7692-144">Las `Message(<string>)` `DumpMachine()` funciones y (desde [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) y [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics) , respectivamente) se imprimen directamente en la consola.</span><span class="sxs-lookup"><span data-stu-id="b7692-144">The `Message(<string>)` and `DumpMachine()` functions (from [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) and [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics), respectively) both print directly to the console.</span></span> <span data-ttu-id="b7692-145">Al igual que un cálculo de Quantum real, Q # no nos permite acceder directamente a los Estados de qubit.</span><span class="sxs-lookup"><span data-stu-id="b7692-145">Just like a real quantum computation, Q# does not allow us to directly access qubit states.</span></span>
> <span data-ttu-id="b7692-146">Sin embargo, como `DumpMachine` imprime el estado actual del equipo de destino, puede proporcionar información valiosa para la depuración y el aprendizaje cuando se usa junto con el simulador de estado completo.</span><span class="sxs-lookup"><span data-stu-id="b7692-146">However, as `DumpMachine` prints the target machine's current state, it can provide valuable insight for debugging and learning when used in conjunction with the full state simulator.</span></span>


### <a name="applying-single-qubit-and-controlled-gates"></a><span data-ttu-id="b7692-147">Aplicación de una sola qubit y de las puertas controladas</span><span class="sxs-lookup"><span data-stu-id="b7692-147">Applying single-qubit and controlled gates</span></span>

<span data-ttu-id="b7692-148">A continuación, se aplican las puertas que componen la propia operación.</span><span class="sxs-lookup"><span data-stu-id="b7692-148">Next, we apply the gates which comprise the operation itself.</span></span>
<span data-ttu-id="b7692-149">Q # ya contiene muchas de las puertas de Quantum básicas como operaciones en el [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) espacio de nombres y no son excepciones.</span><span class="sxs-lookup"><span data-stu-id="b7692-149">Q# already contains many basic quantum gates as operations in the [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) namespace, and these are no exception.</span></span> 

<span data-ttu-id="b7692-150">Dentro de una operación de Q #, las instrucciones que invocan llamadas se ejecutarán en orden secuencial.</span><span class="sxs-lookup"><span data-stu-id="b7692-150">Within a Q# operation, the statements invoking callables will of course be executed in sequential order.</span></span>
<span data-ttu-id="b7692-151">Por lo tanto, la primera puerta que se va a aplicar es [`H`](xref:microsoft.quantum.intrinsic.h) (Hadamard) al primer qubit:</span><span class="sxs-lookup"><span data-stu-id="b7692-151">Hence, the first gate to apply is the [`H`](xref:microsoft.quantum.intrinsic.h) (Hadamard) to the first qubit:</span></span>

<br/>
<img src="../media/qft_firstH.PNG" alt="Circuit diagram for three qubit QFT through first Hadamard" width="120">

<span data-ttu-id="b7692-152">Para aplicar una operación a un qubit específico desde un registro (es decir, un único `Qubit` de una matriz `Qubit[]` ) usamos la notación de índice estándar.</span><span class="sxs-lookup"><span data-stu-id="b7692-152">To apply an operation to a specific qubit from a register (i.e. a single `Qubit` from an array `Qubit[]`) we use standard index notation.</span></span>
<span data-ttu-id="b7692-153">Por lo tanto, aplicar el [`H`](xref:microsoft.quantum.intrinsic.h) al primer qubit de nuestro registro `qs` tiene el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="b7692-153">So, applying the [`H`](xref:microsoft.quantum.intrinsic.h) to the first qubit of our register `qs` takes the form:</span></span>

```qsharp
            H(qs[0]);
```

<span data-ttu-id="b7692-154">Además de aplicar la `H` puerta (Hadamard) a qubits individuales, el circuito QFT se compone principalmente de [`R1`](xref:microsoft.quantum.intrinsic.r1) rotaciones controladas.</span><span class="sxs-lookup"><span data-stu-id="b7692-154">Besides applying the `H` (Hadamard) gate to individual qubits, the QFT circuit consists primarily of controlled [`R1`](xref:microsoft.quantum.intrinsic.r1) rotations.</span></span>
<span data-ttu-id="b7692-155">Una `R1(θ, <qubit>)` operación en general deja el componente $ \ket {0} $ de la qubit sin modificar, mientras se aplica un giro de $e ^ {i\theta} $ al componente $ \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="b7692-155">An `R1(θ, <qubit>)` operation in general leaves the $\ket{0}$ component of the qubit unchanged, while applying a rotation of $e^{i\theta}$ to the $\ket{1}$ component.</span></span>

#### <a name="controlled-operations"></a><span data-ttu-id="b7692-156">Operaciones controladas</span><span class="sxs-lookup"><span data-stu-id="b7692-156">Controlled operations</span></span>

<span data-ttu-id="b7692-157">Q # hace que sea muy fácil condicionar la ejecución de una operación en uno o varios qubits de control.</span><span class="sxs-lookup"><span data-stu-id="b7692-157">Q# makes it extremely easy to condition the execution of an operation upon one or multiple control qubits.</span></span>
<span data-ttu-id="b7692-158">En general, simplemente se antepone la llamada a `Controlled` y los argumentos de la operación cambian como:</span><span class="sxs-lookup"><span data-stu-id="b7692-158">In general, we merely preface the call with `Controlled`, and the operation arguments change as:</span></span>

 <span data-ttu-id="b7692-159">`Op(<normal args>)`$ \to $ `Controlled Op([<control qubits>], (<normal args>))` .</span><span class="sxs-lookup"><span data-stu-id="b7692-159">`Op(<normal args>)` $\to$ `Controlled Op([<control qubits>], (<normal args>))`.</span></span>

<span data-ttu-id="b7692-160">Tenga en cuenta que el control qubits debe proporcionarse como una matriz, incluso si es un qubit único.</span><span class="sxs-lookup"><span data-stu-id="b7692-160">Note that the control qubits must be provided as an array, even if it is a single qubit.</span></span>

<span data-ttu-id="b7692-161">Después de `H` , vemos que las siguientes puertas son las `R1` puertas que actúan en la primera qubit (y que están controladas por el segundo/tercer):</span><span class="sxs-lookup"><span data-stu-id="b7692-161">After the `H`, we see that the next gates are the `R1` gates acting on the first qubit (and controlled by the second/third):</span></span>

<br/>
<img src="../media/qft_firstqubit.PNG" alt="Circuit diagram for three qubit QFT through first qubit" width="310">

<span data-ttu-id="b7692-162">Lo llamamos con</span><span class="sxs-lookup"><span data-stu-id="b7692-162">We call these with</span></span>

```qsharp
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));
```

<span data-ttu-id="b7692-163">Tenga en cuenta que usamos la [`PI()`](xref:microsoft.quantum.math.pi) función del [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) espacio de nombres para definir los giros en términos de PI radianes.</span><span class="sxs-lookup"><span data-stu-id="b7692-163">Note that we use the [`PI()`](xref:microsoft.quantum.math.pi) function from the [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) namespace to define the rotations in terms of pi radians.</span></span>
<span data-ttu-id="b7692-164">Además, se divide por un `Double` (por ejemplo, `2.0` ) porque la división por un entero `2` produciría un error de tipo.</span><span class="sxs-lookup"><span data-stu-id="b7692-164">Additionally, we divide by a `Double` (e.g. `2.0`) because dividing by an integer `2` would throw a type error.</span></span> 

> [!TIP]
> <span data-ttu-id="b7692-165">`R1(π/2)`y `R1(π/4)` son equivalentes a `S` las `T` operaciones y (también en `Microsoft.Quantum.Intrinsic` ).</span><span class="sxs-lookup"><span data-stu-id="b7692-165">`R1(π/2)` and `R1(π/4)` are equivalent to the `S` and `T` operations (also in `Microsoft.Quantum.Intrinsic`).</span></span>


<span data-ttu-id="b7692-166">Después de aplicar las `H` operaciones pertinentes y las rotaciones controladas al segundo y tercer qubits:</span><span class="sxs-lookup"><span data-stu-id="b7692-166">After applying the relevant `H` operations and controlled rotations to the second and third qubits:</span></span>

```qsharp
            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);
```

<span data-ttu-id="b7692-167">solo necesitamos aplicar una [`SWAP`](xref:microsoft.quantum.intrinsic.swap) puerta para completar el circuito:</span><span class="sxs-lookup"><span data-stu-id="b7692-167">we need only apply a [`SWAP`](xref:microsoft.quantum.intrinsic.swap) gate to complete the circuit:</span></span>

```qsharp
            SWAP(qs[2], qs[0]);
```

<span data-ttu-id="b7692-168">Esto es necesario porque la naturaleza de la transformación de Fourier de Quantum genera el qubits en orden inverso, por lo que los intercambios permiten una integración perfecta de la subrutina en algoritmos más grandes.</span><span class="sxs-lookup"><span data-stu-id="b7692-168">This is necessary because the nature of the quantum Fourier transform outputs the qubits in reverse order, so the swaps allow for seamless integration of the subroutine into larger algorithms.</span></span>

<span data-ttu-id="b7692-169">Por lo tanto, hemos terminado de escribir las operaciones de nivel de qubit de la transformación Fourier de Quantum en nuestra operación de Q #:</span><span class="sxs-lookup"><span data-stu-id="b7692-169">Hence we have finished writing the qubit-level operations of the quantum Fourier transform into our Q# operation:</span></span>

<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

<span data-ttu-id="b7692-170">Sin embargo, no podemos llamarlo un día todavía.</span><span class="sxs-lookup"><span data-stu-id="b7692-170">However, we can't call it a day just yet.</span></span>
<span data-ttu-id="b7692-171">Nuestro qubits estaba en el estado $ \ket {0} $ cuando lo hemos asignado y, como en la vida, en Q # deberíamos dejar cosas de la misma manera en que las encontramos (o mejor).</span><span class="sxs-lookup"><span data-stu-id="b7692-171">Our qubits were in state $\ket{0}$ when we allocated them, and much like in life, in Q# we should leave things the same way we found them (or better!).</span></span>

### <a name="deallocate-qubits"></a><span data-ttu-id="b7692-172">Desasignar qubits</span><span class="sxs-lookup"><span data-stu-id="b7692-172">Deallocate qubits</span></span>

<span data-ttu-id="b7692-173">Se llama de [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) nuevo para ver el estado posterior a la operación y, por último, se aplica [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) al registro qubit para restablecer el qubits en $ \ket {0} $ antes de completar la operación:</span><span class="sxs-lookup"><span data-stu-id="b7692-173">We call [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) again to see the post-operation state, and finally apply [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) to the qubit register to reset our qubits to $\ket{0}$ before completing the operation:</span></span>

```qsharp
            Message("After:");
            DumpMachine();

            ResetAll(qs);
```

<span data-ttu-id="b7692-174">Requerir que todos los qubits desasignados se establezcan explícitamente en $ \ket {0} $ es una característica básica de Q #, ya que permite que otras operaciones sepan su estado precisamente cuando empiecen a usar esos mismos qubits (un recurso insuficiente).</span><span class="sxs-lookup"><span data-stu-id="b7692-174">Requiring that all deallocated qubits be explicitly set to $\ket{0}$ is a basic feature of Q#, as it allows other operations to know their state precisely when they begin using those same qubits (a scarce resource).</span></span>
<span data-ttu-id="b7692-175">Además, esto garantiza que no se inenreden con ningún otro qubits del sistema.</span><span class="sxs-lookup"><span data-stu-id="b7692-175">Additionally, this assures that they not be entangled with any other qubits in the system.</span></span>
<span data-ttu-id="b7692-176">Si el restablecimiento no se realiza al final de un `using` bloque de asignación, se producirá un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b7692-176">If the reset is not performed at the end of a `using` allocation block, a runtime error will be thrown.</span></span>

<span data-ttu-id="b7692-177">El archivo de preguntas y respuestas completo debe tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="b7692-177">Your full Q# file should now look like this:</span></span>

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


<span data-ttu-id="b7692-178">Una vez finalizada la operación y el archivo de preguntas y respuestas, nuestro programa Quantum está listo para ser llamado y simulado.</span><span class="sxs-lookup"><span data-stu-id="b7692-178">With the Q# file and operation complete, our quantum program is ready to be called and simulated.</span></span>

## <a name="execute-the-program"></a><span data-ttu-id="b7692-179">Ejecutar el programa</span><span class="sxs-lookup"><span data-stu-id="b7692-179">Execute the program</span></span>

<span data-ttu-id="b7692-180">Una vez definida nuestra operación de Q # en un `.qs` archivo, ahora es necesario llamar a esa operación y observar cualquier dato clásico devuelto.</span><span class="sxs-lookup"><span data-stu-id="b7692-180">Having defined our Q# operation in a `.qs` file, we now need to call that operation and observe any returned classical data.</span></span>
<span data-ttu-id="b7692-181">Por ahora, no se devuelve nada (Recuerde que la operación definida anteriormente devuelve `Unit` ), pero cuando se modifica posteriormente la operación Q # para devolver una matriz de resultados de la medición ( `Result[]` ), nos abordaremos esto.</span><span class="sxs-lookup"><span data-stu-id="b7692-181">For now, there isn't anything returned (recall that our operation defined above returns `Unit`), but when we later modify the Q# operation to return an array of measurement results (`Result[]`), we will address this.</span></span>

<span data-ttu-id="b7692-182">Aunque el programa Q # está omnipresente en todos los entornos que se usan para llamarlo, la manera de hacerlo es variar.</span><span class="sxs-lookup"><span data-stu-id="b7692-182">While the Q# program is ubiquitous across the environments used to call it, the manner of doing so will of course vary.</span></span> <span data-ttu-id="b7692-183">Por lo tanto, solo tiene que seguir las instrucciones de la pestaña correspondiente a su configuración: trabajar desde la aplicación de línea de comandos de Q # o mediante un programa host en Python o C#.</span><span class="sxs-lookup"><span data-stu-id="b7692-183">As such, simply follow the instructions in the tab corresponding to your setup: working from the Q# command line application or using a host program in Python or C#.</span></span>

#### <a name="command-line"></a>[<span data-ttu-id="b7692-184">Línea de comandos</span><span class="sxs-lookup"><span data-stu-id="b7692-184">Command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="b7692-185">Ejecutar el programa Q # desde la línea de comandos solo requiere un pequeño cambio en el archivo de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="b7692-185">Running the Q# program from the command line requires only a small change to the Q# file.</span></span>

<span data-ttu-id="b7692-186">Simplemente agregue `@EntryPoint()` a una línea que preceda a la definición de la operación:</span><span class="sxs-lookup"><span data-stu-id="b7692-186">Simply add `@EntryPoint()` to a line preceding the operation definition:</span></span>

```qsharp
    @EntryPoint()
    operation Perform3qubitQFT() : Unit {
        // ...
```

<span data-ttu-id="b7692-187">Para ejecutar el programa, abra el terminal en la carpeta del proyecto y escriba</span><span class="sxs-lookup"><span data-stu-id="b7692-187">To run the program, open the terminal in the folder of your project and enter</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="b7692-188">Tras la ejecución, debería ver los `Message` `DumpMachine` resultados y siguientes impresos en la consola.</span><span class="sxs-lookup"><span data-stu-id="b7692-188">Upon execution, you should see the `Message` and `DumpMachine` outputs below printed in your console.</span></span>


#### <a name="python"></a>[<span data-ttu-id="b7692-189">Python</span><span class="sxs-lookup"><span data-stu-id="b7692-189">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="b7692-190">Cree un archivo de host de Python: `host.py` .</span><span class="sxs-lookup"><span data-stu-id="b7692-190">Create a Python host file: `host.py`.</span></span>

<span data-ttu-id="b7692-191">El archivo de host se construye de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="b7692-191">The host file is constructed as follows:</span></span> 
1. <span data-ttu-id="b7692-192">En primer lugar, se importa el `qsharp` módulo, que registra el cargador de módulos para la interoperabilidad de Q #.</span><span class="sxs-lookup"><span data-stu-id="b7692-192">First, we import the `qsharp` module, which registers the module loader for Q# interoperability.</span></span> 
    <span data-ttu-id="b7692-193">Esto permite que los espacios de nombres de Q # (por ejemplo, el que `NamespaceQFT` se definen en el archivo q #) aparezcan como módulos de Python, desde los que se pueden importar operaciones de Q #.</span><span class="sxs-lookup"><span data-stu-id="b7692-193">This allows Q# namespaces (e.g. the `NamespaceQFT` we defined in our Q# file) to appear as Python modules, from which we can import Q# operations.</span></span>
2. <span data-ttu-id="b7692-194">A continuación, importe las operaciones de Q # que llamaremos directamente---en este caso, `Perform3qubitQFT` .</span><span class="sxs-lookup"><span data-stu-id="b7692-194">Then, import the Q# operations which we will directly invoke---in this case, `Perform3qubitQFT`.</span></span>
    <span data-ttu-id="b7692-195">Solo es necesario importar el punto de entrada en un programa de preguntas y respuestas (es decir, _no_ en operaciones como `H` y `R1` , que son llamadas por otras operaciones de q #, pero nunca por el host clásico).</span><span class="sxs-lookup"><span data-stu-id="b7692-195">We need only import the entry point into a Q# program (i.e. _not_ operations like `H` and `R1`, which are called by other Q# operations but never by the classical host).</span></span>
3. <span data-ttu-id="b7692-196">En la simulación de operaciones o funciones de Q #, use el formulario `<Q#callable>.simulate(<args>)` para ejecutarlas en el `QuantumSimulator()` equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="b7692-196">In simulating Q# operations or functions, use the form `<Q#callable>.simulate(<args>)` to run them on the `QuantumSimulator()` target machine.</span></span> 

> [!NOTE]
> <span data-ttu-id="b7692-197">Si deseamos llamar a la operación en otro equipo, por ejemplo `ResourceEstimator()` , simplemente usaremos `<Q#callable>.estimate_resources(<args>)` .</span><span class="sxs-lookup"><span data-stu-id="b7692-197">If we wanted to call the operation on a different machine, for example the `ResourceEstimator()`, we would simply use `<Q#callable>.estimate_resources(<args>)`.</span></span>
> <span data-ttu-id="b7692-198">En general, las operaciones de Q # son independientes de las máquinas en las que se ejecutan, pero algunas características como `DumpMachine` pueden comportarse de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="b7692-198">In general, Q# operations are agnostic to the machines on which they're run, but some features such as `DumpMachine` may behave differently.</span></span>

4. <span data-ttu-id="b7692-199">Tras realizar la simulación, la llamada a la operación devolverá valores tal como se define en el archivo de preguntas y respuestas.</span><span class="sxs-lookup"><span data-stu-id="b7692-199">Upon performing the simulation, the operation call will return values as defined in the Q# file.</span></span>
    <span data-ttu-id="b7692-200">Por ahora, no se devuelve nada, pero más adelante veremos un ejemplo de la asignación y el procesamiento de estos valores.</span><span class="sxs-lookup"><span data-stu-id="b7692-200">For now there is nothing returned, but later on we will see an example of assigning and processing these values.</span></span>
    <span data-ttu-id="b7692-201">Con los datos resultantes en nuestras manos y en todo el clásico, podemos hacer todo lo que nos gustaría.</span><span class="sxs-lookup"><span data-stu-id="b7692-201">With the resultant data in our hands and totally classical, we can do whatever we'd like with it.</span></span>

<span data-ttu-id="b7692-202">El `host.py` archivo completo debe ser el siguiente:</span><span class="sxs-lookup"><span data-stu-id="b7692-202">Your full `host.py` file should be this:</span></span>

```python
import qsharp
from NamespaceQFT import Perform3qubitQFT

Perform3qubitQFT.simulate()
```

<span data-ttu-id="b7692-203">Ejecute el archivo Python e impreso en la consola. debería ver los `Message` resultados y `DumpMachine` siguientes.</span><span class="sxs-lookup"><span data-stu-id="b7692-203">Run the Python file, and printed in your console you should see the `Message` and `DumpMachine` outputs below.</span></span> 


#### <a name="c"></a>[<span data-ttu-id="b7692-204">C#</span><span class="sxs-lookup"><span data-stu-id="b7692-204">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="b7692-205">Siguiendo las mismas instrucciones que en la [Guía de instalación](xref:microsoft.quantum.install.cs), cree un archivo de host de C# y cambie su nombre a `host.cs` .</span><span class="sxs-lookup"><span data-stu-id="b7692-205">Following the same instructions as in the [install guide](xref:microsoft.quantum.install.cs), create a C# host file, and rename it to `host.cs`.</span></span>

<span data-ttu-id="b7692-206">El host de C# tiene cuatro partes:</span><span class="sxs-lookup"><span data-stu-id="b7692-206">The C# host has four parts:</span></span>
1. <span data-ttu-id="b7692-207">Construya un simulador cuántico.</span><span class="sxs-lookup"><span data-stu-id="b7692-207">Construct a quantum simulator.</span></span>
    <span data-ttu-id="b7692-208">En el código siguiente, esta es la variable `qsim` .</span><span class="sxs-lookup"><span data-stu-id="b7692-208">In the code below, this is the variable `qsim`.</span></span>
2. <span data-ttu-id="b7692-209">Calcule los argumentos necesarios para el algoritmo cuántico.</span><span class="sxs-lookup"><span data-stu-id="b7692-209">Compute any arguments required for the quantum algorithm.</span></span>
    <span data-ttu-id="b7692-210">En este ejemplo no hay ninguno.</span><span class="sxs-lookup"><span data-stu-id="b7692-210">There are none in this example.</span></span>
3. <span data-ttu-id="b7692-211">Ejecute el algoritmo cuántico.</span><span class="sxs-lookup"><span data-stu-id="b7692-211">Run the quantum algorithm.</span></span> 
    <span data-ttu-id="b7692-212">Cada operación de Q# genera una clase C# con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="b7692-212">Each Q# operation generates a C# class with the same name.</span></span> 
    <span data-ttu-id="b7692-213">Esta clase tiene un método `Run` que ejecuta la operación **de forma asincrónica**.</span><span class="sxs-lookup"><span data-stu-id="b7692-213">This class has a `Run` method that **asynchronously** executes the operation.</span></span>
    <span data-ttu-id="b7692-214">La ejecución es asincrónica debido a que la ejecución en el hardware real será asincrónica.</span><span class="sxs-lookup"><span data-stu-id="b7692-214">The execution is asynchronous because execution on actual hardware will be asynchronous.</span></span> 
    <span data-ttu-id="b7692-215">Dado que el `Run` método es asincrónico, llamamos al `Wait()` método; Esto bloquea la ejecución hasta que la tarea se completa y devuelve el resultado sincrónicamente.</span><span class="sxs-lookup"><span data-stu-id="b7692-215">Because the `Run` method is asynchronous, we call the `Wait()` method; this blocks execution until the task completes and returns the result synchronously.</span></span> 
4. <span data-ttu-id="b7692-216">Procesa el resultado devuelto de la operación.</span><span class="sxs-lookup"><span data-stu-id="b7692-216">Process the returned result of the operation.</span></span>
    <span data-ttu-id="b7692-217">Por ahora, la operación no devuelve nada.</span><span class="sxs-lookup"><span data-stu-id="b7692-217">For now, the operation returns nothing.</span></span>


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
<span data-ttu-id="b7692-218">Ejecute la aplicación y la salida debe coincidir con la que aparece a continuación.</span><span class="sxs-lookup"><span data-stu-id="b7692-218">Run the application, and your output should match that below.</span></span>
<span data-ttu-id="b7692-219">El programa se cerrará después de presionar una tecla.</span><span class="sxs-lookup"><span data-stu-id="b7692-219">The program will exit after you press a key.</span></span>
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

<span data-ttu-id="b7692-220">Cuando se llama en el simulador de estado completo, `DumpMachine()` proporciona estas representaciones múltiples del WaveFunction del estado de Quantum.</span><span class="sxs-lookup"><span data-stu-id="b7692-220">When called on the full-state simulator, `DumpMachine()` provides these mutliple representations of the quantum state's wavefunction.</span></span> <span data-ttu-id="b7692-221">Los Estados posibles de una $n sistema $-qubit pueden estar representados por los Estados de base de $2 ^ n $ computacional, cada uno con un coeficiente complejo correspondiente (simplemente una amplitud y una fase).</span><span class="sxs-lookup"><span data-stu-id="b7692-221">The possible states of an $n$-qubit system can be represented by $2^n$ computational basis states, each with a corresponding complex coefficient (simply an amplitude and a phase).</span></span>
<span data-ttu-id="b7692-222">Los Estados de base de cálculo corresponden a todas las posibles cadenas binarias de longitud $n $---, es decir, todas las combinaciones posibles de los Estados qubit $ \ket {0} $ y $ \ket {1} $, donde cada dígito binario corresponde a una qubit individual.</span><span class="sxs-lookup"><span data-stu-id="b7692-222">The computational basis states correspond to all the possible binary strings of length $n$---that is, all the possible combinations of qubit states $\ket{0}$ and $\ket{1}$, where each binary digit corresponds to an individual qubit.</span></span>

<span data-ttu-id="b7692-223">La primera fila proporciona un comentario con los identificadores del qubits correspondiente en su orden significativo.</span><span class="sxs-lookup"><span data-stu-id="b7692-223">The first row provides a comment with the IDs of the corresponding qubits in their significant order.</span></span>
<span data-ttu-id="b7692-224">Qubit `2` es el "más importante" simplemente significa que en la representación binaria del vector de estado de base $ \ket{i} $, el estado de qubit `2` corresponde al dígito situado más a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="b7692-224">Qubit `2` being the "most significant" simply means that in the binary representation of basis state vector $\ket{i}$, the state of qubit `2` corresponds to the left-most digit.</span></span> <span data-ttu-id="b7692-225">Por ejemplo, $ \ket {6} = \ket {110} $ incluye qubits `2` y `1` ambos en $ \ket {1} $ y qubit `0` en $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="b7692-225">For example, $\ket{6} = \ket{110}$ comprises qubits `2` and `1` both in $\ket{1}$ and qubit `0` in $\ket{0}$.</span></span>


<span data-ttu-id="b7692-226">El resto de las filas describen la amplitud de probabilidad de medir el vector de estado de base $ \ket{i} $ en formatos cartesianos y polares.</span><span class="sxs-lookup"><span data-stu-id="b7692-226">The rest of the rows describe the probability amplitude of measuring the basis state vector $\ket{i}$ in both Cartesian and polar formats.</span></span>
<span data-ttu-id="b7692-227">En detalle para la primera fila de nuestro estado de entrada $ \ket {000} $:</span><span class="sxs-lookup"><span data-stu-id="b7692-227">In detail for the first row of our input state $\ket{000}$:</span></span>
* <span data-ttu-id="b7692-228">**`|0>:`** esta fila corresponde al `0` Estado de base de cálculo (dado que la asignación posterior de estado inicial era $ \ket {000} $, esperamos que este sea el único estado con amplitud de probabilidad en este momento).</span><span class="sxs-lookup"><span data-stu-id="b7692-228">**`|0>:`** this row corresponds to the `0` computational basis state (given that our initial state post-allocation was $\ket{000}$, we would expect this to be the only state with probability amplitude at this point).</span></span>
* <span data-ttu-id="b7692-229">**`1.000000 +  0.000000 i`**: la amplitud de probabilidad en formato cartesiano.</span><span class="sxs-lookup"><span data-stu-id="b7692-229">**`1.000000 +  0.000000 i`**: the probability amplitude in Cartesian format.</span></span>
* <span data-ttu-id="b7692-230">**` == `**: el `equal` signo separa ambas representaciones equivalentes.</span><span class="sxs-lookup"><span data-stu-id="b7692-230">**` == `**: the `equal` sign separates both equivalent representations.</span></span>
* <span data-ttu-id="b7692-231">**`********************`**: Una representación gráfica de la magnitud, el número de `*` es proporcional a la probabilidad de medir este vector de estado.</span><span class="sxs-lookup"><span data-stu-id="b7692-231">**`********************`**: A graphical representation of the magnitude, the number of `*` is proportionate to the probability of measuring this state vector.</span></span> 
* <span data-ttu-id="b7692-232">**`[ 1.000000 ]`**: el valor numérico de la magnitud</span><span class="sxs-lookup"><span data-stu-id="b7692-232">**`[ 1.000000 ]`**: the numeric value of the magnitude</span></span>
* <span data-ttu-id="b7692-233">**`    ---`**: Representación gráfica de la fase de amplitud.</span><span class="sxs-lookup"><span data-stu-id="b7692-233">**`    ---`**: A graphical representation of the amplitude's phase.</span></span>
* <span data-ttu-id="b7692-234">**`[ 0.0000 rad ]`**: valor numérico de la fase (en radianes).</span><span class="sxs-lookup"><span data-stu-id="b7692-234">**`[ 0.0000 rad ]`**: the numeric value of the phase (in radians).</span></span>

<span data-ttu-id="b7692-235">Tanto la magnitud como la fase se muestran con una representación gráfica.</span><span class="sxs-lookup"><span data-stu-id="b7692-235">Both the magnitude and the phase are displayed with a graphical representation.</span></span> <span data-ttu-id="b7692-236">La representación de la magnitud es sencilla: muestra una barra de `*` y cuanto mayor sea la probabilidad, mayor será la barra.</span><span class="sxs-lookup"><span data-stu-id="b7692-236">The magnitude representation is straightforward: it shows a bar of `*`, and the higher the probability, the larger the bar will be.</span></span> <span data-ttu-id="b7692-237">Para la fase, consulte [pruebas y depuración: funciones de volcado](xref:microsoft.quantum.guide.testingdebugging#dump-functions) de memoria para las posibles representaciones de símbolos basadas en intervalos de ángulo.</span><span class="sxs-lookup"><span data-stu-id="b7692-237">For the phase, see [Testing and debugging: dump functions](xref:microsoft.quantum.guide.testingdebugging#dump-functions) for the possible symbol representations based on angle ranges.</span></span>


<span data-ttu-id="b7692-238">Por lo tanto, la salida impresa ilustra que nuestras puertas programadas transformaron nuestro estado desde</span><span class="sxs-lookup"><span data-stu-id="b7692-238">So, the printed output is illustrating that our programmed gates transformed our state from</span></span>

<span data-ttu-id="b7692-239">$ $ \ket{\psi} \_ {Initial} = \ket {000} $ $</span><span class="sxs-lookup"><span data-stu-id="b7692-239">$$ \ket{\psi}\_{initial} = \ket{000} $$</span></span>

<span data-ttu-id="b7692-240">to</span><span class="sxs-lookup"><span data-stu-id="b7692-240">to</span></span> 

<span data-ttu-id="b7692-241">$ $ \begin{align} \ket{\psi} \_ {final} &= \frac {1} {\sqrt {8} } \left (\ket {000} + \ket {001} + \ket {010} + \ket {011} + \ket {100} + \ket {101} + \ket {110} + \ket {111} \right) \\ \\ &= \frac {1} {\sqrt{2 ^ n}} \sum \_ {j = 0} ^ {2 ^ n-1} \ket{j}, \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="b7692-241">$$ \begin{align} \ket{\psi}\_{final} &= \frac{1}{\sqrt{8}} \left( \ket{000} + \ket{001} + \ket{010} + \ket{011} + \ket{100} + \ket{101} + \ket{110} + \ket{111}  \right) \\\\ &= \frac{1}{\sqrt{2^n}}\sum\_{j=0}^{2^n-1} \ket{j}, \end{align} $$</span></span>

<span data-ttu-id="b7692-242">que es precisamente el comportamiento de la transformación de Fourier 3-qubit.</span><span class="sxs-lookup"><span data-stu-id="b7692-242">which is precisely the behavior of the 3-qubit Fourier transform.</span></span> 

<span data-ttu-id="b7692-243">Si tiene curiosidad sobre cómo se ven afectados otros Estados de entrada, le recomendamos que experimente con la aplicación de las operaciones de qubit antes de la transformación.</span><span class="sxs-lookup"><span data-stu-id="b7692-243">If you are curious about how other input states are affected, we encourage you to play around with applying qubit operations before the transform.</span></span>

## <a name="adding-measurements"></a><span data-ttu-id="b7692-244">Agregar medidas</span><span class="sxs-lookup"><span data-stu-id="b7692-244">Adding measurements</span></span>

<span data-ttu-id="b7692-245">Desafortunadamente, una piedra angular de la mecánica de Quantum nos indica que un sistema Quantum real no puede tener una función de este tipo `DumpMachine` .</span><span class="sxs-lookup"><span data-stu-id="b7692-245">Unfortunately, a cornerstone of quantum mechanics tells us that a real quantum system cannot have such a `DumpMachine` function.</span></span> <span data-ttu-id="b7692-246">En su lugar, nos obligamos a extraer información a través de medidas, que en general no solo proporcionan el estado completo del Quantum, sino que también pueden modificar drásticamente el propio sistema.</span><span class="sxs-lookup"><span data-stu-id="b7692-246">Instead, we're forced to extract information through measurements, which in general not only fail to provide us the full quantum state, but can also drastically alter the system itself.</span></span>
<span data-ttu-id="b7692-247">Hay muchos tipos de mediciones Quantum, pero nos centraremos en las mediciones más básicas: las medidas proyectadas en un único qubits.</span><span class="sxs-lookup"><span data-stu-id="b7692-247">There are many sorts of quantum measurements, but we will focus on the most basic: projective measurements on single qubits.</span></span>
<span data-ttu-id="b7692-248">A medida que se mide de forma determinada (por ejemplo, la base de cálculo $ \{ \ket {0} , \ket {1} \} $), el estado de qubit se proyecta en el estado de base medido---, por lo tanto, se destruye cualquier superposición entre los dos.</span><span class="sxs-lookup"><span data-stu-id="b7692-248">Upon measurement in a given basis (e.g. the computational basis $ \{ \ket{0}, \ket{1} \} $), the qubit state is projected onto whichever basis state was measured---hence destroying any superposition between the two.</span></span>

<span data-ttu-id="b7692-249">Para implementar las medidas en un programa de preguntas y respuestas, usamos la `M` operación (from `Microsoft.Quantum.Intrinsic` ), que devuelve un `Result` tipo.</span><span class="sxs-lookup"><span data-stu-id="b7692-249">To implement measurements within a Q# program, we use the `M` operation (from `Microsoft.Quantum.Intrinsic`), which returns a `Result` type.</span></span>

<span data-ttu-id="b7692-250">En primer lugar, se modifica la `Perform3QubitQFT` operación para devolver una matriz de resultados de medida, `Result[]` , en lugar de `Unit` .</span><span class="sxs-lookup"><span data-stu-id="b7692-250">First, we modify our `Perform3QubitQFT` operation to return an array of measurement results, `Result[]`, instead of `Unit`.</span></span>

```qsharp
    operation Perform3QubitQFT() : Result[] {
```

#### <a name="define-and-initialize-result-array"></a><span data-ttu-id="b7692-251">Definición e inicialización de una `Result[]` matriz</span><span class="sxs-lookup"><span data-stu-id="b7692-251">Define and initialize `Result[]` array</span></span>

<span data-ttu-id="b7692-252">Antes de asignar qubits (es decir, antes de la `using` instrucción), se declara y se enlaza esta matriz de longitud 3 (una `Result` para cada qubit):</span><span class="sxs-lookup"><span data-stu-id="b7692-252">Before even allocating qubits (i.e. before the `using` statement), we declare and bind this length-3 array (one `Result` for each qubit):</span></span> 

```qsharp
        mutable resultArray = new Result[3];
```

<span data-ttu-id="b7692-253">La `mutable` palabra clave preorientada `resultArray` permite reenlazar la variable más adelante en el código---por ejemplo, al agregar los resultados de la medida.</span><span class="sxs-lookup"><span data-stu-id="b7692-253">The `mutable` keyword prefacing `resultArray` allows the variable to be rebound later in the code---for example, when adding our measurement results.</span></span>

#### <a name="perform-measurements-in-a-for-loop-and-add-results-to-array"></a><span data-ttu-id="b7692-254">Realizar mediciones en un `for` bucle y agregar resultados a la matriz</span><span class="sxs-lookup"><span data-stu-id="b7692-254">Perform measurements in a `for` loop and add results to array</span></span>

<span data-ttu-id="b7692-255">Después de las operaciones de transformación de Fourier dentro del `using` bloque, inserte el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="b7692-255">After the Fourier transform operations inside the `using` block, insert the following code:</span></span>

```qsharp
            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }
```
<span data-ttu-id="b7692-256">La [`IndexRange`](xref:microsoft.quantum.arrays.indexrange) función a la que se llama en una matriz (por ejemplo, nuestra matriz de qubits `qs` ) devuelve un intervalo sobre los índices de la matriz.</span><span class="sxs-lookup"><span data-stu-id="b7692-256">The [`IndexRange`](xref:microsoft.quantum.arrays.indexrange) function called on an array (e.g. our array of qubits, `qs`) returns a range over the indices of the array.</span></span> <span data-ttu-id="b7692-257">Aquí se usa en nuestro `for` bucle para medir secuencialmente cada qubit mediante la `M(qs[i])` instrucción.</span><span class="sxs-lookup"><span data-stu-id="b7692-257">Here, we use it in our `for` loop to sequentially measure each qubit using the `M(qs[i])` statement.</span></span>
<span data-ttu-id="b7692-258">Cada `Result` tipo medido ( `Zero` o `One` ) se agrega a continuación a la posición de índice correspondiente en `resultArray` con una instrucción Update-and-resign.</span><span class="sxs-lookup"><span data-stu-id="b7692-258">Each measured `Result` type (either `Zero` or `One`) is then added to the corresponding index position in `resultArray` with an update-and-reassign statement.</span></span>

> [!NOTE]
> <span data-ttu-id="b7692-259">La sintaxis de esta instrucción es exclusiva de Q #, pero corresponde a la reasignación de variables similar que se ha `resultArray[i] <- M(qs[i])` detectado en otros lenguajes, como F # y R.</span><span class="sxs-lookup"><span data-stu-id="b7692-259">The syntax of this statement is unique to Q#, but corresponds to the similar variable reassignment `resultArray[i] <- M(qs[i])` seen in other languages such as F# and R.</span></span>

<span data-ttu-id="b7692-260">La palabra clave `set` siempre se usa para reasignar variables enlazadas mediante `mutable` .</span><span class="sxs-lookup"><span data-stu-id="b7692-260">The keyword `set` is always used to reassign variables bound using `mutable`.</span></span>

#### <a name="return-resultarray"></a><span data-ttu-id="b7692-261">Devolver`resultArray`</span><span class="sxs-lookup"><span data-stu-id="b7692-261">Return `resultArray`</span></span>

<span data-ttu-id="b7692-262">Con los tres qubits medidos y los resultados agregados a `resultArray` , es seguro restablecer y desasignar el qubits como antes.</span><span class="sxs-lookup"><span data-stu-id="b7692-262">With all three qubits measured and the results added to `resultArray`, we are safe to reset and deallocate the qubits as before.</span></span>
<span data-ttu-id="b7692-263">Después del `using` cierre del bloque, inserte</span><span class="sxs-lookup"><span data-stu-id="b7692-263">After the `using` block's close, insert</span></span>

```qsharp
        return resultArray;
```
<span data-ttu-id="b7692-264">para devolver el resultado de la operación en última instancia.</span><span class="sxs-lookup"><span data-stu-id="b7692-264">to ultimately return the output of our operation.</span></span> 

### <a name="understanding-the-effects-of-measurement"></a><span data-ttu-id="b7692-265">Descripción de los efectos de la medición</span><span class="sxs-lookup"><span data-stu-id="b7692-265">Understanding the effects of measurement</span></span>

<span data-ttu-id="b7692-266">Vamos a cambiar la ubicación de las `DumpMachine` funciones para generar el estado antes y después de las mediciones.</span><span class="sxs-lookup"><span data-stu-id="b7692-266">Let's change the placement of our `DumpMachine` functions to output the state before and after the measurements.</span></span>
<span data-ttu-id="b7692-267">El código de operación final debería ser similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="b7692-267">The final operation code should look like:</span></span> 

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

<span data-ttu-id="b7692-268">Si está trabajando desde la línea de comandos, la matriz devuelta simplemente se imprimirá directamente en la consola al final de la ejecución.</span><span class="sxs-lookup"><span data-stu-id="b7692-268">If you are working from the command line, the returned array will simply be printed directly to the console at the end of the execution.</span></span>
<span data-ttu-id="b7692-269">De lo contrario, actualice el programa host para procesar la matriz devuelta.</span><span class="sxs-lookup"><span data-stu-id="b7692-269">Otherwise, update your host program to process the returned array.</span></span>

#### <a name="command-line"></a>[<span data-ttu-id="b7692-270">Línea de comandos</span><span class="sxs-lookup"><span data-stu-id="b7692-270">Command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="b7692-271">Para comprender mejor la matriz devuelta que se va a imprimir en la consola de, podemos agregar otra `Message` en el archivo Q # justo antes de la `return` instrucción:</span><span class="sxs-lookup"><span data-stu-id="b7692-271">To have more understanding of the returned array which will be printed in the console, we can add another `Message` in the Q# file just before the `return` statement:</span></span>

```qsharp
        Message("Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
        return resultArray;
```

<span data-ttu-id="b7692-272">Ejecute el proyecto y el resultado debe ser similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="b7692-272">Run the project, and your output should look similar to the following:</span></span>

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

#### <a name="python"></a>[<span data-ttu-id="b7692-273">Python</span><span class="sxs-lookup"><span data-stu-id="b7692-273">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="b7692-274">Actualice el programa de Python a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b7692-274">Update your Python program to the following:</span></span>

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

<span data-ttu-id="b7692-275">Ejecute el archivo y el resultado debe ser similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="b7692-275">Run the file, and your output should look similar to the following:</span></span>

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

#### <a name="c"></a>[<span data-ttu-id="b7692-276">C#</span><span class="sxs-lookup"><span data-stu-id="b7692-276">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="b7692-277">Ahora que la operación devuelve un resultado, reemplace la llamada al método `Wait()` con la captura de la `Result` propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7692-277">Now that our operation is returning a result, replace the method call `Wait()` with fetching the `Result` property.</span></span> <span data-ttu-id="b7692-278">Esto sigue logrando la misma Synchronicity descrita anteriormente y podemos enlazar directamente este valor a la variable `measurementResult` .</span><span class="sxs-lookup"><span data-stu-id="b7692-278">This still accomplishes the same synchronicity discussed earlier, and we can directly bind this value to the variable `measurementResult`.</span></span>

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

<span data-ttu-id="b7692-279">Ejecute el proyecto y el resultado debe ser similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="b7692-279">Run the project, and your output should look similar to the following:</span></span>

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

<span data-ttu-id="b7692-280">Esta salida muestra algunos aspectos diferentes:</span><span class="sxs-lookup"><span data-stu-id="b7692-280">This output illustrates a few different things:</span></span>
1. <span data-ttu-id="b7692-281">Al comparar el resultado devuelto con la medición previa `DumpMachine` , _no_ se ilustra claramente la superposición post-QFT en función de los Estados de base.</span><span class="sxs-lookup"><span data-stu-id="b7692-281">Comparing the returned result to the pre-measurement `DumpMachine`, it clearly does _not_ illustrate the post-QFT superposition over basis states.</span></span>
    <span data-ttu-id="b7692-282">Una medida solo devuelve un estado de base único, con una probabilidad determinada por la amplitud de ese estado en el WaveFunction del sistema.</span><span class="sxs-lookup"><span data-stu-id="b7692-282">A measurement only returns a single basis state, with a probability determined by the amplitude of that state in the system's wavefunction.</span></span>
2. <span data-ttu-id="b7692-283">A partir de la medición posterior `DumpMachine` , vemos que la medida _cambia_ el estado en sí, lo que lo proyecta desde la superposición inicial sobre los Estados de base hasta el estado de base única que corresponde al valor medido.</span><span class="sxs-lookup"><span data-stu-id="b7692-283">From the post-measurement `DumpMachine`, we see that measurement _changes_ the state itself, projecting it from the initial superposition over basis states to the single basis state that corresponds to the measured value.</span></span>

<span data-ttu-id="b7692-284">Si fuera a repetir esta operación muchas veces, veremos que las estadísticas de resultados comenzarán a ilustrar la superposición igualmente ponderada del estado posterior a la QFT que da lugar a un resultado aleatorio en cada captura.</span><span class="sxs-lookup"><span data-stu-id="b7692-284">If we were to repeat this operation many times, we would see the result statistics begin to illustrate the equally weighted superposition of the post-QFT state that gives rise to a random result on each shot.</span></span>
<span data-ttu-id="b7692-285">_Sin embargo_, además de ser ineficaces y seguir siendo imperfectos, esto solo reproduciría las amplitudes relativas de los Estados de base, no las fases relativas entre ellas.</span><span class="sxs-lookup"><span data-stu-id="b7692-285">_However_, besides being inefficient and still imperfect, this would nevertheless only reproduce the relative amplitudes of the basis states, not the relative phases between them.</span></span>
<span data-ttu-id="b7692-286">Esto último no es un problema en este ejemplo, pero veremos que las fases relativas aparecen si se proporciona una entrada más compleja a QFT de $ \ket {000} $.</span><span class="sxs-lookup"><span data-stu-id="b7692-286">The latter is not an issue in this example, but we would see relative phases appear if given a more complex input to the QFT than $\ket{000}$.</span></span>

#### <a name="partial-measurements"></a><span data-ttu-id="b7692-287">Medidas parciales</span><span class="sxs-lookup"><span data-stu-id="b7692-287">Partial measurements</span></span> 
<span data-ttu-id="b7692-288">Para explorar cómo la medición de solo algunos qubits del registro puede afectar al estado del sistema, intente agregar lo siguiente dentro del `for` bucle, después de la línea de medida:</span><span class="sxs-lookup"><span data-stu-id="b7692-288">To explore how measuring only some qubits of the register can affect the system's state, try adding the following inside the `for` loop, after the measurement line:</span></span>
```qsharp
                let iString = IntAsString(i);
                Message("After measurement of qubit " + iString + ":");
                DumpMachine();
```

<span data-ttu-id="b7692-289">Tenga en cuenta que para tener acceso a la `IntAsString` función tendrá que agregar</span><span class="sxs-lookup"><span data-stu-id="b7692-289">Note that to access the `IntAsString` function you will have to add</span></span> 
```qsharp
    open Microsoft.Quantum.Convert;
```
<span data-ttu-id="b7692-290">con el resto de las instrucciones de espacio de nombres `open` .</span><span class="sxs-lookup"><span data-stu-id="b7692-290">with the rest of the namespace `open` statements.</span></span>

<span data-ttu-id="b7692-291">En la salida resultante, verá la proyección gradual en subespacios a medida que se mide cada qubit.</span><span class="sxs-lookup"><span data-stu-id="b7692-291">In the resulting output, you will see the gradual projection into subspaces as each qubit is measured.</span></span>


## <a name="use-the-q-libraries"></a><span data-ttu-id="b7692-292">Uso de las bibliotecas de preguntas y respuestas</span><span class="sxs-lookup"><span data-stu-id="b7692-292">Use the Q# libraries</span></span>
<span data-ttu-id="b7692-293">Como se mencionó en la introducción, gran parte de la potencia de Q # tiene en el hecho de que le permite abstraer las preocupaciones de trabajar con qubits individuales.</span><span class="sxs-lookup"><span data-stu-id="b7692-293">As we mentioned in the introduction, much of Q#'s power rests in the fact that it allows you to abstract-away the worries of dealing with individual qubits.</span></span>
<span data-ttu-id="b7692-294">En realidad, si desea desarrollar programas Quantum de gran tamaño aplicables, preocuparse de si una `H` operación va antes o después de que una rotación determinada solo le ralentice.</span><span class="sxs-lookup"><span data-stu-id="b7692-294">Indeed, if you want to develop full-scale, applicable quantum programs, worrying about whether an `H` operation goes before or after a particular rotation would only slow you down.</span></span> 

<span data-ttu-id="b7692-295">Las bibliotecas de preguntas y respuestas contienen la operación [QFT](xref:microsoft.quantum.canon.qft) , que se puede realizar simplemente y aplicar para cualquier número de qubits.</span><span class="sxs-lookup"><span data-stu-id="b7692-295">The Q# libraries contain the [QFT](xref:microsoft.quantum.canon.qft) operation, which you can simply take and apply for any number of qubits.</span></span>
<span data-ttu-id="b7692-296">Para probarlo, defina una nueva operación en el archivo Q # que tenga el mismo contenido de `Perform3QubitQFT` , pero con todo lo que haya entre el primero `H` y el `SWAP` reemplazado por dos líneas sencillas:</span><span class="sxs-lookup"><span data-stu-id="b7692-296">To give it a try, define a new operation in your Q# file which has the same contents of `Perform3QubitQFT`, but with everything from the first `H` to the `SWAP` replaced by two easy lines:</span></span>
```qsharp
            let register = BigEndian(qs);    //from Microsoft.Quantum.Arithmetic
            QFT(register);                   //from Microsoft.Quantum.Canon
```
<span data-ttu-id="b7692-297">La primera línea simplemente crea una [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) expresión de la matriz asignada de qubits, `qs` , que es lo que la operación [QFT](xref:microsoft.quantum.canon.qft) toma como argumento.</span><span class="sxs-lookup"><span data-stu-id="b7692-297">The first line simply creates a [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) expression of the allocated array of qubits, `qs`, which is what the [QFT](xref:microsoft.quantum.canon.qft) operation takes as an argument.</span></span>
<span data-ttu-id="b7692-298">Esto corresponde al orden de índice de qubits en el registro.</span><span class="sxs-lookup"><span data-stu-id="b7692-298">This corresponds to index ordering of the qubits in the register.</span></span>

<span data-ttu-id="b7692-299">Para tener acceso a estas operaciones, agregue `open` instrucciones para sus respectivos espacios de nombres al principio del archivo Q #:</span><span class="sxs-lookup"><span data-stu-id="b7692-299">To have access to these operations, add `open` statements for their respective namespaces at the beginning of the Q# file:</span></span>
```qsharp
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Arithmetic;
```

<span data-ttu-id="b7692-300">Ahora, ajuste el programa host para que llame al nombre de la nueva operación (por ejemplo `PerformIntrinsicQFT` ,) y asígnele un giro.</span><span class="sxs-lookup"><span data-stu-id="b7692-300">Now, adjust your host program to call the name of your new operation (e.g. `PerformIntrinsicQFT`), and give it a whirl.</span></span>

<span data-ttu-id="b7692-301">Para ver las ventajas reales del uso de las operaciones de la biblioteca de preguntas y respuestas, cambie el número de qubits a un valor distinto de `3` :</span><span class="sxs-lookup"><span data-stu-id="b7692-301">To see the real benefit of using the Q# library operations, change the number of qubits to something other than `3`:</span></span>
```qsharp
        mutable resultArray = new Result[4]; 

        using (qs = Qubit[4]) {
            //...
        }
```
<span data-ttu-id="b7692-302">Por tanto, puede aplicar el QFT adecuado para cualquier número determinado de qubits, sin tener que preocuparse por el desorden de nuevas `H` operaciones y giros en cada qubit.</span><span class="sxs-lookup"><span data-stu-id="b7692-302">You can thus apply the proper QFT for any given number of qubits, without having to worry about the mess of new `H` operations and rotations on each qubit.</span></span>

<span data-ttu-id="b7692-303">Tenga en cuenta que el simulador de Quantum tarda más tiempo en ejecutarse a medida que aumenta el número de qubits---exactamente por qué le parecemos el hardware Quantum real.</span><span class="sxs-lookup"><span data-stu-id="b7692-303">Note that the quantum simulator takes exponentially more time to run as you increase the number of qubits---precisely why we look forward to real quantum hardware!</span></span>













