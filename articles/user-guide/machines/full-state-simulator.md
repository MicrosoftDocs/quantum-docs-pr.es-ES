---
title: Simulador de estado completo
description: Obtenga información sobre cómo ejecutar los programas de preguntas y respuestas en el Microsoft Quantum Development Kit simulador de estado completo.
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: f73abbc4366b003e4b22366ed83ca9c897737307
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275645"
---
# <a name="quantum-development-kit-full-state-simulator"></a><span data-ttu-id="34012-103">Simulador de estado completo del kit de desarrollo de Quantum</span><span class="sxs-lookup"><span data-stu-id="34012-103">Quantum Development Kit Full State Simulator</span></span>

<span data-ttu-id="34012-104">El kit de desarrollo de Quantum proporciona un simulador de Quantum de estado completo similar a [Liq $ UI | \rangle $](http://stationq.github.io/Liquid/) de Microsoft Research.</span><span class="sxs-lookup"><span data-stu-id="34012-104">The Quantum Development Kit provides a full state quantum simulator similar to [LIQ$Ui|\rangle$](http://stationq.github.io/Liquid/) from Microsoft Research.</span></span>
<span data-ttu-id="34012-105">Este simulador se puede usar para ejecutar y depurar algoritmos Quantum escritos en Q # en el equipo.</span><span class="sxs-lookup"><span data-stu-id="34012-105">This simulator can be used to execute and debug quantum algorithms written in Q# on your computer.</span></span>

<span data-ttu-id="34012-106">Este simulador de Quantum se expone a través de la `QuantumSimulator` clase.</span><span class="sxs-lookup"><span data-stu-id="34012-106">This quantum simulator is exposed via the `QuantumSimulator` class.</span></span> <span data-ttu-id="34012-107">Para usar el simulador, solo tiene que crear una instancia de esta clase y pasarla al `Run` método de la operación Quantum que desea ejecutar junto con el resto de los parámetros:</span><span class="sxs-lookup"><span data-stu-id="34012-107">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a><span data-ttu-id="34012-108">IDisposable</span><span class="sxs-lookup"><span data-stu-id="34012-108">IDisposable</span></span>

<span data-ttu-id="34012-109">La `QuantumSimulator` clase implementa <xref:System.IDisposable> , por lo que `Dispose` se debe llamar al método una vez que ya no se use la instancia del simulador.</span><span class="sxs-lookup"><span data-stu-id="34012-109">The `QuantumSimulator` class implements <xref:System.IDisposable>, thus the `Dispose` method should be called once the instance of the simulator is not used anymore.</span></span> <span data-ttu-id="34012-110">La mejor manera de hacerlo es ajustar el simulador dentro de una `using` instrucción, como en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="34012-110">The best way to do this is to wrap the simulator within a `using` statement, as in the example above.</span></span>

## <a name="seed"></a><span data-ttu-id="34012-111">Seed</span><span class="sxs-lookup"><span data-stu-id="34012-111">Seed</span></span>

<span data-ttu-id="34012-112">`QuantumSimulator`Utiliza un generador de números aleatorios para simular la aleatoriedad de Quantum.</span><span class="sxs-lookup"><span data-stu-id="34012-112">The `QuantumSimulator` uses a random number generator to simulate quantum randomness.</span></span> <span data-ttu-id="34012-113">Con fines de prueba, a veces resulta útil tener resultados deterministas.</span><span class="sxs-lookup"><span data-stu-id="34012-113">For testing purposes, it is sometimes useful to have deterministic results.</span></span> <span data-ttu-id="34012-114">Esto puede lograrse proporcionando un valor de inicialización para el generador de números aleatorios en el `QuantumSimulator` constructor de a través del `randomNumberGeneratorSeed` parámetro:</span><span class="sxs-lookup"><span data-stu-id="34012-114">This can be accomplished by providing a seed for the random number generator in the `QuantumSimulator`'s constructor via the `randomNumberGeneratorSeed` parameter:</span></span>

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a><span data-ttu-id="34012-115">Subprocesos</span><span class="sxs-lookup"><span data-stu-id="34012-115">Threads</span></span>

<span data-ttu-id="34012-116">`QuantumSimulator`Usa [OpenMP](http://www.openmp.org/) para paralelizar el álgebra lineal requerido.</span><span class="sxs-lookup"><span data-stu-id="34012-116">The `QuantumSimulator` uses [OpenMP](http://www.openmp.org/) to parallelize the linear algebra required.</span></span> <span data-ttu-id="34012-117">De forma predeterminada, OpenMP usa todos los subprocesos de hardware disponibles, lo que significa que, por lo general, los programas con un número reducido de qubits se ejecutarán lentamente, ya que la coordinación necesaria mermará el trabajo real.</span><span class="sxs-lookup"><span data-stu-id="34012-117">By default OpenMP uses all available hardware threads, which means that programs with small numbers of qubits will often run slowly because the coordination required will dwarf the actual work.</span></span> <span data-ttu-id="34012-118">Esto puede corregirse si se establece la variable de entorno `OMP_NUM_THREADS` en un número pequeño.</span><span class="sxs-lookup"><span data-stu-id="34012-118">This can be fixed by setting the environment variable `OMP_NUM_THREADS` to a small number.</span></span> <span data-ttu-id="34012-119">Como norma general, un subproceso es adecuado para un máximo de 4 qubits aproximadamente y, a partir de ahí, resulta adecuado un subproceso adicional por qubit, aunque esto depende en gran medida del algoritmo.</span><span class="sxs-lookup"><span data-stu-id="34012-119">As a very rough rule of thumb, 1 thread is good for up to about 4 qubits, and then an additional thread per qubit is good, although this is highly dependent on your algorithm.</span></span>

