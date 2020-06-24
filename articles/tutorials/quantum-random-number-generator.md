---
title: Creación de un generador cuántico de números aleatorios
description: Cree un proyecto de Q# para crear un generador cuántico de números aleatorios con el fin de mostrar los conceptos cuánticos fundamentales tales como la superposición.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: 18e8975e513a87c0a67a6dbb5586cc7dab5a93fb
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275282"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="0bec4-103">Tutorial: Implementación de un generador cuántico de números aleatorios en Q\#</span><span class="sxs-lookup"><span data-stu-id="0bec4-103">Tutorial: Implement a Quantum Random Number Generator in Q\#</span></span>

<span data-ttu-id="0bec4-104">Un ejemplo sencillo de un algoritmo cuántico escrito en Q# es un generador cuántico de números aleatorios.</span><span class="sxs-lookup"><span data-stu-id="0bec4-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="0bec4-105">Este algoritmo aprovecha la naturaleza de la mecánica cuántica para generar un número aleatorio.</span><span class="sxs-lookup"><span data-stu-id="0bec4-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0bec4-106">Prerrequisitos</span><span class="sxs-lookup"><span data-stu-id="0bec4-106">Prerequisites</span></span>

- <span data-ttu-id="0bec4-107">[Kit de desarrollo de Microsoft Quantum](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="0bec4-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="0bec4-108">Cree un proyecto de Q# usando [Q# desde la línea de comandos](xref:microsoft.quantum.install.standalone) o con un [programa host de Python](xref:microsoft.quantum.install.python) o un [programa host de C#](xref:microsoft.quantum.install.cs).</span><span class="sxs-lookup"><span data-stu-id="0bec4-108">Create a Q# project for either [using Q# from the command line](xref:microsoft.quantum.install.standalone), or with a [Python host program](xref:microsoft.quantum.install.python) or [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="write-a-q-operation"></a><span data-ttu-id="0bec4-109">Escriba una operación de Q#</span><span class="sxs-lookup"><span data-stu-id="0bec4-109">Write a Q# operation</span></span>

### <a name="q-operation-code"></a><span data-ttu-id="0bec4-110">Código de operación de Q#</span><span class="sxs-lookup"><span data-stu-id="0bec4-110">Q# operation code</span></span>

1. <span data-ttu-id="0bec4-111">Reemplace el contenido del archivo Program.qs por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="0bec4-111">Replace the contents of the Program.qs file with the following code:</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

<span data-ttu-id="0bec4-112">Tal y como se mencionó en nuestro artículo [Descripción de la computación cuántica](xref:microsoft.quantum.overview.understanding), un cúbit es una unidad de información cuántica que puede estar en superposición.</span><span class="sxs-lookup"><span data-stu-id="0bec4-112">As mentioned in our [Understanding quantum computing](xref:microsoft.quantum.overview.understanding) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="0bec4-113">Cuando se mide, un cúbit solo puede ser 0 o 1.</span><span class="sxs-lookup"><span data-stu-id="0bec4-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="0bec4-114">Sin embargo, durante la ejecución, el estado del cúbit representa la probabilidad de leer un 0 o un 1 al tomar una medida.</span><span class="sxs-lookup"><span data-stu-id="0bec4-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="0bec4-115">Este estado probabilístico se conoce como superposición.</span><span class="sxs-lookup"><span data-stu-id="0bec4-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="0bec4-116">Podemos usar esta probabilidad para generar números aleatorios.</span><span class="sxs-lookup"><span data-stu-id="0bec4-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="0bec4-117">En nuestra operación de Q#, presentamos el tipo de datos `Qubit`, nativo de Q#.</span><span class="sxs-lookup"><span data-stu-id="0bec4-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="0bec4-118">Solo se puede asignar un `Qubit` con una instrucción `using`.</span><span class="sxs-lookup"><span data-stu-id="0bec4-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="0bec4-119">Cuando se asigna un cúbit, siempre está en el estado `Zero`.</span><span class="sxs-lookup"><span data-stu-id="0bec4-119">When it gets allocated, a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="0bec4-120">Con la operación `H`, podemos poner nuestro `Qubit` en superposición.</span><span class="sxs-lookup"><span data-stu-id="0bec4-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="0bec4-121">Para medir un cúbit y leer su valor, se usa la operación intrínseca `M`.</span><span class="sxs-lookup"><span data-stu-id="0bec4-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="0bec4-122">Al poner el `Qubit` en superposición y medirlo, el resultado será un valor diferente cada vez que se invoque el código.</span><span class="sxs-lookup"><span data-stu-id="0bec4-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span>

<span data-ttu-id="0bec4-123">Cuando se desasigna un `Qubit`, se debe volver a establecer explícitamente en el estado `Zero`; de lo contrario, el simulador notificará un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0bec4-123">When a `Qubit` is deallocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="0bec4-124">Una manera fácil de hacerlo es invocar a `Reset`.</span><span class="sxs-lookup"><span data-stu-id="0bec4-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="0bec4-125">Visualización del código con la esfera de Bloch</span><span class="sxs-lookup"><span data-stu-id="0bec4-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="0bec4-126">En la esfera Bloch, el polo norte representa el valor clásico **0** y el polo sur representa el valor clásico **1**.</span><span class="sxs-lookup"><span data-stu-id="0bec4-126">In the Bloch sphere, the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="0bec4-127">Cualquier superposición se puede representar mediante un punto en la esfera (representado con una flecha).</span><span class="sxs-lookup"><span data-stu-id="0bec4-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="0bec4-128">Cuanto más cerca esté el extremo de la flecha a un polo, mayor será la probabilidad de que el cúbit caiga en el valor clásico asignado a ese polo cuando se mida.</span><span class="sxs-lookup"><span data-stu-id="0bec4-128">The closer the end of the arrow to a pole the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="0bec4-129">Por ejemplo, el estado del cúbit representado por la flecha roja siguiente tiene una mayor probabilidad de dar el valor **0** si lo medimos.</span><span class="sxs-lookup"><span data-stu-id="0bec4-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

<span data-ttu-id="0bec4-130">Podemos usar esta representación para visualizar lo que está haciendo el código:</span><span class="sxs-lookup"><span data-stu-id="0bec4-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="0bec4-131">En primer lugar, empezamos con un cúbit inicializado en el estado **0** y aplicamos `H` para crear una superposición en la que las probabilidades de **0** y **1** sean las mismas.</span><span class="sxs-lookup"><span data-stu-id="0bec4-131">First we start with a qubit initialized in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">

* <span data-ttu-id="0bec4-132">A continuación, se mide el cúbit y se guarda el resultado:</span><span class="sxs-lookup"><span data-stu-id="0bec4-132">Then we measure the qubit and save the output:</span></span>

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

<span data-ttu-id="0bec4-133">Como el resultado de la medida es completamente aleatorio, hemos obtenido un bit aleatorio.</span><span class="sxs-lookup"><span data-stu-id="0bec4-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="0bec4-134">Podemos llamar a esta operación varias veces para crear enteros.</span><span class="sxs-lookup"><span data-stu-id="0bec4-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="0bec4-135">Por ejemplo, si llamamos a la operación tres veces para obtener tres bits aleatorios, podemos crear números de 3 bits aleatorios (es decir, un número aleatorio entre 0 y 7).</span><span class="sxs-lookup"><span data-stu-id="0bec4-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>


## <a name="creating-a-complete-random-number-generator"></a><span data-ttu-id="0bec4-136">Creación de un generador completo de números aleatorios</span><span class="sxs-lookup"><span data-stu-id="0bec4-136">Creating a complete random number generator</span></span>

<span data-ttu-id="0bec4-137">Ahora que tenemos una operación de Q# que genera bits aleatorios, podemos usarlo para crear un generador completo de números cuánticos aleatorios.</span><span class="sxs-lookup"><span data-stu-id="0bec4-137">Now that we have a Q# operation that generates random bits, we can use it to build a complete quantum random number generator.</span></span> <span data-ttu-id="0bec4-138">Podemos usar las aplicaciones de línea de comandos de Q# o usar un programa host.</span><span class="sxs-lookup"><span data-stu-id="0bec4-138">We can use the Q# command line applications or use a host program.</span></span>



### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a>[<span data-ttu-id="0bec4-139">Aplicaciones de línea de comandos de Q# con Visual Studio o Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="0bec4-139">Q# command line applications with Visual Studio or Visual Studio Code</span></span>](#tab/tabid-qsharp)

<span data-ttu-id="0bec4-140">Para crear la aplicación de línea de comandos de Q# completa, agregue el siguiente punto de entrada al programa de Q#:</span><span class="sxs-lookup"><span data-stu-id="0bec4-140">To create the full Q# command line application, add the following entry point to your Q# program:</span></span> 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

<span data-ttu-id="0bec4-141">El ejecutable ejecutará la operación o función marcada con el atributo `@EntryPoint()` en un simulador o una calculadora de recursos, dependiendo de la configuración del proyecto y de las opciones de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="0bec4-141">The executable will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

<span data-ttu-id="0bec4-142">En Visual Studio, solo tiene que presionar Ctrl+F5 para ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="0bec4-142">In Visual Studio, simply press Ctrl + F5 to execute the script.</span></span>

<span data-ttu-id="0bec4-143">En VS Code, escriba lo siguiente en el terminal para compilar el archivo Program.qs la primera vez:</span><span class="sxs-lookup"><span data-stu-id="0bec4-143">In VS Code, build the Program.qs the first time by typing the below in the terminal:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="0bec4-144">En las ejecuciones posteriores, no es necesario volver a compilarlo.</span><span class="sxs-lookup"><span data-stu-id="0bec4-144">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="0bec4-145">Para ejecutarlo, escriba el siguiente comando y presione Entrar:</span><span class="sxs-lookup"><span data-stu-id="0bec4-145">To run it, type the following command and press enter:</span></span>

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="0bec4-146">Python con Visual Studio Code o la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="0bec4-146">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

<span data-ttu-id="0bec4-147">Para ejecutar el nuevo programa de Q# desde Python, guarde el código siguiente como `host.py`:</span><span class="sxs-lookup"><span data-stu-id="0bec4-147">To run your new Q# program from Python, save the following code as `host.py`:</span></span>

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

<span data-ttu-id="0bec4-148">A continuación, puede ejecutar el programa host de Python desde la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="0bec4-148">You can then run your Python host program from the command line:</span></span>

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[<span data-ttu-id="0bec4-149">C# con Visual Studio Code o Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0bec4-149">C# with Visual Studio Code or Visual Studio</span></span>](#tab/tabid-csharp)

<span data-ttu-id="0bec4-150">Para ejecutar el nuevo programa de Q# desde C#, modifique `Driver.cs` para incluir el siguiente código de C#:</span><span class="sxs-lookup"><span data-stu-id="0bec4-150">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

<span data-ttu-id="0bec4-151">A continuación, puede ejecutar el programa host de C# desde la línea de comandos (en Visual Studio, presione F5):</span><span class="sxs-lookup"><span data-stu-id="0bec4-151">You can then run your C# host program from the command line (in Visual Studio you should press F5):</span></span>

```bash
$ dotnet run
The random number generated is 42
```

***
