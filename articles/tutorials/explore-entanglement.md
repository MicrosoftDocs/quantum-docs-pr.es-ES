---
title: 'Explore el incumplimiento con :::no-loc(Q#):::'
description: 'Aprenda a escribir un programa Quantum en :::no-loc(Q#)::: . Desarrolle una aplicación de estado Bell mediante el kit de desarrollo de Microsoft Quantum (QDK)'
author: geduardo
ms.author: v-edsanc
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 7a1a49e18ac9330ca6e3cc89b3e58c96eccb91db
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691674"
---
# <a name="tutorial-explore-entanglement-with-q"></a><span data-ttu-id="8ebda-104">Tutorial: Exploración del entrelazamiento con Q\#</span><span class="sxs-lookup"><span data-stu-id="8ebda-104">Tutorial: Explore entanglement with Q\#</span></span>

<span data-ttu-id="8ebda-105">En este tutorial, se muestra cómo escribir un :::no-loc(Q#)::: programa que manipula y mide qubits y muestra los efectos de la superposición y el inenredo.</span><span class="sxs-lookup"><span data-stu-id="8ebda-105">In this tutorial, we show you how to write a :::no-loc(Q#)::: program that manipulates and measures qubits and demonstrates the effects of superposition and entanglement.</span></span>

<span data-ttu-id="8ebda-106">Escribirá una aplicación llamada Bell para demostrar el entrelazamiento cuántico.</span><span class="sxs-lookup"><span data-stu-id="8ebda-106">You will write an application called Bell to demonstrate quantum entanglement.</span></span>
<span data-ttu-id="8ebda-107">El nombre Bell hace referencia a los estados de Bell, que son estados cuánticos específicos de dos cúbits que se usan para representar los ejemplos más sencillos de la superposición y el entrelazamiento cuántico.</span><span class="sxs-lookup"><span data-stu-id="8ebda-107">The name Bell is in reference to Bell states, which are specific quantum states of two qubits that are used to represent the simplest examples of superposition and quantum entanglement.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="8ebda-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8ebda-108">Pre-requisites</span></span>

<span data-ttu-id="8ebda-109">Si está listo para empezar a codificar, siga estos pasos antes de continuar:</span><span class="sxs-lookup"><span data-stu-id="8ebda-109">If you are ready to start coding, follow these steps before proceeding:</span></span> 

* <span data-ttu-id="8ebda-110">[Instale](xref:microsoft.quantum.install) el kit de desarrollo de Quantum usando su entorno de desarrollo y lenguaje preferido.</span><span class="sxs-lookup"><span data-stu-id="8ebda-110">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your  preferred language and development environment.</span></span>
* <span data-ttu-id="8ebda-111">Si ya tiene instalado el QDK, asegúrese de que tiene [actualizada](xref:microsoft.quantum.update) la última versión</span><span class="sxs-lookup"><span data-stu-id="8ebda-111">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>

<span data-ttu-id="8ebda-112">También puede seguir con la narrativa sin instalar QDK, revisando la información general del :::no-loc(Q#)::: lenguaje de programación y los primeros conceptos de la informática Quantum.</span><span class="sxs-lookup"><span data-stu-id="8ebda-112">You can also follow along with the narrative without installing the QDK, reviewing  the overviews of the :::no-loc(Q#)::: programming language and the first concepts of quantum computing.</span></span>

## <a name="in-this-tutorial-youll-learn-how-to"></a><span data-ttu-id="8ebda-113">En este tutorial, aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="8ebda-113">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="8ebda-114">Operaciones de creación y combinación en Q\#</span><span class="sxs-lookup"><span data-stu-id="8ebda-114">Create and combine operations in Q\#</span></span>
> * <span data-ttu-id="8ebda-115">Crear operaciones para colocar qubits en la superposición, entangle y medirlos.</span><span class="sxs-lookup"><span data-stu-id="8ebda-115">Create operations to put qubits in superposition, entangle and measure them.</span></span>
> * <span data-ttu-id="8ebda-116">Muestre el incumplimiento de Quantum con un programa que se :::no-loc(Q#)::: ejecuta en un simulador.</span><span class="sxs-lookup"><span data-stu-id="8ebda-116">Demonstrate quantum entanglement with a :::no-loc(Q#)::: program run in a simulator.</span></span> 

## <a name="demonstrating-qubit-behavior-with-the-qdk"></a><span data-ttu-id="8ebda-117">Demostrar el comportamiento de qubit con QDK</span><span class="sxs-lookup"><span data-stu-id="8ebda-117">Demonstrating qubit behavior with the QDK</span></span>

<span data-ttu-id="8ebda-118">Mientras que los bits clásicos contienen un único valor binario, como 0 o 1, el estado de un [cúbit](xref:microsoft.quantum.glossary#qubit) puede ser una **superposición** de 0 y 1.</span><span class="sxs-lookup"><span data-stu-id="8ebda-118">Where classical bits hold a single binary value such as a 0 or 1, the state of a [qubit](xref:microsoft.quantum.glossary#qubit) can be in a **superposition** of 0 and 1.</span></span>  <span data-ttu-id="8ebda-119">Conceptualmente, el estado de un qubit se puede considerar como una dirección en un espacio abstracto (también conocido como vector).</span><span class="sxs-lookup"><span data-stu-id="8ebda-119">Conceptually, the state of a qubit can be thought of as a direction in an abstract space (also known as a vector).</span></span>  <span data-ttu-id="8ebda-120">Un estado de qubit puede estar en cualquiera de las direcciones posibles.</span><span class="sxs-lookup"><span data-stu-id="8ebda-120">A qubit state can be in any of the possible directions.</span></span> <span data-ttu-id="8ebda-121">Los dos **estados clásicos** son las dos direcciones, que representan el 100 % de probabilidad de medir 0 y el 100 % de probabilidad de medir 1.</span><span class="sxs-lookup"><span data-stu-id="8ebda-121">The two **classical states** are the two directions; representing 100% chance of measuring 0 and 100% chance of measuring 1.</span></span>

<span data-ttu-id="8ebda-122">La acción de medir genera un resultado binario y cambia el estado del cúbit.</span><span class="sxs-lookup"><span data-stu-id="8ebda-122">The act of measurement produces a binary result and changes a qubit state.</span></span>
<span data-ttu-id="8ebda-123">La medida produce un valor binario, ya sea 0 o 1.</span><span class="sxs-lookup"><span data-stu-id="8ebda-123">Measurement  produces a binary value, either 0 or 1.</span></span>  <span data-ttu-id="8ebda-124">El cúbit pasa de estar en superposición (cualquier dirección) a estar en uno de los estados clásicos.</span><span class="sxs-lookup"><span data-stu-id="8ebda-124">The qubit goes from being in superposition (any direction) to one of the classical states.</span></span>  <span data-ttu-id="8ebda-125">Después, si se repite la medida sin que intervenga ninguna operación, se produce el mismo resultado binario.</span><span class="sxs-lookup"><span data-stu-id="8ebda-125">Thereafter, repeating the same measurement without any intervening operations produces the same binary result.</span></span>  

<span data-ttu-id="8ebda-126">Varios cúbits pueden estar [**entrelazados**](xref:microsoft.quantum.glossary#entanglement).</span><span class="sxs-lookup"><span data-stu-id="8ebda-126">Multiple qubits can be [**entangled**](xref:microsoft.quantum.glossary#entanglement).</span></span>  <span data-ttu-id="8ebda-127">Cuando se toma una medida de un cúbit entrelazado, se actualizan también los conocimientos del estado de los otros.</span><span class="sxs-lookup"><span data-stu-id="8ebda-127">When we make a measurement of one entangled qubit, our knowledge of the state of the other(s) is updated as well.</span></span>

<span data-ttu-id="8ebda-128">Ahora, estamos listos para demostrar cómo :::no-loc(Q#)::: expresa este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="8ebda-128">Now, we're ready to demonstrate how :::no-loc(Q#)::: expresses this behavior.</span></span>  <span data-ttu-id="8ebda-129">Comience con el programa más sencillo posible y compílelo para demostrar la superposición cuántica y el entrelazamiento cuántico.</span><span class="sxs-lookup"><span data-stu-id="8ebda-129">You start with the simplest program possible and build it up to demonstrate quantum superposition and quantum entanglement.</span></span>

## <a name="creating-a-no-locq-project"></a><span data-ttu-id="8ebda-130">Crear un :::no-loc(Q#)::: proyecto</span><span class="sxs-lookup"><span data-stu-id="8ebda-130">Creating a :::no-loc(Q#)::: project</span></span>

<span data-ttu-id="8ebda-131">Lo primero que tenemos que hacer es crear un nuevo :::no-loc(Q#)::: proyecto.</span><span class="sxs-lookup"><span data-stu-id="8ebda-131">The first thing we have to do is to create a new :::no-loc(Q#)::: project.</span></span> <span data-ttu-id="8ebda-132">En este tutorial vamos a usar el entorno basado en [ :::no-loc(Q#)::: aplicaciones con vs Code](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="8ebda-132">In this tutorial we are going to use the environment based on [:::no-loc(Q#)::: applications with VS Code](xref:microsoft.quantum.install.standalone).</span></span>

<span data-ttu-id="8ebda-133">Para crear un nuevo proyecto, en VS Code:</span><span class="sxs-lookup"><span data-stu-id="8ebda-133">To create a new project, in VS Code:</span></span> 

1. <span data-ttu-id="8ebda-134">Haga clic en **Ver** -> **Paleta de comandos** y seleccione **:::no-loc(Q#):::: Crear nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="8ebda-134">Click **View** -> **Command Palette** and select **:::no-loc(Q#):::: Create New Project** .</span></span>
2. <span data-ttu-id="8ebda-135">Haga clic en **Aplicación de consola independiente** .</span><span class="sxs-lookup"><span data-stu-id="8ebda-135">Click **Standalone console application** .</span></span>
3. <span data-ttu-id="8ebda-136">Vaya a la ubicación para guardar el proyecto y haga clic en **Crear proyecto** .</span><span class="sxs-lookup"><span data-stu-id="8ebda-136">Navigate to the location to save the project and click **Create Project** .</span></span>
4. <span data-ttu-id="8ebda-137">Cuando el proyecto se haya creado correctamente, haga clic en **Abrir nuevo proyecto...** abajo a la derecha.</span><span class="sxs-lookup"><span data-stu-id="8ebda-137">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="8ebda-138">En este caso, se ha llamado al proyecto `Bell` .</span><span class="sxs-lookup"><span data-stu-id="8ebda-138">In this case we called the project `Bell`.</span></span> <span data-ttu-id="8ebda-139">Esto genera dos archivos: `Bell.csproj` , el archivo de proyecto y `Program.qs` , una plantilla de una :::no-loc(Q#)::: aplicación que se va a usar para escribir la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8ebda-139">This generates two files: `Bell.csproj`, the project file and `Program.qs`, a template of a :::no-loc(Q#)::: application that we will use to write our application.</span></span> <span data-ttu-id="8ebda-140">El contenido de `Program.qs` debe ser:</span><span class="sxs-lookup"><span data-stu-id="8ebda-140">The content of `Program.qs` should be:</span></span>

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

## <a name="write-the-q-application"></a><span data-ttu-id="8ebda-141">Escritura de la \# aplicación Q</span><span class="sxs-lookup"><span data-stu-id="8ebda-141">Write the Q\# application</span></span>
 
<span data-ttu-id="8ebda-142">Nuestro objetivo es preparar dos qubits en un estado de Quantum específico, mostrando cómo operar en qubits con :::no-loc(Q#)::: para cambiar su estado y demostrar los efectos de la superposición y el incumplimiento.</span><span class="sxs-lookup"><span data-stu-id="8ebda-142">Our goal is to prepare two qubits in a specific quantum state, demonstrating how to operate on qubits with :::no-loc(Q#)::: to change their state and demonstrate the effects of superposition and entanglement.</span></span> <span data-ttu-id="8ebda-143">Compilaremos esta pieza por parte para introducir los Estados, las operaciones y la medida de qubit.</span><span class="sxs-lookup"><span data-stu-id="8ebda-143">We will build this up piece by piece to introduce qubit states, operations, and measurement.</span></span>

### <a name="initialize-qubit-using-measurement"></a><span data-ttu-id="8ebda-144">Inicializar qubit mediante medición</span><span class="sxs-lookup"><span data-stu-id="8ebda-144">Initialize qubit using measurement</span></span>

<span data-ttu-id="8ebda-145">En el primer fragmento de código siguiente, le mostramos cómo trabajar con qubits en :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="8ebda-145">In the first code snippet below, we show you how to work with qubits in :::no-loc(Q#):::.</span></span>  <span data-ttu-id="8ebda-146">Introduciremos dos operaciones [`M`](xref:Microsoft.Quantum.Intrinsic.m) y [`X`](xref:Microsoft.Quantum.Intrinsic.X) que transformarán el estado de un qubit.</span><span class="sxs-lookup"><span data-stu-id="8ebda-146">We’ll introduce two operations, [`M`](xref:Microsoft.Quantum.Intrinsic.m) and [`X`](xref:Microsoft.Quantum.Intrinsic.X) that transform the state of a qubit.</span></span> <span data-ttu-id="8ebda-147">En este fragmento de código, se define una operación `SetQubitState` que toma como parámetro un cúbit y otro parámetro, `desired`, que representa el estado en el que queremos que esté el cúbit.</span><span class="sxs-lookup"><span data-stu-id="8ebda-147">In this code snippet, an operation `SetQubitState` is defined that takes as a parameter a qubit and another parameter, `desired`, representing the state that we would like the qubit to be in.</span></span>  <span data-ttu-id="8ebda-148">La operación `SetQubitState` toma una medida en el cúbit con la operación `M`.</span><span class="sxs-lookup"><span data-stu-id="8ebda-148">The operation `SetQubitState` performs a measurement on the qubit using the operation `M`.</span></span>  <span data-ttu-id="8ebda-149">En :::no-loc(Q#)::: , una medida qubit siempre devuelve `Zero` o `One` .</span><span class="sxs-lookup"><span data-stu-id="8ebda-149">In :::no-loc(Q#):::, a qubit measurement always returns either `Zero` or `One`.</span></span>  <span data-ttu-id="8ebda-150">Si la medida devuelve un valor que no es igual al valor deseado, `SetQubitState` "voltea" el qubit; es decir, ejecuta una `X` operación, que cambia el estado de qubit a un nuevo estado en el que las probabilidades de una medida devuelven `Zero` y `One` se invierten.</span><span class="sxs-lookup"><span data-stu-id="8ebda-150">If the measurement returns a value not equal to the desired value, `SetQubitState` “flips” the qubit; that is, it runs an `X` operation, which changes the qubit state to a new state in which the probabilities of a measurement returning `Zero` and `One` are reversed.</span></span> <span data-ttu-id="8ebda-151">De este modo, `SetQubitState` siempre coloca el qubit de destino en el estado deseado.</span><span class="sxs-lookup"><span data-stu-id="8ebda-151">This way, `SetQubitState` always puts the target qubit in the desired state.</span></span>

<span data-ttu-id="8ebda-152">Reemplace el contenido de `Program.qs` por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="8ebda-152">Replace the contents of `Program.qs` with the following code:</span></span>


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

<span data-ttu-id="8ebda-153">Ahora se puede llamar a esta operación para establecer un cúbit en un estado clásico, ya sea devolviendo `Zero` el 100 % del tiempo o devolviendo `One` el 100 % del tiempo.</span><span class="sxs-lookup"><span data-stu-id="8ebda-153">This operation may now be called to set a qubit to a classical state, either returning `Zero` 100% of the time or returning `One` 100% of the time.</span></span>
<span data-ttu-id="8ebda-154">`Zero` y `One` son constantes que representan los únicos dos resultados posibles de la medida de un cúbit.</span><span class="sxs-lookup"><span data-stu-id="8ebda-154">`Zero` and `One` are constants that represent the only two possible results of a measurement of a qubit.</span></span>

<span data-ttu-id="8ebda-155">La operación `SetQubitState` mide el cúbit.</span><span class="sxs-lookup"><span data-stu-id="8ebda-155">The operation `SetQubitState` measures the qubit.</span></span> <span data-ttu-id="8ebda-156">Si el qubit está en el estado deseado, lo `SetQubitState` deja por sí solo; de lo contrario, al ejecutar la `X` operación, cambiamos el estado de qubit al estado deseado.</span><span class="sxs-lookup"><span data-stu-id="8ebda-156">If the qubit is in the state we want, `SetQubitState` leaves it alone; otherwise, by running the `X` operation, we change the qubit state to the desired state.</span></span>

#### <a name="about-no-locq-operations"></a><span data-ttu-id="8ebda-157">Acerca de :::no-loc(Q#)::: las operaciones</span><span class="sxs-lookup"><span data-stu-id="8ebda-157">About :::no-loc(Q#)::: operations</span></span>

<span data-ttu-id="8ebda-158">Una :::no-loc(Q#)::: operación es una subrutina Quantum.</span><span class="sxs-lookup"><span data-stu-id="8ebda-158">A :::no-loc(Q#)::: operation is a quantum subroutine.</span></span> <span data-ttu-id="8ebda-159">Es decir, es una rutina invocable que contiene llamadas a otras operaciones Quantum.</span><span class="sxs-lookup"><span data-stu-id="8ebda-159">That is, it is a callable routine that contains calls to other quantum operations.</span></span>

<span data-ttu-id="8ebda-160">Los argumentos de una operación se especifican como una tupla, entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="8ebda-160">The arguments to an operation are specified as a tuple, within parentheses.</span></span>

<span data-ttu-id="8ebda-161">El tipo de valor devuelto de la operación se especifica después de un signo de dos puntos.</span><span class="sxs-lookup"><span data-stu-id="8ebda-161">The return type of the operation is specified after a colon.</span></span> <span data-ttu-id="8ebda-162">En este caso, la `SetQubitState` operación no tiene ningún tipo de valor devuelto, por lo que se marca como devuelta `Unit` .</span><span class="sxs-lookup"><span data-stu-id="8ebda-162">In this case, the `SetQubitState` operation has no return type, so it is marked as returning `Unit`.</span></span> <span data-ttu-id="8ebda-163">Es el :::no-loc(Q#)::: equivalente de `unit` en F #, que es aproximadamente análogo a `void` en C#, y una tupla vacía en Python ( `()` , representada por la sugerencia de tipo `Tuple[()]` ).</span><span class="sxs-lookup"><span data-stu-id="8ebda-163">This is the :::no-loc(Q#)::: equivalent of `unit` in F#, which is roughly analogous to `void` in C#, and an empty tuple in Python (`()`, represented by the type hint `Tuple[()]`).</span></span>

<span data-ttu-id="8ebda-164">Ha usado dos operaciones Quantum en la primera :::no-loc(Q#)::: operación:</span><span class="sxs-lookup"><span data-stu-id="8ebda-164">You have used two quantum operations in your first :::no-loc(Q#)::: operation:</span></span>

* <span data-ttu-id="8ebda-165">La [`M`](xref:Microsoft.Quantum.Intrinsic.m) operación, que mide el estado de qubit</span><span class="sxs-lookup"><span data-stu-id="8ebda-165">The [`M`](xref:Microsoft.Quantum.Intrinsic.m) operation, which measures the state of the qubit</span></span>
* <span data-ttu-id="8ebda-166">La [`X`](xref:Microsoft.Quantum.Intrinsic.X) operación, que voltea el estado de un qubit</span><span class="sxs-lookup"><span data-stu-id="8ebda-166">The [`X`](xref:Microsoft.Quantum.Intrinsic.X) operation, which flips the state of a qubit</span></span>

<span data-ttu-id="8ebda-167">Una operación cuántica transforma el estado de un cúbit.</span><span class="sxs-lookup"><span data-stu-id="8ebda-167">A quantum operation transforms the state of a qubit.</span></span> <span data-ttu-id="8ebda-168">Algunos usuarios hablan de puertas cuánticas en lugar de operaciones, por analogía con las puertas lógicas clásicas.</span><span class="sxs-lookup"><span data-stu-id="8ebda-168">Sometime people talk about quantum gates instead of operations, in analogy to classical logic gates.</span></span> <span data-ttu-id="8ebda-169">Esto tiene su origen en los primeros tiempos de la computación cuántica, cuando los algoritmos eran una simple construcción teórica y se visualizaban como diagramas, de forma similar a los diagramas de circuitos de la computación clásica.</span><span class="sxs-lookup"><span data-stu-id="8ebda-169">This is rooted in the early days of quantum computing when algorithms were merely a theoretical construct and visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>

### <a name="counting-measurement-outcomes"></a><span data-ttu-id="8ebda-170">Recuento de los resultados de la medición</span><span class="sxs-lookup"><span data-stu-id="8ebda-170">Counting measurement outcomes</span></span>

<span data-ttu-id="8ebda-171">Para mostrar el efecto de la operación `SetQubitState`, se agrega una operación `TestBellState`.</span><span class="sxs-lookup"><span data-stu-id="8ebda-171">To demonstrate the effect of the `SetQubitState` operation, a `TestBellState` operation is then added.</span></span> <span data-ttu-id="8ebda-172">Esta operación toma como entrada un `Zero` o `One`, llama a la operación `SetQubitState` un número determinado de veces con esa entrada y cuenta el número de veces que la medida del cúbit devolvió `Zero` y el número de veces que se devolvió `One`.</span><span class="sxs-lookup"><span data-stu-id="8ebda-172">This operation takes as input a `Zero` or `One`, and calls the `SetQubitState` operation some number of times with that input, and counts the number of times that `Zero` was returned from the measurement of the qubit and the number of times that `One` was returned.</span></span> <span data-ttu-id="8ebda-173">Por supuesto, en esta primera simulación de la operación `TestBellState` esperamos que la salida muestre que todas las medidas de un cúbit establecidas con `Zero` como entrada del parámetro devolverán `Zero`, y todas las medidas de un cúbit establecidas con `One` como entrada del parámetro devolverán `One`.</span><span class="sxs-lookup"><span data-stu-id="8ebda-173">Of course, in this first simulation of the `TestBellState` operation, we expect that the output will show that all measurements of the qubit set with `Zero` as the parameter input will return `Zero`, and all measurements of a qubit set with `One` as the parameter input will return `One`.</span></span> <span data-ttu-id="8ebda-174">Más adelante, agregaremos código a `TestBellState` para mostrar la superposición y el inenredo.</span><span class="sxs-lookup"><span data-stu-id="8ebda-174">Further on, we’ll add code to `TestBellState` to demonstrate superposition and entanglement.</span></span>

<span data-ttu-id="8ebda-175">Agregue la siguiente operación al archivo `Program.qs`, dentro del espacio de nombres, después del final de la operación de `SetQubitState`:</span><span class="sxs-lookup"><span data-stu-id="8ebda-175">Add the following operation to the `Program.qs` file, inside the namespace, after the end of the `SetQubitState` operation:</span></span>

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
<span data-ttu-id="8ebda-176">Tenga en cuenta que hemos agregado una línea antes de `return` que imprima un mensaje explicativo en la consola con la función ( `Message` ) [Microsoft. Quantum. Intrinsic. Message]</span><span class="sxs-lookup"><span data-stu-id="8ebda-176">Note that we added a line before the `return` to print an explanatory message in the console with the function (`Message`)[microsoft.quantum.intrinsic.message]</span></span>

<span data-ttu-id="8ebda-177">Esta operación (`TestBellState`) creará un bucle para `count` iteraciones, establecerá un valor de `initial` especificado en cúbits y, a continuación, medirá (`M`) el resultado.</span><span class="sxs-lookup"><span data-stu-id="8ebda-177">This operation (`TestBellState`) will loop for `count` iterations, set a specified `initial` value on a qubit and then measure (`M`) the result.</span></span> <span data-ttu-id="8ebda-178">Recopilará estadísticas sobre cuántos ceros y unos se han medido y los devolverá al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8ebda-178">It will gather statistics on how many zeros and ones we've measured and return them to the caller.</span></span> <span data-ttu-id="8ebda-179">Realiza otra operación necesaria.</span><span class="sxs-lookup"><span data-stu-id="8ebda-179">It performs one other necessary operation.</span></span> <span data-ttu-id="8ebda-180">Restablece el cúbit a un estado conocido (`Zero`) antes de devolverlo, lo que permite que otros usuarios asignen este cúbit en un estado conocido.</span><span class="sxs-lookup"><span data-stu-id="8ebda-180">It resets the qubit to a known state (`Zero`) before returning it allowing others to allocate this qubit in a known state.</span></span> <span data-ttu-id="8ebda-181">Esto es necesario para la instrucción `using`.</span><span class="sxs-lookup"><span data-stu-id="8ebda-181">This is required by the `using` statement.</span></span>

#### <a name="about-variables-in-q"></a><span data-ttu-id="8ebda-182">Acerca de las variables en Q\#</span><span class="sxs-lookup"><span data-stu-id="8ebda-182">About variables in Q\#</span></span>

<span data-ttu-id="8ebda-183">De forma predeterminada, las variables de :::no-loc(Q#)::: son inmutables; su valor no se puede cambiar una vez enlazado.</span><span class="sxs-lookup"><span data-stu-id="8ebda-183">By default, variables in :::no-loc(Q#)::: are immutable; their value may not be changed after they are bound.</span></span> <span data-ttu-id="8ebda-184">La palabra clave `let` se utiliza para indicar el enlace de una variable inmutable.</span><span class="sxs-lookup"><span data-stu-id="8ebda-184">The `let` keyword is used to indicate the binding of an immutable variable.</span></span> <span data-ttu-id="8ebda-185">Los argumentos de la operación son siempre inmutables.</span><span class="sxs-lookup"><span data-stu-id="8ebda-185">Operation arguments are always immutable.</span></span>

<span data-ttu-id="8ebda-186">Si necesita una variable cuyo valor puede cambiar, como `numOnes` en el ejemplo, puede declarar la variable con la palabra clave `mutable`.</span><span class="sxs-lookup"><span data-stu-id="8ebda-186">If you need a variable whose value can change, such as `numOnes` in the example, you can declare the variable with the `mutable` keyword.</span></span> <span data-ttu-id="8ebda-187">Se puede cambiar el valor de una variable mutable mediante una instrucción `set`.</span><span class="sxs-lookup"><span data-stu-id="8ebda-187">A mutable variable's value may be changed using a `set` statement.</span></span>

<span data-ttu-id="8ebda-188">En ambos casos, el compilador deduce el tipo de una variable.</span><span class="sxs-lookup"><span data-stu-id="8ebda-188">In both cases, the type of a variable is inferred by the compiler.</span></span> <span data-ttu-id="8ebda-189">:::no-loc(Q#)::: no requiere ninguna anotación de tipo para las variables.</span><span class="sxs-lookup"><span data-stu-id="8ebda-189">:::no-loc(Q#)::: doesn't require any type annotations for variables.</span></span>

#### <a name="about-using-statements-in-q"></a><span data-ttu-id="8ebda-190">Acerca `using` de las instrucciones en Q\#</span><span class="sxs-lookup"><span data-stu-id="8ebda-190">About `using` statements in Q\#</span></span>

<span data-ttu-id="8ebda-191">La `using` instrucción también es especial para :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="8ebda-191">The `using` statement is also special to :::no-loc(Q#):::.</span></span> <span data-ttu-id="8ebda-192">Se usa para asignar cúbits para su uso en un bloque de código.</span><span class="sxs-lookup"><span data-stu-id="8ebda-192">It is used to allocate qubits for use in a block of code.</span></span> <span data-ttu-id="8ebda-193">En :::no-loc(Q#)::: , todos los qubits se asignan y liberan dinámicamente, en lugar de ser recursos fijos que están ahí para toda la duración de un algoritmo complejo.</span><span class="sxs-lookup"><span data-stu-id="8ebda-193">In :::no-loc(Q#):::, all qubits are dynamically allocated and released, rather than being fixed resources that are there for the entire lifetime of a complex algorithm.</span></span> <span data-ttu-id="8ebda-194">Una instrucción `using` asigna un conjunto de cúbits al principio y libera esos cúbits al final del bloque.</span><span class="sxs-lookup"><span data-stu-id="8ebda-194">A `using` statement allocates a set of qubits at the start, and releases those qubits at the end of the block.</span></span>

## <a name="run-the-code-from-the-command-prompt"></a><span data-ttu-id="8ebda-195">Ejecutar el código desde el símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="8ebda-195">Run the code from the command prompt</span></span>

<span data-ttu-id="8ebda-196">Para ejecutar el código, es necesario indicar al compilador *que* se puede ejecutar cuando se proporciona el `dotnet run` comando.</span><span class="sxs-lookup"><span data-stu-id="8ebda-196">In order to run the code we need to tell the compiler *which* callable to run when we provide the `dotnet run` command.</span></span> <span data-ttu-id="8ebda-197">Esto se hace con un simple cambio en el :::no-loc(Q#)::: archivo agregando una línea que `@EntryPoint()` preceda directamente a la operación invocable: `TestBellState` en este caso.</span><span class="sxs-lookup"><span data-stu-id="8ebda-197">This is done with a simple change in the :::no-loc(Q#)::: file by adding a line with `@EntryPoint()` directly preceding the callable: the `TestBellState` operation in this case.</span></span> <span data-ttu-id="8ebda-198">El código completo debe ser:</span><span class="sxs-lookup"><span data-stu-id="8ebda-198">The full code should be:</span></span>

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

<span data-ttu-id="8ebda-199">Para ejecutar el programa, es necesario especificar `count` los `initial` argumentos y desde el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="8ebda-199">To run the program we need to specify `count` and `initial` arguments from the command prompt.</span></span> <span data-ttu-id="8ebda-200">Vamos a elegir, por ejemplo `count = 1000` , y `initial = One` .</span><span class="sxs-lookup"><span data-stu-id="8ebda-200">Let's choose for example `count = 1000` and `initial = One`.</span></span> <span data-ttu-id="8ebda-201">Escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="8ebda-201">Enter the following command:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

<span data-ttu-id="8ebda-202">Y debe observar el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="8ebda-202">And you should observe the following output:</span></span>

```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

<span data-ttu-id="8ebda-203">Si lo intenta, `initial = Zero` debe observar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8ebda-203">If you try with `initial = Zero` you should observe:</span></span>

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

## <a name="prepare-superposition"></a><span data-ttu-id="8ebda-204">Preparar la superposición</span><span class="sxs-lookup"><span data-stu-id="8ebda-204">Prepare superposition</span></span>

<span data-ttu-id="8ebda-205">Ahora veamos cómo :::no-loc(Q#)::: expresa cómo expresar qubits en la superposición.</span><span class="sxs-lookup"><span data-stu-id="8ebda-205">Now let’s look at how :::no-loc(Q#)::: expresses ways to put qubits in superposition.</span></span>  <span data-ttu-id="8ebda-206">Recuerde que el estado de un cúbit puede ser una superposición de 0 y 1.</span><span class="sxs-lookup"><span data-stu-id="8ebda-206">Recall that the state of a qubit can be in a superposition of 0 and 1.</span></span>  <span data-ttu-id="8ebda-207">Usaremos la operación `Hadamard` para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="8ebda-207">We’ll use the `Hadamard` operation to accomplish this.</span></span> <span data-ttu-id="8ebda-208">Si el cúbit está en cualquiera de los estados clásicos (al medir devuelve `Zero` siempre o `One` siempre), las operaciones `Hadamard` o `H` pondrán el cúbit en un estado tal que al medirlo, devolverá `Zero` el 50 % del tiempo y devolverá `One` el otro 50 % del tiempo.</span><span class="sxs-lookup"><span data-stu-id="8ebda-208">If the qubit is in either of the classical states (where a measurement returns `Zero` always or `One` always), then the `Hadamard` or `H` operation will put the qubit in a state where a measurement of the qubit will return `Zero` 50% of the time and return `One` 50% of the time.</span></span>  <span data-ttu-id="8ebda-209">Conceptualmente, el cúbit se puede considerar a medio camino entre `Zero` y `One`.</span><span class="sxs-lookup"><span data-stu-id="8ebda-209">Conceputually, the qubit can be thought of as halfway between the `Zero` and `One`.</span></span>  <span data-ttu-id="8ebda-210">Ahora, cuando simulemos la operación `TestBellState`, veremos que los resultados devolverán aproximadamente un número igual de `Zero` y `One` después de medir.</span><span class="sxs-lookup"><span data-stu-id="8ebda-210">Now, when we simulate the `TestBellState` operation, we will see the results will return roughly an equal number of `Zero` and `One` after measurement.</span></span>  

### <a name="x-flips-qubit-state"></a><span data-ttu-id="8ebda-211">`X` Voltea el estado de qubit</span><span class="sxs-lookup"><span data-stu-id="8ebda-211">`X` flips qubit state</span></span>

<span data-ttu-id="8ebda-212">En primer lugar, simplemente intentaremos voltear qubit (si el qubit está en el `Zero` Estado, se pasará a `One` y viceversa).</span><span class="sxs-lookup"><span data-stu-id="8ebda-212">First we'll just try to flip the qubit (if the qubit is in `Zero` state it will flip to `One` and vice versa).</span></span> <span data-ttu-id="8ebda-213">Esto se logra con una operación `X` antes de medirlo en `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="8ebda-213">This is accomplished by performing an `X` operation before we measure it in `TestBellState`:</span></span>

```qsharp
X(qubit);
let res = M(qubit);
```

<span data-ttu-id="8ebda-214">Ahora se invierten los resultados:</span><span class="sxs-lookup"><span data-stu-id="8ebda-214">Now the results are reversed:</span></span>

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

<span data-ttu-id="8ebda-215">Ahora vamos a explorar las propiedades Quantum de qubits.</span><span class="sxs-lookup"><span data-stu-id="8ebda-215">Now let's explore the quantum properties of the qubits.</span></span>

### <a name="h-prepares-superposition"></a><span data-ttu-id="8ebda-216">`H` prepara la superposición</span><span class="sxs-lookup"><span data-stu-id="8ebda-216">`H` prepares superposition</span></span>

<span data-ttu-id="8ebda-217">Lo único que tenemos que hacer es reemplazar la operación `X` de la ejecución anterior por una operación `H` o Hadamard.</span><span class="sxs-lookup"><span data-stu-id="8ebda-217">All we need to do is replace the `X` operation in the previous run with an `H` or Hadamard operation.</span></span> <span data-ttu-id="8ebda-218">En lugar de voltear totalmente el cúbit de 0 a 1, solo lo voltearemos a la mitad.</span><span class="sxs-lookup"><span data-stu-id="8ebda-218">Instead of flipping the qubit all the way from 0 to 1, we will only flip it halfway.</span></span> <span data-ttu-id="8ebda-219">Las líneas reemplazadas en `TestBellState` ahora tienen el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="8ebda-219">The replaced lines in `TestBellState` now look like:</span></span>

```qsharp
H(qubit);
let res = M(qubit);
```

<span data-ttu-id="8ebda-220">Ahora tenemos resultados más interesantes:</span><span class="sxs-lookup"><span data-stu-id="8ebda-220">Now the results get more interesting:</span></span>

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

<span data-ttu-id="8ebda-221">Cada vez que medimos, solicitamos un valor clásico, pero el cúbit se encuentra a medio camino entre 0 y 1, por lo que obtenemos (estadísticamente) 0 la mitad del tiempo y 1 la otra mitad del tiempo.</span><span class="sxs-lookup"><span data-stu-id="8ebda-221">Every time we measure, we ask for a classical value, but the qubit is halfway between 0 and 1, so we get (statistically) 0 half the time and 1 half the time.</span></span>
<span data-ttu-id="8ebda-222">Esto se conoce como **superposición** y nos proporciona nuestra primera vista real en un estado cuántico.</span><span class="sxs-lookup"><span data-stu-id="8ebda-222">This is known as **superposition** and gives us our first real view into a quantum state.</span></span>

## <a name="prepare-entanglement"></a><span data-ttu-id="8ebda-223">Preparación del entrelazamiento</span><span class="sxs-lookup"><span data-stu-id="8ebda-223">Prepare entanglement</span></span>

<span data-ttu-id="8ebda-224">Ahora veremos cómo expresa las :::no-loc(Q#)::: maneras de entangle qubits.</span><span class="sxs-lookup"><span data-stu-id="8ebda-224">Now let’s look at how :::no-loc(Q#)::: expresses ways to entangle qubits.</span></span>
<span data-ttu-id="8ebda-225">En primer lugar, establecemos el primer cúbit en el estado inicial y después usamos la operación `H` para ponerlo en superposición.</span><span class="sxs-lookup"><span data-stu-id="8ebda-225">First, we set the first qubit to the initial state and then use the `H` operation to put it into superposition.</span></span>  <span data-ttu-id="8ebda-226">A continuación, antes de que se mida el primer qubit, usamos una nueva operación ( `CNOT` ), que significa *controlada* por.</span><span class="sxs-lookup"><span data-stu-id="8ebda-226">Then, before we measure the first qubit, we use a new operation (`CNOT`), which stands for *Controlled-NOT* .</span></span>  <span data-ttu-id="8ebda-227">El resultado de la ejecución de esta operación en dos qubits es voltear el segundo qubit si el primer qubit es `One` .</span><span class="sxs-lookup"><span data-stu-id="8ebda-227">The result of running this operation on two qubits is to flip the second qubit if the first qubit is `One`.</span></span>  <span data-ttu-id="8ebda-228">Ahora, los dos cúbits están entrelazados.</span><span class="sxs-lookup"><span data-stu-id="8ebda-228">Now, the two qubits are entangled.</span></span>  <span data-ttu-id="8ebda-229">Nuestras estadísticas del primer cúbit no han cambiado (50-50 de probabilidades de `Zero` o `One` después de medir) pero ahora, cuando medimos el segundo cúbit, es __siempre__ igual que lo que se midió para el primer cúbit.</span><span class="sxs-lookup"><span data-stu-id="8ebda-229">Our statistics for the first qubit haven't changed (50-50 chance of a `Zero` or a `One` after measurement), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit.</span></span> <span data-ttu-id="8ebda-230">Nuestro `CNOT` ha hecho el entrelazamiento de los dos cúbits, de modo que lo que le suceda a uno, le sucede al otro.</span><span class="sxs-lookup"><span data-stu-id="8ebda-230">Our `CNOT` has entangled the two qubits, so that whatever happens to one of them, happens to the other.</span></span> <span data-ttu-id="8ebda-231">Si invirtió las medidas (hizo la del segundo cúbit antes del primero), sucedería lo mismo.</span><span class="sxs-lookup"><span data-stu-id="8ebda-231">If you reversed the measurements (did the second qubit before the first), the same thing would happen.</span></span> <span data-ttu-id="8ebda-232">La primera medida sería aleatoria y la segunda sería en el paso de bloqueo con lo que se haya descubierto en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="8ebda-232">The first measurement would be random and the second would be in lock step with whatever was discovered for the first.</span></span>

<span data-ttu-id="8ebda-233">Lo primero que debemos hacer es asignar dos qubits en lugar de uno en `TestBellState` :</span><span class="sxs-lookup"><span data-stu-id="8ebda-233">The first thing we'll need to do is allocate two qubits instead of one in `TestBellState`:</span></span>

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

<span data-ttu-id="8ebda-234">Esto nos permitirá agregar una nueva operación (`CNOT`) antes de medir (`M`) en `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="8ebda-234">This will allow us to add a new operation (`CNOT`) before we measure  (`M`) in `TestBellState`:</span></span>

```qsharp
SetQubitState(initial, q0);
SetQubitState(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

<span data-ttu-id="8ebda-235">Hemos agregado otra operación `SetQubitState` para inicializar el primer cúbit para asegurarnos de que siempre está en `Zero` cuando se inicia.</span><span class="sxs-lookup"><span data-stu-id="8ebda-235">We've added another `SetQubitState` operation to initialize the first qubit to make sure that it's always in the `Zero` state when we start.</span></span>

<span data-ttu-id="8ebda-236">También necesitamos restablecer el segundo cúbit antes de liberarlo.</span><span class="sxs-lookup"><span data-stu-id="8ebda-236">We also need to reset the second qubit before releasing it.</span></span>

```qsharp
SetQubitState(Zero, q0);
SetQubitState(Zero, q1);
```

<span data-ttu-id="8ebda-237">La rutina completa se ve ahora así:</span><span class="sxs-lookup"><span data-stu-id="8ebda-237">The full routine now looks like this:</span></span>

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

<span data-ttu-id="8ebda-238">Si la ejecutamos, obtendremos exactamente el mismo resultado 50-50 que obtuvimos antes.</span><span class="sxs-lookup"><span data-stu-id="8ebda-238">If we run this, we'll get exactly the same 50-50 result we got before.</span></span> <span data-ttu-id="8ebda-239">Sin embargo, ahora nos interesa cómo reacciona el segundo cúbit al primero que se mide.</span><span class="sxs-lookup"><span data-stu-id="8ebda-239">However, what we're interested in is how the second qubit reacts to the first being measured.</span></span> <span data-ttu-id="8ebda-240">Agregaremos esta estadística con una nueva versión de la operación `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="8ebda-240">We'll add this statistic with a new version of the `TestBellState` operation:</span></span>

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

<span data-ttu-id="8ebda-241">El nuevo valor devuelto (`agree`) realiza un seguimiento de cada vez que la medida del primer cúbit coincide con la medida del segundo.</span><span class="sxs-lookup"><span data-stu-id="8ebda-241">The new return value (`agree`) keeps track of every time the measurement from the first qubit matches the measurement of the second qubit.</span></span>

<span data-ttu-id="8ebda-242">Ejecutar el código que obtenemos:</span><span class="sxs-lookup"><span data-stu-id="8ebda-242">Running the code we obtain:</span></span>

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

<span data-ttu-id="8ebda-243">Tal y como se indicó en la introducción, nuestras estadísticas del primer cúbit no han cambiado (50-50 de probabilidades de 0 o 1 después de medir) pero ahora, cuando medimos el segundo cúbit, es __siempre__ igual que lo que se midió para el primer cúbit, porque están entrelazados.</span><span class="sxs-lookup"><span data-stu-id="8ebda-243">As stated in the overview, our statistics for the first qubit haven't changed (50-50 chance of a 0 or a 1), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit, because they are entangled!</span></span>

## <a name="next-steps"></a><span data-ttu-id="8ebda-244">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8ebda-244">Next steps</span></span>

<span data-ttu-id="8ebda-245">En el tutorial [de la búsqueda de Grover](xref:microsoft.quantum.quickstarts.search) se muestra cómo compilar y ejecutar la búsqueda de Grover, uno de los algoritmos de procesamiento de Quantum más populares y ofrece un buen ejemplo de un :::no-loc(Q#)::: programa que se puede usar para solucionar problemas reales con la informática Quantum.</span><span class="sxs-lookup"><span data-stu-id="8ebda-245">The tutorial [Grover’s search](xref:microsoft.quantum.quickstarts.search) shows you how to build and run Grover search, one of the most popular quantum computing algorithms and offers a nice example of a :::no-loc(Q#)::: program that can be used to solve real problems with quantum computing.</span></span>  

<span data-ttu-id="8ebda-246">Introducción al [Kit de desarrollo de Quantum](xref:microsoft.quantum.welcome) recomienda más formas de aprender :::no-loc(Q#)::: y la programación de Quantum.</span><span class="sxs-lookup"><span data-stu-id="8ebda-246">[Get Started with the Quantum Development Kit](xref:microsoft.quantum.welcome) recommends more ways to learn :::no-loc(Q#)::: and quantum programming.</span></span>
