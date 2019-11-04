---
title: Ancho del contador | Simulador de seguimiento de equipo Quantum | Microsoft Docs
description: Información general sobre el simulador de seguimiento de equipos Quantum
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: ae0c0ec2e677be03dc8dc1497dc62ad9034295a4
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442406"
---
# <a name="width-counter"></a><span data-ttu-id="2b798-103">Ancho (contador)</span><span class="sxs-lookup"><span data-stu-id="2b798-103">Width Counter</span></span>

<span data-ttu-id="2b798-104">El `Width Counter` cuenta el número de qubits asignados y prestados por cada operación.</span><span class="sxs-lookup"><span data-stu-id="2b798-104">The `Width Counter` counts the number of qubits allocated and borrowed by each operation.</span></span>
<span data-ttu-id="2b798-105">Todas las operaciones del espacio de nombres `Microsoft.Quantum.Primitive` se expresan en términos de rotaciones de qubit individuales, de T, de qubit Clifford, de CNOT y de qubit de Pauli.</span><span class="sxs-lookup"><span data-stu-id="2b798-105">All operations from the `Microsoft.Quantum.Primitive` namespace are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="2b798-106">Algunas de las operaciones primitivas pueden asignar qubits adicionales.</span><span class="sxs-lookup"><span data-stu-id="2b798-106">Some of the primitive operations can allocate extra qubits.</span></span> <span data-ttu-id="2b798-107">Por ejemplo, multiplique las puertas `X` controladas o las puertas de `T` controladas.</span><span class="sxs-lookup"><span data-stu-id="2b798-107">For example, multiply controlled `X` gates or controlled `T` gates.</span></span> <span data-ttu-id="2b798-108">Vamos a calcular el número de qubits adicionales asignados por la implementación de una puerta de `X` controlada por multiplicación:</span><span class="sxs-lookup"><span data-stu-id="2b798-108">Let us compute the number of extra qubits allocated by the implementation of a multiply controlled `X` gate:</span></span>

```qsharp
open Microsoft.Quantum.Primitive;
open Microsoft.Quantum.Arrays;
operation MultiControlledXDriver( numberOfQubits : Int ) : Unit {

    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a><span data-ttu-id="2b798-109">Usar el contador de ancho C# en un programa</span><span class="sxs-lookup"><span data-stu-id="2b798-109">Using Width Counter within a C# Program</span></span>

<span data-ttu-id="2b798-110">La multiplicación controlada `X` que actúe en un total de 5 qubits asignará 2 qubits auxiliares y el ancho de entrada será 5.</span><span class="sxs-lookup"><span data-stu-id="2b798-110">Multiply controlled `X` acting on a total of 5 qubits will allocate 2 ancillary qubits and its input width will be 5.</span></span> <span data-ttu-id="2b798-111">Para comprobar que este es el caso, podemos usar el siguiente C# programa:</span><span class="sxs-lookup"><span data-stu-id="2b798-111">To check that this is the case, we can use the following C# program:</span></span>

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = MultiControlledXDriver.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, MultiControlledXDriver>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, MultiControlledXDriver>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

<span data-ttu-id="2b798-112">La primera parte del programa ejecuta `MultiControlledXDriver`.</span><span class="sxs-lookup"><span data-stu-id="2b798-112">The first part of the program executes `MultiControlledXDriver`.</span></span> <span data-ttu-id="2b798-113">En la segunda parte usamos el método `QCTraceSimulator.GetMetric` para obtener el número de qubits asignados, así como el número de qubits que se han controlado `X` recibido como entrada.</span><span class="sxs-lookup"><span data-stu-id="2b798-113">In the second part we use the method `QCTraceSimulator.GetMetric` to get the number of allocated qubits as well as the number of qubits that Controlled `X` received as input.</span></span> 

<span data-ttu-id="2b798-114">Por último, para generar todas las estadísticas recopiladas por el contador de ancho en formato CSV, podemos usar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2b798-114">Finally, to output all the statistics collected by width counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="2b798-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b798-115">See also</span></span> ##

- <span data-ttu-id="2b798-116">Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) de equipos Quantum.</span><span class="sxs-lookup"><span data-stu-id="2b798-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
