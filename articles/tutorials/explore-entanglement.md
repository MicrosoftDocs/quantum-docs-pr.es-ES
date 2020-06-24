---
title: Exploración del entrelazamiento con Q#
description: Obtenga información sobre cómo escribir un programa cuántico en Q#. Desarrolle una aplicación de estado Bell mediante el kit de desarrollo de Microsoft Quantum (QDK)
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 294366b884da93f11c60cfdbdce9b40cf5202b0d
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275309"
---
# <a name="tutorial-explore-entanglement-with-q"></a><span data-ttu-id="575ef-104">Tutorial: Exploración del entrelazamiento con Q\#</span><span class="sxs-lookup"><span data-stu-id="575ef-104">Tutorial: Explore entanglement with Q\#</span></span>

<span data-ttu-id="575ef-105">En este tutorial, se muestra cómo escribir un programa de Q# que manipula y mide cúbits, y muestra los efectos de la superposición y el entrelazamiento.</span><span class="sxs-lookup"><span data-stu-id="575ef-105">In this tutorial, we show you how to write a Q# program that manipulates and measures qubits and demonstrates the effects of superposition and entanglement.</span></span>
<span data-ttu-id="575ef-106">Incluye instrucciones para instalar QDK, compilar el programa y ejecutarlo en un simulador cuántico.</span><span class="sxs-lookup"><span data-stu-id="575ef-106">This guides you on installing the QDK, building the program and executing that program on a quantum simulator.</span></span>  

<span data-ttu-id="575ef-107">Escribirá una aplicación llamada Bell para demostrar el entrelazamiento cuántico.</span><span class="sxs-lookup"><span data-stu-id="575ef-107">You will write an application called Bell to demonstrate quantum entanglement.</span></span>
<span data-ttu-id="575ef-108">El nombre Bell hace referencia a los estados de Bell, que son estados cuánticos específicos de dos cúbits que se usan para representar los ejemplos más sencillos de la superposición y el entrelazamiento cuántico.</span><span class="sxs-lookup"><span data-stu-id="575ef-108">The name Bell is in reference to Bell states, which are specific quantum states of two qubits that are used to represent the simplest examples of superposition and quantum entanglement.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="575ef-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="575ef-109">Prerequisites</span></span>

<span data-ttu-id="575ef-110">Si está listo para empezar a codificar, siga estos pasos antes de continuar:</span><span class="sxs-lookup"><span data-stu-id="575ef-110">If you are ready to start coding, follow these steps before proceeding:</span></span> 

* <span data-ttu-id="575ef-111">Instale el kit de desarrollo de Microsoft Quantum para [Python](xref:microsoft.quantum.install.python) o [.NET](xref:microsoft.quantum.install.cs).</span><span class="sxs-lookup"><span data-stu-id="575ef-111">Install the Quantum Development Kit for [Python](xref:microsoft.quantum.install.python) or [.NET](xref:microsoft.quantum.install.cs).</span></span>
* <span data-ttu-id="575ef-112">Si ya tiene instalado el QDK, asegúrese de que tiene [actualizada](xref:microsoft.quantum.update) la última versión</span><span class="sxs-lookup"><span data-stu-id="575ef-112">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>

<span data-ttu-id="575ef-113">También puede seguir sin instalar QDK y revisar las introducciones al lenguaje de programación Q# y los primeros conceptos de la computación cuántica.</span><span class="sxs-lookup"><span data-stu-id="575ef-113">You can also follow along with the narrative without installing the QDK, reviewing the overviews of the Q# programming language and the first concepts of quantum computing.</span></span>

## <a name="demonstrating-qubit-behavior-with-q"></a><span data-ttu-id="575ef-114">Demostración del comportamiento de los cúbits con Q#</span><span class="sxs-lookup"><span data-stu-id="575ef-114">Demonstrating qubit behavior with Q#</span></span>

<span data-ttu-id="575ef-115">Recuerde nuestra [definición sencilla de cúbit](xref:microsoft.quantum.overview.understanding).</span><span class="sxs-lookup"><span data-stu-id="575ef-115">Recall our simple [definition of a qubit](xref:microsoft.quantum.overview.understanding).</span></span>  <span data-ttu-id="575ef-116">Mientras que los bits clásicos contienen un único valor binario, como 0 o 1, el estado de un [cúbit](xref:microsoft.quantum.glossary#qubit) puede ser una **superposición** de 0 y 1.</span><span class="sxs-lookup"><span data-stu-id="575ef-116">Where classical bits hold a single binary value such as a 0 or 1, the state of a [qubit](xref:microsoft.quantum.glossary#qubit) can be in a **superposition** of 0 and 1.</span></span>  <span data-ttu-id="575ef-117">Conceptualmente, un cúbit se podría considerar como una dirección en el espacio (también conocida como vector).</span><span class="sxs-lookup"><span data-stu-id="575ef-117">Conceptually, a qubit can be thought of as a direction in space (also known as a vector).</span></span>  <span data-ttu-id="575ef-118">Un cúbit puede estar en cualquiera de las direcciones posibles.</span><span class="sxs-lookup"><span data-stu-id="575ef-118">A qubit can be in any of the possible directions.</span></span> <span data-ttu-id="575ef-119">Los dos **estados clásicos** son las dos direcciones, que representan el 100 % de probabilidad de medir 0 y el 100 % de probabilidad de medir 1.</span><span class="sxs-lookup"><span data-stu-id="575ef-119">The two **classical states** are the two directions; representing 100% chance of measuring 0 and 100% chance of measuring 1.</span></span>  <span data-ttu-id="575ef-120">Esta representación se visualiza también más formalmente con la [esfera de Bloch](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span><span class="sxs-lookup"><span data-stu-id="575ef-120">This representation is also more formally visualized by the [bloch sphere](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).</span></span>

<span data-ttu-id="575ef-121">La acción de medir genera un resultado binario y cambia el estado del cúbit.</span><span class="sxs-lookup"><span data-stu-id="575ef-121">The act of measurement produces a binary result and changes a qubit state.</span></span> <span data-ttu-id="575ef-122">La medida produce un valor binario, ya sea 0 o 1.</span><span class="sxs-lookup"><span data-stu-id="575ef-122">Measurement produces a binary value, either 0 or 1.</span></span>  <span data-ttu-id="575ef-123">El cúbit pasa de estar en superposición (cualquier dirección) a estar en uno de los estados clásicos.</span><span class="sxs-lookup"><span data-stu-id="575ef-123">The qubit goes from being in superposition (any direction) to one of the classical states.</span></span>  <span data-ttu-id="575ef-124">Después, si se repite la medida sin que intervenga ninguna operación, se produce el mismo resultado binario.</span><span class="sxs-lookup"><span data-stu-id="575ef-124">Thereafter, repeating the same measurement without any intervening operations produces the same binary result.</span></span>  

<span data-ttu-id="575ef-125">Varios cúbits pueden estar [**entrelazados**](xref:microsoft.quantum.glossary#entanglement).</span><span class="sxs-lookup"><span data-stu-id="575ef-125">Multiple qubits can be [**entangled**](xref:microsoft.quantum.glossary#entanglement).</span></span> <span data-ttu-id="575ef-126">Cuando se toma una medida de un cúbit entrelazado, se actualizan también los conocimientos del estado de los otros.</span><span class="sxs-lookup"><span data-stu-id="575ef-126">When we make a measurement of one entangled qubit, our knowledge of the state of the other(s) is updated as well.</span></span>

<span data-ttu-id="575ef-127">Ahora, estamos listos para demostrar cómo expresa Q# este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="575ef-127">Now, we're ready to demonstrate how Q# expresses this behavior.</span></span>  <span data-ttu-id="575ef-128">Comience con el programa más sencillo posible y compílelo para demostrar la superposición cuántica y el entrelazamiento cuántico.</span><span class="sxs-lookup"><span data-stu-id="575ef-128">You start with the simplest program possible and build it up to demonstrate quantum superposition and quantum entanglement.</span></span>

## <a name="setup"></a><span data-ttu-id="575ef-129">Configurar</span><span class="sxs-lookup"><span data-stu-id="575ef-129">Setup</span></span>

<span data-ttu-id="575ef-130">En este tutorial, se usan programas host y se compone de dos partes:</span><span class="sxs-lookup"><span data-stu-id="575ef-130">This tutorial uses a host programs and consists of two parts:</span></span>

1. <span data-ttu-id="575ef-131">Una serie de algoritmos cuánticos, implementados mediante el lenguaje de programación cuántica Q#.</span><span class="sxs-lookup"><span data-stu-id="575ef-131">A series of quantum algorithms, implemented using the Q# quantum programming language.</span></span>
1. <span data-ttu-id="575ef-132">Un programa host, implementado en Python o C#, que actúa como el punto de entrada principal e invoca operaciones de Q# para ejecutar algoritmos cuánticos.</span><span class="sxs-lookup"><span data-stu-id="575ef-132">A host program, implemented in either Python or C#, that serves as the main entry point and invokes Q# operations to execute the quantum algorithms.</span></span>

#### <a name="python"></a>[<span data-ttu-id="575ef-133">Python</span><span class="sxs-lookup"><span data-stu-id="575ef-133">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="575ef-134">Elija una ubicación para su aplicación</span><span class="sxs-lookup"><span data-stu-id="575ef-134">Choose a location for your application</span></span>

1. <span data-ttu-id="575ef-135">Cree un archivo llamado `Bell.qs`.</span><span class="sxs-lookup"><span data-stu-id="575ef-135">Create a file called `Bell.qs`.</span></span> <span data-ttu-id="575ef-136">Este archivo contendrá el código Q#.</span><span class="sxs-lookup"><span data-stu-id="575ef-136">This file will contain your Q# code.</span></span>

1. <span data-ttu-id="575ef-137">Cree un archivo llamado `host.py`.</span><span class="sxs-lookup"><span data-stu-id="575ef-137">Create a file called `host.py`.</span></span> <span data-ttu-id="575ef-138">Este archivo contendrá el código host Python.</span><span class="sxs-lookup"><span data-stu-id="575ef-138">This file will contain your Python host code.</span></span>

#### <a name="c-command-line"></a>[<span data-ttu-id="575ef-139">Línea de comandos para C#</span><span class="sxs-lookup"><span data-stu-id="575ef-139">C# Command Line</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="575ef-140">Cree un nuevo proyecto de Q#</span><span class="sxs-lookup"><span data-stu-id="575ef-140">Create a new Q# project:</span></span>

    ```
    dotnet new console -lang Q# --output Bell
    cd Bell
    ```

    <span data-ttu-id="575ef-141">Debería ver un archivo `.csproj`, un archivo Q# denominado `Operations.qs` y un archivo de programa host llamado `Driver.cs`</span><span class="sxs-lookup"><span data-stu-id="575ef-141">You should see a `.csproj` file, a Q# file called `Operations.qs`, and a host program file called `Driver.cs`</span></span>

1. <span data-ttu-id="575ef-142">Cambie el nombre del archivo Q#</span><span class="sxs-lookup"><span data-stu-id="575ef-142">Rename the Q# file</span></span>

    ```
    mv Operation.qs Bell.qs
    ```

#### <a name="visual-studio"></a>[<span data-ttu-id="575ef-143">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="575ef-143">Visual Studio</span></span>](#tab/tabid-vs2019)

1. <span data-ttu-id="575ef-144">Creación de un nuevo proyecto</span><span class="sxs-lookup"><span data-stu-id="575ef-144">Create a new project</span></span>

   * <span data-ttu-id="575ef-145">Abra Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="575ef-145">Open Visual Studio</span></span>
   * <span data-ttu-id="575ef-146">En el menú **Archivo**, seleccione **Nuevo** -> **Proyecto...**</span><span class="sxs-lookup"><span data-stu-id="575ef-146">Go to the **File** menu and select **New** -> **Project...**</span></span>
   * <span data-ttu-id="575ef-147">En el explorador de plantillas de proyecto, escriba `Q#` en el campo de búsqueda y seleccione la plantilla `Q# Application`.</span><span class="sxs-lookup"><span data-stu-id="575ef-147">In the project template explorer, type `Q#` into the search field and select the `Q# Application` template</span></span>
   * <span data-ttu-id="575ef-148">Asígnele el nombre `Bell` a su proyecto</span><span class="sxs-lookup"><span data-stu-id="575ef-148">Give your project the name `Bell`</span></span>

1. <span data-ttu-id="575ef-149">Cambie el nombre del archivo Q#</span><span class="sxs-lookup"><span data-stu-id="575ef-149">Rename the Q# file</span></span>

   * <span data-ttu-id="575ef-150">Vaya hasta **Explorador de soluciones**</span><span class="sxs-lookup"><span data-stu-id="575ef-150">Navigate to the **Solution Explorer**</span></span>
   * <span data-ttu-id="575ef-151">Haga clic con el botón derecho en el archivo `Operations.qs`</span><span class="sxs-lookup"><span data-stu-id="575ef-151">Right click on the `Operations.qs` file</span></span>
   * <span data-ttu-id="575ef-152">Cambie su nombre por `Bell.qs`</span><span class="sxs-lookup"><span data-stu-id="575ef-152">Rename it to `Bell.qs`</span></span>

* * *

## <a name="write-a-q-operation"></a><span data-ttu-id="575ef-153">Escriba una operación de Q#</span><span class="sxs-lookup"><span data-stu-id="575ef-153">Write a Q# operation</span></span>

<span data-ttu-id="575ef-154">Nuestros objetivos son: preparar dos cúbits en un estado cuántico específico; demostrar cómo operar en los cúbits con Q# para cambiar su estado; y demostrar los efectos de la superposición y el entrelazamiento.</span><span class="sxs-lookup"><span data-stu-id="575ef-154">Our goal is to prepare two qubits in a specific quantum state, demonstrating how to operate on qubits with Q# to change their state and demonstrate the effects of superposition and entanglement.</span></span> <span data-ttu-id="575ef-155">Crearemos esto paso a paso para mostrar los estados del cúbit, las operaciones y la medida.</span><span class="sxs-lookup"><span data-stu-id="575ef-155">We will build this up piece by piece to demonstrate qubit states, operations, and measurement.</span></span>

<span data-ttu-id="575ef-156">**Información general:**  En el primer código que aparece a continuación, mostramos cómo trabajar con cúbits en Q#.</span><span class="sxs-lookup"><span data-stu-id="575ef-156">**Overview:**  In the first code below, we show you how to work with qubits in Q#.</span></span>  <span data-ttu-id="575ef-157">Introduciremos dos operaciones, `M` y `X`, que transforman el estado de un cúbit.</span><span class="sxs-lookup"><span data-stu-id="575ef-157">We’ll introduce two operations, `M` and `X` that transform the state of a qubit.</span></span> 

<span data-ttu-id="575ef-158">En este fragmento de código, se define una operación `Set` que toma como parámetro un cúbit y otro parámetro, `desired`, que representa el estado en el que queremos que esté el cúbit.</span><span class="sxs-lookup"><span data-stu-id="575ef-158">In this code snippet, an operation `Set` is defined that takes as a parameter a qubit and another parameter, `desired`, representing the state that we would like the qubit to be in.</span></span>  <span data-ttu-id="575ef-159">La operación `Set` toma una medida en el cúbit con la operación `M`.</span><span class="sxs-lookup"><span data-stu-id="575ef-159">The operation `Set` performs a measurement on the qubit using the operation `M`.</span></span>  <span data-ttu-id="575ef-160">En Q#, la medida de un cúbit siempre devuelve `Zero` o `One`.</span><span class="sxs-lookup"><span data-stu-id="575ef-160">In Q#, a qubit measurement always returns either  `Zero` or `One`.</span></span>  <span data-ttu-id="575ef-161">Si la medida devuelve un valor distinto del deseado, Set "invierte" el cúbit; es decir, ejecuta una operación `X` que cambia el estado del cúbit a un nuevo estado en el que las probabilidades de que una medida devuelva `Zero` y `One` se invierten.</span><span class="sxs-lookup"><span data-stu-id="575ef-161">If the measurement returns a value not equal to a desired value, Set “flips” the qubit; that is, it executes an `X` operation, which changes the qubit state to a new state in which the probabilities of a measurement returning `Zero` and `One` are reversed.</span></span>  <span data-ttu-id="575ef-162">Para mostrar el efecto de la operación `Set`, se agrega una operación `TestBellState`.</span><span class="sxs-lookup"><span data-stu-id="575ef-162">To demonstrate the effect of the `Set` operation, a `TestBellState` operation is then added.</span></span>  <span data-ttu-id="575ef-163">Esta operación toma como entrada un `Zero` o `One`, llama a la operación `Set` un número determinado de veces con esa entrada y cuenta el número de veces que la medida del cúbit devolvió `Zero` y el número de veces que se devolvió `One`.</span><span class="sxs-lookup"><span data-stu-id="575ef-163">This operation takes as input a `Zero` or `One`, and calls the `Set` operation some number of times with that input, and counts the number of times that `Zero` was returned from the measurement of the qubit and the number of times that `One` was returned.</span></span> <span data-ttu-id="575ef-164">Por supuesto, en esta primera simulación de la operación `TestBellState` esperamos que la salida muestre que todas las medidas de un cúbit establecidas con `Zero` como entrada del parámetro devolverán `Zero`, y todas las medidas de un cúbit establecidas con `One` como entrada del parámetro devolverán `One`.</span><span class="sxs-lookup"><span data-stu-id="575ef-164">Of course, in this first simulation of the `TestBellState` operation, we expect that the output will show that all measurements of the qubit set with `Zero` as the parameter input will return `Zero`, and all measurements of a qubit set with `One` as the parameter input will return `One`.</span></span>  <span data-ttu-id="575ef-165">Más adelante, agregaremos código a `TestBellState` para demostrar la superposición y el entrelazamiento.</span><span class="sxs-lookup"><span data-stu-id="575ef-165">Further on, we’ll add code to `TestBellState` to demonstrating superposition and entanglement.</span></span>


### <a name="q-operation-code"></a><span data-ttu-id="575ef-166">Código de operación de Q#</span><span class="sxs-lookup"><span data-stu-id="575ef-166">Q# operation code</span></span>

1. <span data-ttu-id="575ef-167">Reemplace el contenido del archivo Bell.qs con el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="575ef-167">Replace the contents of the Bell.qs file with the following code:</span></span>

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

    <span data-ttu-id="575ef-168">Ahora se puede llamar a esta operación para establecer un cúbit en un estado clásico, ya sea devolviendo `Zero` el 100 % del tiempo o devolviendo `One` el 100 % del tiempo.</span><span class="sxs-lookup"><span data-stu-id="575ef-168">This operation may now be called to set a qubit to a classical state, either returning `Zero` 100% of the time or returning `One` 100% of the time.</span></span>  <span data-ttu-id="575ef-169">`Zero` y `One` son constantes que representan los únicos dos resultados posibles de la medida de un cúbit.</span><span class="sxs-lookup"><span data-stu-id="575ef-169">`Zero` and `One` are constants that represent the only two possible results of a measurement of a qubit.</span></span>

    <span data-ttu-id="575ef-170">La operación `Set` mide el cúbit.</span><span class="sxs-lookup"><span data-stu-id="575ef-170">The operation `Set` measures the qubit.</span></span>
    <span data-ttu-id="575ef-171">Si el cúbit está en el estado que queremos, `Set` lo deja así; de lo contrario, al ejecutar la operación `X`, cambiamos el estado del cúbit al estado deseado.</span><span class="sxs-lookup"><span data-stu-id="575ef-171">If the qubit is in the state we want, `Set` leaves it alone; otherwise, by executing the `X` operation, we change the qubit state to the desired state.</span></span>

### <a name="about-q-operations"></a><span data-ttu-id="575ef-172">Acerca de las operaciones de Q#</span><span class="sxs-lookup"><span data-stu-id="575ef-172">About Q# operations</span></span>

<span data-ttu-id="575ef-173">Una operación Q# es una subrutina cuántica.</span><span class="sxs-lookup"><span data-stu-id="575ef-173">A Q# operation is a quantum subroutine.</span></span> <span data-ttu-id="575ef-174">Es decir, es una rutina invocable que contiene operaciones cuánticas.</span><span class="sxs-lookup"><span data-stu-id="575ef-174">That is, it is a callable routine that contains quantum operations.</span></span>

<span data-ttu-id="575ef-175">Los argumentos de una operación se especifican como una tupla, entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="575ef-175">The arguments to an operation are specified as a tuple, within parentheses.</span></span>

<span data-ttu-id="575ef-176">El tipo de valor devuelto de la operación se especifica después de un signo de dos puntos.</span><span class="sxs-lookup"><span data-stu-id="575ef-176">The return type of the operation is specified after a colon.</span></span> <span data-ttu-id="575ef-177">En este caso, la operación de `Set` no devuelve ningún valor, por lo que se marca como retorno `Unit`.</span><span class="sxs-lookup"><span data-stu-id="575ef-177">In this case, the `Set` operation has no return, so it is marked as returning `Unit`.</span></span> <span data-ttu-id="575ef-178">Este es el equivalente de Q# de `unit` en F#, que es aproximadamente análogo a `void` en C#, y una tupla vacía (`Tuple[()]`) en Python.</span><span class="sxs-lookup"><span data-stu-id="575ef-178">This is the Q# equivalent of `unit` in F#, which is roughly analogous to `void` in C#, and an empty tuple (`Tuple[()]`) in Python.</span></span>

<span data-ttu-id="575ef-179">Ha usado dos operaciones cuánticas en la primera operación de Q#:</span><span class="sxs-lookup"><span data-stu-id="575ef-179">You have used two quantum operations in your first Q# operation:</span></span>

* <span data-ttu-id="575ef-180">La operación [M](xref:microsoft.quantum.intrinsic.m), que mide el estado del cúbit.</span><span class="sxs-lookup"><span data-stu-id="575ef-180">The [M](xref:microsoft.quantum.intrinsic.m) operation, which measures the state of the qubit</span></span>
* <span data-ttu-id="575ef-181">La operación [x](xref:microsoft.quantum.intrinsic.x), que invierte el estado de un cúbit.</span><span class="sxs-lookup"><span data-stu-id="575ef-181">The [X](xref:microsoft.quantum.intrinsic.x) operation, which flips the state of a qubit</span></span>

<span data-ttu-id="575ef-182">Una operación cuántica transforma el estado de un cúbit.</span><span class="sxs-lookup"><span data-stu-id="575ef-182">A quantum operation transforms the state of a qubit.</span></span> <span data-ttu-id="575ef-183">Algunos usuarios hablan de puertas cuánticas en lugar de operaciones, por analogía con las puertas lógicas clásicas.</span><span class="sxs-lookup"><span data-stu-id="575ef-183">Sometime people talk about quantum gates instead of operations, in analogy to classical logic gates.</span></span> <span data-ttu-id="575ef-184">Esto tiene su origen en los primeros tiempos de la computación cuántica, cuando los algoritmos eran una simple construcción teórica y se visualizaban como diagramas, de forma similar a los diagramas de circuitos de la computación clásica.</span><span class="sxs-lookup"><span data-stu-id="575ef-184">This is rooted in the early days of quantum computing when algorithms were merely a theoretical construct and visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>

### <a name="add-q-test-code"></a><span data-ttu-id="575ef-185">Agregar código de prueba de Q#</span><span class="sxs-lookup"><span data-stu-id="575ef-185">Add Q# test code</span></span>

1. <span data-ttu-id="575ef-186">Agregue la siguiente operación al archivo `Bell.qs`, dentro del espacio de nombres, después del final de la operación de `Set`:</span><span class="sxs-lookup"><span data-stu-id="575ef-186">Add the following operation to the `Bell.qs` file, inside the namespace, after the end of the `Set` operation:</span></span>

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

    <span data-ttu-id="575ef-187">Esta operación (`TestBellState`) creará un bucle para `count` iteraciones, establecerá un valor de `initial` especificado en cúbits y, a continuación, medirá (`M`) el resultado.</span><span class="sxs-lookup"><span data-stu-id="575ef-187">This operation (`TestBellState`) will loop for `count` iterations, set a specified `initial` value on a qubit and then measure (`M`) the result.</span></span> <span data-ttu-id="575ef-188">Recopilará estadísticas sobre cuántos ceros y unos se han medido y los devolverá al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="575ef-188">It will gather statistics on how many zeros and ones we've measured and return them to the caller.</span></span> <span data-ttu-id="575ef-189">Realiza otra operación necesaria.</span><span class="sxs-lookup"><span data-stu-id="575ef-189">It performs one other necessary operation.</span></span> <span data-ttu-id="575ef-190">Restablece el cúbit a un estado conocido (`Zero`) antes de devolverlo, lo que permite que otros usuarios asignen este cúbit en un estado conocido.</span><span class="sxs-lookup"><span data-stu-id="575ef-190">It resets the qubit to a known state (`Zero`) before returning it allowing others to allocate this qubit in a known state.</span></span> <span data-ttu-id="575ef-191">Esto es necesario para la instrucción `using`.</span><span class="sxs-lookup"><span data-stu-id="575ef-191">This is required by the `using` statement.</span></span>

### <a name="about-variables-in-q"></a><span data-ttu-id="575ef-192">Acerca de las variables en Q#</span><span class="sxs-lookup"><span data-stu-id="575ef-192">About variables in Q#</span></span>

<span data-ttu-id="575ef-193">De forma predeterminada, las variables en Q# son inmutables; su valor no se puede cambiar una vez que se enlazaron.</span><span class="sxs-lookup"><span data-stu-id="575ef-193">By default, variables in Q# are immutable; their value may not be changed after they are bound.</span></span> <span data-ttu-id="575ef-194">La palabra clave `let` se utiliza para indicar el enlace de una variable inmutable.</span><span class="sxs-lookup"><span data-stu-id="575ef-194">The `let` keyword is used to indicate the binding of an immutable variable.</span></span> <span data-ttu-id="575ef-195">Los argumentos de la operación son siempre inmutables.</span><span class="sxs-lookup"><span data-stu-id="575ef-195">Operation arguments are always immutable.</span></span>

<span data-ttu-id="575ef-196">Si necesita una variable cuyo valor puede cambiar, como `numOnes` en el ejemplo, puede declarar la variable con la palabra clave `mutable`.</span><span class="sxs-lookup"><span data-stu-id="575ef-196">If you need a variable whose value can change, such as `numOnes` in the example, you can declare the variable with the `mutable` keyword.</span></span> <span data-ttu-id="575ef-197">Se puede cambiar el valor de una variable mutable mediante una instrucción `set`.</span><span class="sxs-lookup"><span data-stu-id="575ef-197">A mutable variable's value may be changed using a `set` statement.</span></span>

<span data-ttu-id="575ef-198">En ambos casos, el compilador deduce el tipo de una variable.</span><span class="sxs-lookup"><span data-stu-id="575ef-198">In both cases, the type of a variable is inferred by the compiler.</span></span> <span data-ttu-id="575ef-199">Para las variables, Q# no requiere ninguna anotación de tipo.</span><span class="sxs-lookup"><span data-stu-id="575ef-199">Q# doesn't require any type annotations for variables.</span></span>

### <a name="about-using-statements-in-q"></a><span data-ttu-id="575ef-200">Acerca de las instrucciones `using` en Q#</span><span class="sxs-lookup"><span data-stu-id="575ef-200">About `using` statements in Q#</span></span>

<span data-ttu-id="575ef-201">La instrucción `using` también es especial para Q#.</span><span class="sxs-lookup"><span data-stu-id="575ef-201">The `using` statement is also special to Q#.</span></span> <span data-ttu-id="575ef-202">Se usa para asignar cúbits para su uso en un bloque de código.</span><span class="sxs-lookup"><span data-stu-id="575ef-202">It is used to allocate qubits for use in a block of code.</span></span> <span data-ttu-id="575ef-203">En Q#, todos los cúbits se asignan y liberan dinámicamente, en lugar de ser recursos fijos que están disponibles para toda la duración de un algoritmo complejo.</span><span class="sxs-lookup"><span data-stu-id="575ef-203">In Q#, all qubits are dynamically allocated and released, rather than being fixed resources that are there for the entire lifetime of a complex algorithm.</span></span> <span data-ttu-id="575ef-204">Una instrucción `using` asigna un conjunto de cúbits al principio y libera esos cúbits al final del bloque.</span><span class="sxs-lookup"><span data-stu-id="575ef-204">A `using` statement allocates a set of qubits at the start, and releases those qubits at the end of the block.</span></span>

## <a name="create-the-host-application-code"></a><span data-ttu-id="575ef-205">Cree el código de aplicación host</span><span class="sxs-lookup"><span data-stu-id="575ef-205">Create the host application code</span></span>

#### <a name="python"></a>[<span data-ttu-id="575ef-206">Python</span><span class="sxs-lookup"><span data-stu-id="575ef-206">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="575ef-207">Abra el archivo `host.py` y agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="575ef-207">Open the `host.py` file and add the following code:</span></span>

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

#### <a name="c"></a>[<span data-ttu-id="575ef-208">C#</span><span class="sxs-lookup"><span data-stu-id="575ef-208">C#</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="575ef-209">Reemplace el contenido del archivo `Driver.cs` por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="575ef-209">Replace the contents of the `Driver.cs` file with the following code:</span></span>

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

### <a name="about-the-host-application-code"></a><span data-ttu-id="575ef-210">Sobre el código de aplicación host</span><span class="sxs-lookup"><span data-stu-id="575ef-210">About the host application code</span></span>

#### <a name="python"></a>[<span data-ttu-id="575ef-211">Python</span><span class="sxs-lookup"><span data-stu-id="575ef-211">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="575ef-212">La aplicación host de Python consta de tres partes:</span><span class="sxs-lookup"><span data-stu-id="575ef-212">The Python host application has three parts:</span></span>

* <span data-ttu-id="575ef-213">Calcule los argumentos necesarios para el algoritmo cuántico.</span><span class="sxs-lookup"><span data-stu-id="575ef-213">Compute any arguments required for the quantum algorithm.</span></span> <span data-ttu-id="575ef-214">En el ejemplo, `count` se fija en 1000 y `initial` es el valor inicial del cúbit.</span><span class="sxs-lookup"><span data-stu-id="575ef-214">In the example, `count` is fixed at a 1000 and `initial` is the initial value of the qubit.</span></span>
* <span data-ttu-id="575ef-215">Ejecute el algoritmo cuántico llamando al método `simulate()` de la operación Q# importada.</span><span class="sxs-lookup"><span data-stu-id="575ef-215">Run the quantum algorithm by calling the `simulate()` method of the imported Q# operation.</span></span>
* <span data-ttu-id="575ef-216">Procesamiento del resultado de la operación.</span><span class="sxs-lookup"><span data-stu-id="575ef-216">Process the result of the operation.</span></span> <span data-ttu-id="575ef-217">En el ejemplo, `res` recibe el resultado de la operación.</span><span class="sxs-lookup"><span data-stu-id="575ef-217">In the example, `res` receives the result of the operation.</span></span> <span data-ttu-id="575ef-218">Aquí, el resultado es una tupla del número de ceros (`num_zeros`) y el número de unos (`num_ones`) que el simulador mide.</span><span class="sxs-lookup"><span data-stu-id="575ef-218">Here the result is a tuple of the number of zeros (`num_zeros`) and number of ones (`num_ones`) measured by the simulator.</span></span> <span data-ttu-id="575ef-219">Deconstruimos la tupla para obtener los dos campos e imprimir los resultados.</span><span class="sxs-lookup"><span data-stu-id="575ef-219">We deconstruct the tuple to get the two fields, and print the results.</span></span>

#### <a name="c"></a>[<span data-ttu-id="575ef-220">C#</span><span class="sxs-lookup"><span data-stu-id="575ef-220">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="575ef-221">La aplicación host de C# tiene cuatro partes:</span><span class="sxs-lookup"><span data-stu-id="575ef-221">The C# host application has four parts:</span></span>

* <span data-ttu-id="575ef-222">Construya un simulador cuántico.</span><span class="sxs-lookup"><span data-stu-id="575ef-222">Construct a quantum simulator.</span></span> <span data-ttu-id="575ef-223">En el ejemplo, `qsim` es el simulador.</span><span class="sxs-lookup"><span data-stu-id="575ef-223">In the example, `qsim` is the simulator.</span></span>
* <span data-ttu-id="575ef-224">Calcule los argumentos necesarios para el algoritmo cuántico.</span><span class="sxs-lookup"><span data-stu-id="575ef-224">Compute any arguments required for the quantum algorithm.</span></span> <span data-ttu-id="575ef-225">En el ejemplo, `count` se fija en 1000 y `initial` es el valor inicial del cúbit.</span><span class="sxs-lookup"><span data-stu-id="575ef-225">In the example, `count` is fixed at a 1000 and `initial` is the initial value of the qubit.</span></span>
* <span data-ttu-id="575ef-226">Ejecute el algoritmo cuántico.</span><span class="sxs-lookup"><span data-stu-id="575ef-226">Run the quantum algorithm.</span></span> <span data-ttu-id="575ef-227">Cada operación de Q# genera una clase C# con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="575ef-227">Each Q# operation generates a C# class with the same name.</span></span> <span data-ttu-id="575ef-228">Esta clase tiene un método `Run` que ejecuta la operación **de forma asincrónica**.</span><span class="sxs-lookup"><span data-stu-id="575ef-228">This class has a `Run` method that **asynchronously** executes the operation.</span></span> <span data-ttu-id="575ef-229">La ejecución es asincrónica debido a que la ejecución en el hardware real será asincrónica.</span><span class="sxs-lookup"><span data-stu-id="575ef-229">The execution is asynchronous because execution on actual hardware will be asynchronous.</span></span> <span data-ttu-id="575ef-230">Dado que el método `Run` es asincrónico, se captura la propiedad `Result`. Esto bloquea la ejecución hasta que la tarea se completa y devuelve el resultado de forma sincrónicamente.</span><span class="sxs-lookup"><span data-stu-id="575ef-230">Because the `Run` method is asynchronous, we fetch the `Result` property; this blocks execution until the task completes and returns the result synchronously.</span></span>
* <span data-ttu-id="575ef-231">Procesamiento del resultado de la operación.</span><span class="sxs-lookup"><span data-stu-id="575ef-231">Process the result of the operation.</span></span> <span data-ttu-id="575ef-232">En el ejemplo, `res` recibe el resultado de la operación.</span><span class="sxs-lookup"><span data-stu-id="575ef-232">In the example, `res` receives the result of the operation.</span></span> <span data-ttu-id="575ef-233">Aquí, el resultado es una tupla del número de ceros (`numZeros`) y el número de unos (`numOnes`) que el simulador mide.</span><span class="sxs-lookup"><span data-stu-id="575ef-233">Here the result is a tuple of the number of zeros (`numZeros`) and number of ones (`numOnes`) measured by the simulator.</span></span> <span data-ttu-id="575ef-234">Esto se devuelve como ValueTuple en C#.</span><span class="sxs-lookup"><span data-stu-id="575ef-234">This is returned as a ValueTuple in C#.</span></span> <span data-ttu-id="575ef-235">Deconstruimos la tupla para obtener los dos campos, imprimir los resultados y esperar una keypress.</span><span class="sxs-lookup"><span data-stu-id="575ef-235">We deconstruct the tuple to get the two fields, print the results, and wait for a keypress.</span></span>

#### [](#tab/tabid-vs2019)

* * *

## <a name="build-and-run"></a><span data-ttu-id="575ef-236">Compilación y ejecución</span><span class="sxs-lookup"><span data-stu-id="575ef-236">Build and run</span></span>

#### <a name="python"></a>[<span data-ttu-id="575ef-237">Python</span><span class="sxs-lookup"><span data-stu-id="575ef-237">Python</span></span>](#tab/tabid-python)

1. <span data-ttu-id="575ef-238">Ejecute el siguiente comando en su terminal:</span><span class="sxs-lookup"><span data-stu-id="575ef-238">Run the following command at your terminal:</span></span>

    ```
    python host.py
    ```

    <span data-ttu-id="575ef-239">Este comando ejecuta la aplicación host, que simula la operación Q#.</span><span class="sxs-lookup"><span data-stu-id="575ef-239">This command runs the host application, which simulates the Q# operation.</span></span>

<span data-ttu-id="575ef-240">Los resultados deben ser:</span><span class="sxs-lookup"><span data-stu-id="575ef-240">The results should be:</span></span>

```Output
Init:0    0s=1000 1s=0   
Init:1    0s=0    1s=1000
```

#### <a name="command-line--visual-studio-code"></a>[<span data-ttu-id="575ef-241">Línea de comandos/Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="575ef-241">Command Line / Visual Studio Code</span></span>](#tab/tabid-csharp)

1. <span data-ttu-id="575ef-242">Ejecute lo siguiente en su terminal:</span><span class="sxs-lookup"><span data-stu-id="575ef-242">Run the following at your terminal:</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="575ef-243">Este comando descargará automáticamente todos los paquetes necesarios, compilará la aplicación y, después, la ejecutará en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="575ef-243">This command will automatically download all required packages, build the application, then run it at the command line.</span></span>

1. <span data-ttu-id="575ef-244">De forma alternativa, presione **F1** para abrir la paleta de comandos y seleccione **Depuración: Iniciar sin depurar.**</span><span class="sxs-lookup"><span data-stu-id="575ef-244">Alternatively, press **F1** to open the Command Palette and select **Debug: Start Without Debugging.**</span></span>
<span data-ttu-id="575ef-245">Es posible que se le pida que cree un nuevo archivo ``launch.json`` que describa cómo iniciar el programa.</span><span class="sxs-lookup"><span data-stu-id="575ef-245">You may be prompted to create a new ``launch.json`` file describing how to start the program.</span></span>
<span data-ttu-id="575ef-246">El ``launch.json`` predeterminado debe funcionar bien en la mayoría de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="575ef-246">The default ``launch.json`` should work well for most applications.</span></span>

<span data-ttu-id="575ef-247">Los resultados deben ser:</span><span class="sxs-lookup"><span data-stu-id="575ef-247">The results should be:</span></span>

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

#### <a name="visual-studio"></a>[<span data-ttu-id="575ef-248">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="575ef-248">Visual Studio</span></span>](#tab/tabid-vs2019)

1. <span data-ttu-id="575ef-249">Solo presione `F5` y el programa debe compilarse y ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="575ef-249">Just hit `F5`, and your program should build and run!</span></span>

<span data-ttu-id="575ef-250">Los resultados deben ser:</span><span class="sxs-lookup"><span data-stu-id="575ef-250">The results should be:</span></span>

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

<span data-ttu-id="575ef-251">El programa se cerrará después de presionar una tecla.</span><span class="sxs-lookup"><span data-stu-id="575ef-251">The program will exit after you press a key.</span></span>

* * *

## <a name="prepare-superposition"></a><span data-ttu-id="575ef-252">Preparar la superposición</span><span class="sxs-lookup"><span data-stu-id="575ef-252">Prepare superposition</span></span>

<span data-ttu-id="575ef-253">**Introducción** Ahora veremos cómo expresa Q# las maneras de colocar los cúbits en superposición.</span><span class="sxs-lookup"><span data-stu-id="575ef-253">**Overview** Now let’s look at how Q# expresses ways to put qubits in superposition.</span></span>  <span data-ttu-id="575ef-254">Recuerde que el estado de un cúbit puede ser una superposición de 0 y 1.</span><span class="sxs-lookup"><span data-stu-id="575ef-254">Recall that the state of a qubit can be in a superposition of 0 and 1.</span></span>  <span data-ttu-id="575ef-255">Usaremos la operación `Hadamard` para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="575ef-255">We’ll use the `Hadamard` operation to accomplish this.</span></span> <span data-ttu-id="575ef-256">Si el cúbit está en cualquiera de los estados clásicos (al medir devuelve `Zero` siempre o `One` siempre), las operaciones `Hadamard` o `H` pondrán el cúbit en un estado tal que al medirlo, devolverá `Zero` el 50 % del tiempo y devolverá `One` el otro 50 % del tiempo.</span><span class="sxs-lookup"><span data-stu-id="575ef-256">If the qubit is in either of the classical states (where a measurement returns `Zero` always or `One` always), then the `Hadamard` or `H` operation will put the qubit in a state where a measurement of the qubit will return `Zero` 50% of the time and return `One` 50% of the time.</span></span>  <span data-ttu-id="575ef-257">Conceptualmente, el cúbit se puede considerar a medio camino entre `Zero` y `One`.</span><span class="sxs-lookup"><span data-stu-id="575ef-257">Conceputually, the qubit can be thought of as halfway between the `Zero` and `One`.</span></span>  <span data-ttu-id="575ef-258">Ahora, cuando simulemos la operación `TestBellState`, veremos que los resultados devolverán aproximadamente un número igual de `Zero` y `One` después de medir.</span><span class="sxs-lookup"><span data-stu-id="575ef-258">Now, when we simulate the `TestBellState` operation, we will see the results will return roughly an equal number of `Zero` and `One` after measurement.</span></span>  

<span data-ttu-id="575ef-259">En primer lugar, intentaremos invertir el cúbit (si el cúbit está en estado `Zero` se invertirá a `One` y viceversa).</span><span class="sxs-lookup"><span data-stu-id="575ef-259">First we'll just try to flip the qubit (if the qubit is in `Zero` state will flip to `One` and vice versa).</span></span> <span data-ttu-id="575ef-260">Esto se logra con una operación `X` antes de medirlo en `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="575ef-260">This is accomplished by performing an `X` operation before we measure it in `TestBellState`:</span></span>

```qsharp
X(qubit);
let res = M(qubit);
```

<span data-ttu-id="575ef-261">Ahora se invierten los resultados (después de presionar `F5`):</span><span class="sxs-lookup"><span data-stu-id="575ef-261">Now the results (after pressing `F5`) are reversed:</span></span>

```Output
Init:Zero 0s=0    1s=1000
Init:One  0s=1000 1s=0
```

<span data-ttu-id="575ef-262">Sin embargo, todo lo que hemos visto hasta ahora es clásico.</span><span class="sxs-lookup"><span data-stu-id="575ef-262">However, everything we've seen so far is classical.</span></span> <span data-ttu-id="575ef-263">Ahora obtengamos un resultado cuántico.</span><span class="sxs-lookup"><span data-stu-id="575ef-263">Let's get a quantum result.</span></span> <span data-ttu-id="575ef-264">Lo único que tenemos que hacer es reemplazar la operación `X` de la ejecución anterior por una operación `H` o Hadamard.</span><span class="sxs-lookup"><span data-stu-id="575ef-264">All we need to do is replace the `X` operation in the previous run with an `H` or Hadamard operation.</span></span> <span data-ttu-id="575ef-265">En lugar de voltear totalmente el cúbit de 0 a 1, solo lo voltearemos a la mitad.</span><span class="sxs-lookup"><span data-stu-id="575ef-265">Instead of flipping the qubit all the way from 0 to 1, we will only flip it halfway.</span></span> <span data-ttu-id="575ef-266">Las líneas reemplazadas en `TestBellState` ahora tienen el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="575ef-266">The replaced lines in `TestBellState` now look like:</span></span>

```qsharp
H(qubit);
let res = M(qubit);
```

<span data-ttu-id="575ef-267">Ahora tenemos resultados más interesantes:</span><span class="sxs-lookup"><span data-stu-id="575ef-267">Now the results get more interesting:</span></span>

```Output
Init:Zero 0s=484  1s=516
Init:One  0s=522  1s=478
```

<span data-ttu-id="575ef-268">Cada vez que medimos, solicitamos un valor clásico, pero el cúbit se encuentra a medio camino entre 0 y 1, por lo que obtenemos (estadísticamente) 0 la mitad del tiempo y 1 la otra mitad del tiempo.</span><span class="sxs-lookup"><span data-stu-id="575ef-268">Every time we measure, we ask for a classical value, but the qubit is halfway between 0 and 1, so we get (statistically) 0 half the time and 1 half the time.</span></span> <span data-ttu-id="575ef-269">Esto se conoce como __superposición__ y nos proporciona nuestra primera vista real en un estado cuántico.</span><span class="sxs-lookup"><span data-stu-id="575ef-269">This is known as __superposition__ and gives us our first real view into a quantum state.</span></span>

## <a name="prepare-entanglement"></a><span data-ttu-id="575ef-270">Preparación del entrelazamiento</span><span class="sxs-lookup"><span data-stu-id="575ef-270">Prepare entanglement</span></span>

<span data-ttu-id="575ef-271">**Información general:**  Ahora veamos cómo expresa Q# las maneras de entrelazar los cúbits.</span><span class="sxs-lookup"><span data-stu-id="575ef-271">**Overview:**  Now let’s look at how Q# expresses ways to entangle qubits.</span></span>  <span data-ttu-id="575ef-272">En primer lugar, establecemos el primer cúbit en el estado inicial y después usamos la operación `H` para ponerlo en superposición.</span><span class="sxs-lookup"><span data-stu-id="575ef-272">First, we set the first qubit to the initial state and then use the `H` operation to put it into superposition.</span></span>  <span data-ttu-id="575ef-273">Luego, antes de medir el primer cúbit, usamos una nueva operación (`CNOT`), que significa Controlled-Not.</span><span class="sxs-lookup"><span data-stu-id="575ef-273">Then, before we measure the first qubit, we use a new operation (`CNOT`), which stands for Controlled-Not.</span></span>  <span data-ttu-id="575ef-274">El resultado de ejecutar esta operación en dos cúbits es la inversión del segundo cúbit si el primero es `One`.</span><span class="sxs-lookup"><span data-stu-id="575ef-274">The result of executing this operation on two qubits is to flip the second qubit if the first qubit is `One`.</span></span>  <span data-ttu-id="575ef-275">Ahora, los dos cúbits están entrelazados.</span><span class="sxs-lookup"><span data-stu-id="575ef-275">Now, the two qubits are entangled.</span></span>  <span data-ttu-id="575ef-276">Nuestras estadísticas del primer cúbit no han cambiado (50-50 de probabilidades de `Zero` o `One` después de medir) pero ahora, cuando medimos el segundo cúbit, es __siempre__ igual que lo que se midió para el primer cúbit.</span><span class="sxs-lookup"><span data-stu-id="575ef-276">Our statistics for the first qubit haven't changed (50-50 chance of a `Zero` or a `One` after measurement), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit.</span></span> <span data-ttu-id="575ef-277">Nuestro `CNOT` ha hecho el entrelazamiento de los dos cúbits, de modo que lo que le suceda a uno, le sucede al otro.</span><span class="sxs-lookup"><span data-stu-id="575ef-277">Our `CNOT` has entangled the two qubits, so that whatever happens to one of them, happens to the other.</span></span> <span data-ttu-id="575ef-278">Si invirtió las medidas (hizo la del segundo cúbit antes del primero), sucedería lo mismo.</span><span class="sxs-lookup"><span data-stu-id="575ef-278">If you reversed the measurements (did the second qubit before the first), the same thing would happen.</span></span> <span data-ttu-id="575ef-279">La primera medida sería aleatoria y la segunda sería en el paso de bloqueo con lo que se haya descubierto en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="575ef-279">The first measurement would be random and the second would be in lock step with whatever was discovered for the first.</span></span>

<span data-ttu-id="575ef-280">Lo primero que debemos hacer es asignar 2 cúbits en lugar de uno en `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="575ef-280">The first thing we'll need to do is allocate 2 qubits instead of one in `TestBellState`:</span></span>

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

<span data-ttu-id="575ef-281">Esto nos permitirá agregar una nueva operación (`CNOT`) antes de medir (`M`) en `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="575ef-281">This will allow us to add a new operation (`CNOT`) before we measure  (`M`) in `TestBellState`:</span></span>

```qsharp
Set(initial, q0);
Set(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

<span data-ttu-id="575ef-282">Hemos agregado otra operación `Set` para inicializar el primer cúbit para asegurarnos de que siempre está en `Zero` cuando se inicia.</span><span class="sxs-lookup"><span data-stu-id="575ef-282">We've added another `Set` operation to initialize the first qubit to make sure that it's always in the `Zero` state when we start.</span></span>

<span data-ttu-id="575ef-283">También necesitamos restablecer el segundo cúbit antes de liberarlo.</span><span class="sxs-lookup"><span data-stu-id="575ef-283">We also need to reset the second qubit before releasing it.</span></span>

```qsharp
Set(Zero, q0);
Set(Zero, q1);
```

<span data-ttu-id="575ef-284">La rutina completa se ve ahora así:</span><span class="sxs-lookup"><span data-stu-id="575ef-284">The full routine now looks like this:</span></span>

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

<span data-ttu-id="575ef-285">Si la ejecutamos, obtendremos exactamente el mismo resultado 50-50 que obtuvimos antes.</span><span class="sxs-lookup"><span data-stu-id="575ef-285">If we run this, we'll get exactly the same 50-50 result we got before.</span></span> <span data-ttu-id="575ef-286">Sin embargo, ahora nos interesa cómo reacciona el segundo cúbit al primero que se mide.</span><span class="sxs-lookup"><span data-stu-id="575ef-286">However, what we're interested in is how the second qubit reacts to the first being measured.</span></span> <span data-ttu-id="575ef-287">Agregaremos esta estadística con una nueva versión de la operación `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="575ef-287">We'll add this statistic with a new version of the `TestBellState` operation:</span></span>

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

<span data-ttu-id="575ef-288">El nuevo valor devuelto (`agree`) realiza un seguimiento de cada vez que la medida del primer cúbit coincide con la medida del segundo.</span><span class="sxs-lookup"><span data-stu-id="575ef-288">The new return value (`agree`) keeps track of every time the measurement from the first qubit matches the measurement of the second qubit.</span></span> <span data-ttu-id="575ef-289">También tenemos que actualizar la aplicación host, según corresponda:</span><span class="sxs-lookup"><span data-stu-id="575ef-289">We also have to update the host application accordingly:</span></span>

#### <a name="python"></a>[<span data-ttu-id="575ef-290">Python</span><span class="sxs-lookup"><span data-stu-id="575ef-290">Python</span></span>](#tab/tabid-python)

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

#### <a name="c"></a>[<span data-ttu-id="575ef-291">C#</span><span class="sxs-lookup"><span data-stu-id="575ef-291">C#</span></span>](#tab/tabid-csharp)

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

<span data-ttu-id="575ef-292">Ahora, cuando hacemos la ejecución, obtenemos algo muy asombroso:</span><span class="sxs-lookup"><span data-stu-id="575ef-292">Now when we run, we get something pretty amazing:</span></span>

```Output
Init:Zero 0s=499  1s=501  agree=1000
Init:One  0s=490  1s=510  agree=1000
```

<span data-ttu-id="575ef-293">Tal y como se indicó en la introducción, nuestras estadísticas del primer cúbit no han cambiado (50-50 de probabilidades de 0 o 1 después de medir) pero ahora, cuando medimos el segundo cúbit, es __siempre__ igual que lo que se midió para el primer cúbit, porque están entrelazados.</span><span class="sxs-lookup"><span data-stu-id="575ef-293">As stated in the overview, our statistics for the first qubit haven't changed (50-50 chance of a 0 or a 1), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit, because they are entangled!</span></span>

<span data-ttu-id="575ef-294">Enhorabuena, ha escrito su primer programa cuántico.</span><span class="sxs-lookup"><span data-stu-id="575ef-294">Congratulations, you've written your first quantum program!</span></span>

## <a name="next-steps"></a><span data-ttu-id="575ef-295">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="575ef-295">Next steps</span></span>

<span data-ttu-id="575ef-296">El tutorial sobre la [búsqueda de Grover](xref:microsoft.quantum.quickstarts.search) muestra cómo compilar y ejecutar una búsqueda de Grover, uno de los algoritmos de computación cuántica más populares, y es un buen ejemplo de un programa de Q# que se puede usar para resolver problemas reales con la computación cuántica.</span><span class="sxs-lookup"><span data-stu-id="575ef-296">The tutorial [Grover’s search](xref:microsoft.quantum.quickstarts.search) shows you how to build and run Grover search, one of the most popular quantum computing algorithms and offers a nice example of a Q# program that can be used to solve real problems with quantum computing.</span></span>  

<span data-ttu-id="575ef-297">En [Introducción al kit de desarrollo de Microsoft Quantum](xref:microsoft.quantum.welcome) se recomiendan más formas de aprender Q# y programación cuántica.</span><span class="sxs-lookup"><span data-stu-id="575ef-297">[Get Started with the Quantum Development Kit](xref:microsoft.quantum.welcome) recommends more ways to learn Q# and quantum programming.</span></span>
