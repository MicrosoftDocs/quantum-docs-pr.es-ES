---
title: 'Contador de ancho: kit de desarrollo de Quantum'
description: Obtenga información sobre el contador de ancho de QDK de Microsoft, que usa el simulador de seguimiento de Quantum para contar el número de operaciones de qubits asignadas y prestadas por el Q# programa.
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 701c36dd8c8b087a2728cd935aee0c2ffc4f59f9
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835951"
---
# <a name="quantum-trace-simulator-width-counter"></a><span data-ttu-id="d4791-103">Simulador de seguimiento de Quantum: contador de ancho</span><span class="sxs-lookup"><span data-stu-id="d4791-103">Quantum trace simulator: width counter</span></span>

<span data-ttu-id="d4791-104">El contador de ancho forma parte del [simulador de seguimiento Quantum](xref:microsoft.quantum.machines.qc-trace-simulator.intro)del kit de desarrollo de Quantum.</span><span class="sxs-lookup"><span data-stu-id="d4791-104">The width counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="d4791-105">Puede usarlo para contar el número de qubits asignados y prestados por cada operación en un Q# programa.</span><span class="sxs-lookup"><span data-stu-id="d4791-105">You can use it to count the number of qubits allocated and borrowed by each operation in a Q# program.</span></span> <span data-ttu-id="d4791-106">Algunas operaciones primitivas pueden asignar qubits adicionales, por ejemplo, las operaciones controladas de multiplicación `X` o `T` las operaciones controladas.</span><span class="sxs-lookup"><span data-stu-id="d4791-106">Some primitive operations can allocate extra qubits, for example, multiply controlled `X` operations or controlled `T` operations.</span></span>

## <a name="invoking-the-width-counter"></a><span data-ttu-id="d4791-107">Invocar el contador de ancho</span><span class="sxs-lookup"><span data-stu-id="d4791-107">Invoking the width counter</span></span>

<span data-ttu-id="d4791-108">Para ejecutar el simulador de seguimiento de Quantum con el contador de ancho, debe crear una <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instancia de, establecer la `UseWidthCounter` propiedad en **true**y, a continuación, crear una nueva <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instancia de con `QCTraceSimulatorConfiguration` como parámetro.</span><span class="sxs-lookup"><span data-stu-id="d4791-108">To run the quantum trace simulator with the width counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseWidthCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a><span data-ttu-id="d4791-109">Usar el contador de ancho en un programa host de C#</span><span class="sxs-lookup"><span data-stu-id="d4791-109">Using the width counter in a C# host program</span></span>

<span data-ttu-id="d4791-110">En el ejemplo de C# que se muestra a continuación en esta sección se calcula el número de qubits adicionales asignados por la implementación de una operación controlada multiplicación <xref:microsoft.quantum.intrinsic.x> , basándose en el Q# código de ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d4791-110">The C# example that follows in this section computes the number of extra qubits allocated by the implementation of a multiply controlled <xref:microsoft.quantum.intrinsic.x> operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

<span data-ttu-id="d4791-111">La operación de multiplicación controlada <xref:microsoft.quantum.intrinsic.x> actúa en un total de cinco qubits, asigna dos [qubits auxiliares](xref:microsoft.quantum.glossary#ancilla)y tiene un ancho de entrada de **5**.</span><span class="sxs-lookup"><span data-stu-id="d4791-111">The multiply controlled <xref:microsoft.quantum.intrinsic.x> operation acts on a total of five qubits, allocates two [ancillary qubits](xref:microsoft.quantum.glossary#ancilla), and has an input width of **5**.</span></span> <span data-ttu-id="d4791-112">Use el siguiente programa de C# para comprobar los recuentos:</span><span class="sxs-lookup"><span data-stu-id="d4791-112">Use the following C# program to verify the counts:</span></span>

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
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

<span data-ttu-id="d4791-113">La primera parte del programa ejecuta la `ApplyMultiControlledX` operación.</span><span class="sxs-lookup"><span data-stu-id="d4791-113">The first part of the program runs the `ApplyMultiControlledX` operation.</span></span> <span data-ttu-id="d4791-114">La segunda parte usa el [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) método para recuperar el número de qubits asignados, así como el número de qubits que la `Controlled X` operación recibió como entrada.</span><span class="sxs-lookup"><span data-stu-id="d4791-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of allocated qubits as well as the number of qubits that the `Controlled X` operation received as input.</span></span> 

<span data-ttu-id="d4791-115">Por último, puede generar todas las estadísticas recopiladas por el contador de ancho en formato CSV con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d4791-115">Finally, you can output all the statistics collected by the width counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="d4791-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4791-116">See also</span></span>

- <span data-ttu-id="d4791-117">Información general del [simulador de seguimiento](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Quantum del kit de desarrollo de Quantum.</span><span class="sxs-lookup"><span data-stu-id="d4791-117">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="d4791-118">Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API.</span><span class="sxs-lookup"><span data-stu-id="d4791-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="d4791-119">Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API.</span><span class="sxs-lookup"><span data-stu-id="d4791-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="d4791-120">Referencia de la <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter> API.</span><span class="sxs-lookup"><span data-stu-id="d4791-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter> API reference.</span></span>
