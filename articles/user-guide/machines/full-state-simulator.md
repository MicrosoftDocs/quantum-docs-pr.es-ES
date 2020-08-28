---
title: 'Simulador de Quantum de estado completo: kit de desarrollo de Quantum'
description: Obtenga información sobre cómo ejecutar sus Q# programas en el Microsoft Quantum Development Kit simulador de estado completo.
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: a27cece9858d62814b9d80c47e61c5d7d3b8c885
ms.sourcegitcommit: 11bd357baeb6ab53a402882979e75964d0869b57
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2020
ms.locfileid: "88992230"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a><span data-ttu-id="90f07-103">Simulador de estado completo del kit de desarrollo de Quantum (QDK)</span><span class="sxs-lookup"><span data-stu-id="90f07-103">Quantum Development Kit (QDK) full state simulator</span></span>

<span data-ttu-id="90f07-104">El QDK proporciona un simulador de estado completo que simula una máquina Quantum en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="90f07-104">The QDK provides a full state simulator that simulates a quantum machine on your local computer.</span></span> <span data-ttu-id="90f07-105">Puede usar el simulador de estado completo para ejecutar y depurar algoritmos Quantum escritos en Q# , con un máximo de 30 qubits.</span><span class="sxs-lookup"><span data-stu-id="90f07-105">You can use the full state simulator to run and debug quantum algorithms written in Q#, utilizing up to 30 qubits.</span></span> <span data-ttu-id="90f07-106">El simulador de estado completo es similar al simulador de Quantum usado en la plataforma  [Liq $ UI | \rangle $](http://stationq.github.io/Liquid/) de Microsoft Research.</span><span class="sxs-lookup"><span data-stu-id="90f07-106">The full state simulator is similar to the quantum simulator used in the  [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) platform from Microsoft Research.</span></span>

## <a name="invoking-and-running-the-full-state-simulator"></a><span data-ttu-id="90f07-107">Invocar y ejecutar el simulador de estado completo</span><span class="sxs-lookup"><span data-stu-id="90f07-107">Invoking and running the full state simulator</span></span>

<span data-ttu-id="90f07-108">Expone el simulador de estado completo a través de la `QuantumSimulator` clase.</span><span class="sxs-lookup"><span data-stu-id="90f07-108">You expose the full state simulator via the `QuantumSimulator` class.</span></span> <span data-ttu-id="90f07-109">Para obtener más información, consulte [formas de ejecutar un Q# programa](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="90f07-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-simulator-from-c"></a><span data-ttu-id="90f07-110">Invocar el simulador de C #</span><span class="sxs-lookup"><span data-stu-id="90f07-110">Invoking the simulator from C#</span></span>

<span data-ttu-id="90f07-111">Cree una instancia de la `QuantumSimulator` clase y, a continuación, pásela al `Run` método de una operación Quantum, junto con los parámetros adicionales.</span><span class="sxs-lookup"><span data-stu-id="90f07-111">Create an instance of the `QuantumSimulator` class and then pass it to the `Run` method of a quantum operation, along with any additional parameters.</span></span>
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

<span data-ttu-id="90f07-112">Dado que la `QuantumSimulator` clase implementa la <xref:System.IDisposable> interfaz, debe llamar al `Dispose` método una vez que ya no necesita la instancia del simulador.</span><span class="sxs-lookup"><span data-stu-id="90f07-112">Because the `QuantumSimulator` class implements the <xref:System.IDisposable> interface, you must call the `Dispose` method once you do not need the instance of the simulator anymore.</span></span> <span data-ttu-id="90f07-113">La mejor manera de hacerlo es encapsular las operaciones y la declaración del simulador dentro de una instrucción [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) , que llama automáticamente al `Dispose` método.</span><span class="sxs-lookup"><span data-stu-id="90f07-113">The best way to do this is to wrap the simulator declaration and operations within a [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) statement, which automatically calls the `Dispose` method.</span></span>

### <a name="invoking-the-simulator-from-python"></a><span data-ttu-id="90f07-114">Invocar el simulador desde Python</span><span class="sxs-lookup"><span data-stu-id="90f07-114">Invoking the simulator from Python</span></span>

<span data-ttu-id="90f07-115">Use el método [Simulate ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) de la Q# biblioteca de Python con la Q# operación importada:</span><span class="sxs-lookup"><span data-stu-id="90f07-115">Use the [simulate()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Q# Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a><span data-ttu-id="90f07-116">Invocar el simulador desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="90f07-116">Invoking the simulator from the command line</span></span>

<span data-ttu-id="90f07-117">Al ejecutar un Q# programa desde la línea de comandos, el simulador de estado completo es el equipo de destino predeterminado.</span><span class="sxs-lookup"><span data-stu-id="90f07-117">When running a Q# program from the command line, the full state simulator is the default target machine.</span></span> <span data-ttu-id="90f07-118">Opcionalmente, puede usar el parámetro **--Simulator** (o **-s** Shortcut) para especificar el equipo de destino deseado.</span><span class="sxs-lookup"><span data-stu-id="90f07-118">Optionally, you can use the **--simulator** (or **-s** shortcut) parameter to specify the desired target machine.</span></span> <span data-ttu-id="90f07-119">Los dos comandos siguientes ejecutan un programa mediante el simulador de estado completo.</span><span class="sxs-lookup"><span data-stu-id="90f07-119">Both of the following commands run a program using the full state simulator.</span></span> 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a><span data-ttu-id="90f07-120">Invocación del simulador de cuadernos de Juptyer Notebook</span><span class="sxs-lookup"><span data-stu-id="90f07-120">Invoking the simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="90f07-121">Use la instrucción I Q# mágica [%simulate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) para ejecutar la Q# operación.</span><span class="sxs-lookup"><span data-stu-id="90f07-121">Use the IQ# magic command [%simulate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a><span data-ttu-id="90f07-122">Propagación del simulador</span><span class="sxs-lookup"><span data-stu-id="90f07-122">Seeding the simulator</span></span>

<span data-ttu-id="90f07-123">De forma predeterminada, el simulador de estado completo utiliza un generador de números aleatorios para simular la aleatoriedad de Quantum.</span><span class="sxs-lookup"><span data-stu-id="90f07-123">By default, the full state simulator uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="90f07-124">Con fines de prueba, a veces resulta útil tener resultados deterministas.</span><span class="sxs-lookup"><span data-stu-id="90f07-124">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="90f07-125">En un programa de C#, puede lograrlo proporcionando un valor de inicialización para el generador de números aleatorios en el `QuantumSimulator` constructor a través del `randomNumberGeneratorSeed` parámetro.</span><span class="sxs-lookup"><span data-stu-id="90f07-125">In a C# program, you can accomplish this by providing a seed for the random number generator in the `QuantumSimulator` constructor via the `randomNumberGeneratorSeed` parameter.</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a><span data-ttu-id="90f07-126">Configuración de subprocesos</span><span class="sxs-lookup"><span data-stu-id="90f07-126">Configuring threads</span></span>

<span data-ttu-id="90f07-127">El simulador de estado completo utiliza [OpenMP](http://www.openmp.org/) para paralelizar el álgebra lineal requerido.</span><span class="sxs-lookup"><span data-stu-id="90f07-127">The full state simulator uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="90f07-128">De forma predeterminada, OpenMP usa todos los subprocesos de hardware disponibles, lo que significa que los programas con un número pequeño de qubits suelen ejecutarse lentamente porque la coordinación necesaria Dwarfs el trabajo real.</span><span class="sxs-lookup"><span data-stu-id="90f07-128">By default, OpenMP uses all available hardware threads, which means that programs with small numbers of qubits often runs slowly because the coordination that is required dwarfs the actual work.</span></span> <span data-ttu-id="90f07-129">Puede corregir esto si establece la variable de entorno `OMP_NUM_THREADS` en un número pequeño.</span><span class="sxs-lookup"><span data-stu-id="90f07-129">You can fix this by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="90f07-130">Como regla general, configure un subproceso para un máximo de cuatro qubits y, a continuación, un subproceso adicional por qubit.</span><span class="sxs-lookup"><span data-stu-id="90f07-130">As a rule of thumb, configure one thread for up to four qubits, and then one additional thread per qubit.</span></span> <span data-ttu-id="90f07-131">Es posible que deba ajustar la variable según el algoritmo.</span><span class="sxs-lookup"><span data-stu-id="90f07-131">You might need to adjust the variable depending on your algorithm.</span></span>

## <a name="see-also"></a><span data-ttu-id="90f07-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="90f07-132">See also</span></span>

- [<span data-ttu-id="90f07-133">Estimador de recursos cuánticos</span><span class="sxs-lookup"><span data-stu-id="90f07-133">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="90f07-134">Simulador cuántico de Toffoli</span><span class="sxs-lookup"><span data-stu-id="90f07-134">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="90f07-135">Simulador de seguimiento de Quantum</span><span class="sxs-lookup"><span data-stu-id="90f07-135">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)