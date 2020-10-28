---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithmImpl
title: Operación TimeDependentTrotterSimulationAlgorithmImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithmImpl
qsharp.summary: Implementation of multiple Trotter steps to approximate a unitary operator that solves the time-dependent Schrödinger equation.
ms.openlocfilehash: c6d1c976d29c69d3ac14d9a2be09826602c8cc1d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730676"
---
# <a name="timedependenttrottersimulationalgorithmimpl-operation"></a><span data-ttu-id="3ed11-102">Operación TimeDependentTrotterSimulationAlgorithmImpl</span><span class="sxs-lookup"><span data-stu-id="3ed11-102">TimeDependentTrotterSimulationAlgorithmImpl operation</span></span>

<span data-ttu-id="3ed11-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="3ed11-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="3ed11-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3ed11-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3ed11-105">Implementación de varios pasos de Trotter para aproximar un operador unitario que resuelve la ecuación de Schrödinger dependiente del tiempo.</span><span class="sxs-lookup"><span data-stu-id="3ed11-105">Implementation of multiple Trotter steps to approximate a unitary operator that solves the time-dependent Schrödinger equation.</span></span>

```qsharp
operation TimeDependentTrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionSchedule : Microsoft.Quantum.Simulation.EvolutionSchedule, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3ed11-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3ed11-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="3ed11-107">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3ed11-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3ed11-108">Duración de la evolución de tiempo simulada en un solo paso de Trotter.</span><span class="sxs-lookup"><span data-stu-id="3ed11-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="3ed11-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3ed11-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3ed11-110">Orden de integrador de Trotter.</span><span class="sxs-lookup"><span data-stu-id="3ed11-110">Order of Trotter integrator.</span></span> <span data-ttu-id="3ed11-111">Debe ser 1 o un número par.</span><span class="sxs-lookup"><span data-stu-id="3ed11-111">This must be either 1 or an even number.</span></span>


### <a name="maxtime--double"></a><span data-ttu-id="3ed11-112">maxTime: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3ed11-112">maxTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3ed11-113">Duración total de la simulación $t $.</span><span class="sxs-lookup"><span data-stu-id="3ed11-113">Total duration of simulation $t$.</span></span>


### <a name="evolutionschedule--evolutionschedule"></a><span data-ttu-id="3ed11-114">evolutionSchedule: [evolutionSchedule](xref:Microsoft.Quantum.Simulation.EvolutionSchedule)</span><span class="sxs-lookup"><span data-stu-id="3ed11-114">evolutionSchedule : [EvolutionSchedule](xref:Microsoft.Quantum.Simulation.EvolutionSchedule)</span></span>

<span data-ttu-id="3ed11-115">Una descripción completa del sistema dependiente del tiempo que se va a simular.</span><span class="sxs-lookup"><span data-stu-id="3ed11-115">A complete description of the time-dependent system to be simulated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="3ed11-116">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3ed11-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3ed11-117">Qubits actuado por simulación.</span><span class="sxs-lookup"><span data-stu-id="3ed11-117">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3ed11-118">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3ed11-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

