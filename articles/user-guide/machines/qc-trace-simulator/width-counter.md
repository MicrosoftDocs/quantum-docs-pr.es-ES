---
title: Ancho (contador)
description: Obtenga información sobre el contador de ancho de QDK de Microsoft, que cuenta el número de qubits asignado y prestado por cada operación en un programa Quantum.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275565"
---
# <a name="width-counter"></a><span data-ttu-id="ab5b5-103">Ancho (contador)</span><span class="sxs-lookup"><span data-stu-id="ab5b5-103">Width Counter</span></span>

<span data-ttu-id="ab5b5-104">`Width Counter`Cuenta el número de qubits asignados y prestados por cada operación.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-104">The `Width Counter` counts the number of qubits allocated and borrowed by each operation.</span></span>
<span data-ttu-id="ab5b5-105">Todas las operaciones del `Microsoft.Quantum.Intrinsic` espacio de nombres se expresan en términos de rotaciones de un solo qubit, de T, de qubit Clifford, de CNOT de qubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-105">All operations from the `Microsoft.Quantum.Intrinsic` namespace are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="ab5b5-106">Algunas de las operaciones primitivas pueden asignar qubits adicionales.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-106">Some of the primitive operations can allocate extra qubits.</span></span> <span data-ttu-id="ab5b5-107">Por ejemplo, multiplique las `X` puertas controladas o las puertas controladas `T` .</span><span class="sxs-lookup"><span data-stu-id="ab5b5-107">For example, multiply controlled `X` gates or controlled `T` gates.</span></span> <span data-ttu-id="ab5b5-108">Vamos a calcular el número de qubits adicionales asignados por la implementación de una puerta controlada por multiplicación `X` :</span><span class="sxs-lookup"><span data-stu-id="ab5b5-108">Let us compute the number of extra qubits allocated by the implementation of a multiply controlled `X` gate:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a><span data-ttu-id="ab5b5-109">Usar el contador de ancho en un programa de C#</span><span class="sxs-lookup"><span data-stu-id="ab5b5-109">Using Width Counter within a C# Program</span></span>

<span data-ttu-id="ab5b5-110">La multiplicación controlada `X` por un total de 5 qubits asignará 2 qubits auxiliares y el ancho de entrada será 5.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-110">Multiply controlled `X` acting on a total of 5 qubits will allocate 2 ancillary qubits and its input width will be 5.</span></span> <span data-ttu-id="ab5b5-111">Para comprobar que este es el caso, podemos usar el siguiente programa de C#:</span><span class="sxs-lookup"><span data-stu-id="ab5b5-111">To check that this is the case, we can use the following C# program:</span></span>

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = ApplyMultiControlledX.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

<span data-ttu-id="ab5b5-112">Se ejecuta la primera parte del programa `ApplyMultiControlledX` .</span><span class="sxs-lookup"><span data-stu-id="ab5b5-112">The first part of the program executes `ApplyMultiControlledX`.</span></span> <span data-ttu-id="ab5b5-113">En la segunda parte usamos el método `QCTraceSimulator.GetMetric` para obtener el número de qubits asignados, así como el número de qubits que se `X` han controlado como entrada.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-113">In the second part we use the method `QCTraceSimulator.GetMetric` to get the number of allocated qubits as well as the number of qubits that Controlled `X` received as input.</span></span> 

<span data-ttu-id="ab5b5-114">Por último, para generar todas las estadísticas recopiladas por el contador de ancho en formato CSV, podemos usar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ab5b5-114">Finally, to output all the statistics collected by width counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="ab5b5-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab5b5-115">See also</span></span> ##

- <span data-ttu-id="ab5b5-116">Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) de equipos Quantum.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
