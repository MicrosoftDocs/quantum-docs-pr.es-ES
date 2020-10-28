---
uid: Microsoft.Quantum.Simulation.TrotterSimulationAlgorithmImpl
title: Operación TrotterSimulationAlgorithmImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterSimulationAlgorithmImpl
qsharp.summary: Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp(_-iHt_).
ms.openlocfilehash: 2af68532d700a1fb5b037707ce4650696cbe1a64
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733996"
---
# <a name="trottersimulationalgorithmimpl-operation"></a><span data-ttu-id="7a352-102">Operación TrotterSimulationAlgorithmImpl</span><span class="sxs-lookup"><span data-stu-id="7a352-102">TrotterSimulationAlgorithmImpl operation</span></span>

<span data-ttu-id="7a352-103">Espacio de nombres: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="7a352-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="7a352-104">Configura [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7a352-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7a352-105">Realiza llamadas repetidas a `TrotterStep` para aproximarse al operador de evolución de tiempo ( _-iHt_ ).</span><span class="sxs-lookup"><span data-stu-id="7a352-105">Makes repeated calls to `TrotterStep` to approximate the time-evolution operator exp( _-iHt_ ).</span></span>

```qsharp
operation TrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="7a352-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="7a352-106">Input</span></span>

### <a name="trotterstepsize--double"></a><span data-ttu-id="7a352-107">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7a352-107">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7a352-108">Duración de la evolución de tiempo simulada en un solo paso de Trotter.</span><span class="sxs-lookup"><span data-stu-id="7a352-108">Duration of simulated time-evolution in single Trotter step.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="7a352-109">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7a352-109">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7a352-110">Orden de integrador de Trotter.</span><span class="sxs-lookup"><span data-stu-id="7a352-110">Order of Trotter integrator.</span></span> <span data-ttu-id="7a352-111">Debe ser 1 o un número par.</span><span class="sxs-lookup"><span data-stu-id="7a352-111">This must be either 1 or an even number.</span></span>


### <a name="maxtime--double"></a><span data-ttu-id="7a352-112">maxTime: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7a352-112">maxTime : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7a352-113">Duración total de la simulación $t $.</span><span class="sxs-lookup"><span data-stu-id="7a352-113">Total duration of simulation $t$.</span></span>


### <a name="evolutiongenerator--evolutiongenerator"></a><span data-ttu-id="7a352-114">evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span><span class="sxs-lookup"><span data-stu-id="7a352-114">evolutionGenerator : [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)</span></span>

<span data-ttu-id="7a352-115">Una descripción completa del sistema que se va a simular.</span><span class="sxs-lookup"><span data-stu-id="7a352-115">A complete description of the system to be simulated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="7a352-116">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7a352-116">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7a352-117">Qubits actuado por simulación.</span><span class="sxs-lookup"><span data-stu-id="7a352-117">Qubits acted on by simulation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7a352-118">Salida: [unidad](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7a352-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

